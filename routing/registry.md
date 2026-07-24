# Routing Registry

Декларативная конфигурация: при каких условиях активировать capability
и кто сейчас является лучшим исполнителем.

Этот файл меняется при смене стека. Архитектура (CLAUDE.md) от этого не меняется.
Capabilities определены в CLAUDE.md → Capability Registry.

> Граница (зафиксировано 2026-07-20): этот файл — карта маршрутизации (кто
> исполнитель, при каком триггере, какой fallback), не движок принятия
> решений. Если правила выбора внутри одной записи (когда делегировать, как
> оценивать объём, как выбирать модель) становятся существенно сложнее
> короткой заметки — выносить отдельной Agent Execution Policy, не
> разрастать здесь. `Execution.subtask_tier_note` уже ближе к policy, чем к
> routing — оставлено как есть по явной просьбе не менять сейчас, но это не
> гипотетический риск на будущее, а состояние на сегодня.

---

Execution:
  trigger:
    default: true
  preferred:
    - Claude
  fallback:
    - Gemini
  subtask_tier_note: >
    Minimal Sufficiency применяется не к основной сессии (там почти всегда
    нужно суждение — архитектура, тон под стандарт Марии, принципы CLAUDE.md,
    см. context/user_maria.md), а только к делегируемым механическим
    подзадачам внутри неё.

    Две независимые оси (исправлено 2026-07-20 — не путать, как в первой
    версии этой заметки):
    - Model routing — какая модель используется.
    - Execution routing — инлайн в текущей сессии или через subagent.
    Комбинации независимы: subagent можно запускать и на дорогой модели
    (изоляция контекста — другой повод, не экономия), инлайн — только на
    модели текущей сессии.

    Технически подтверждено (Agent tool, параметр `model`: «overrides the
    definition for this one call»): subagent реально запускается на модели,
    отличной от основной сессии — не гипотеза, факт схемы инструмента.
    НЕ подтверждено и, судя по тому, что `/model` переключает модель на
    сессию целиком, а не на ход — вероятно недоступно: инлайн-переключение
    модели для одного сообщения внутри непрерывной сессии. Поэтому
    реализуема сегодня ровно одна комбинация для экономии — **subagent на
    дешёвой модели**; «дешёвая модель инлайн» не входит в архитектуру, пока
    это не подтверждено отдельно.

    Оба условия обязательны одновременно для этой единственной комбинации:
    (а) триаж skills/idea-calibration.md Шаг 0 (Impact/Uncertainty/
    Complexity) — все три оси low: один проверяемый исход, ноль интерпретации
    намерения, ноль архитектурного/принципиального веса;
    (б) объём работы достаточен, чтобы окупить cold-start subagent'а (массовый
    rename, батч-аудит файлов, структурная выгрузка из многих файлов) —
    единичный Read/Edit/Grep НЕ делегируется: для одной операции накладные
    расходы на делегирование дороже экономии на модели — делегирование там
    само нарушает Minimal Sufficiency, а не соблюдает его.

    Хотя бы одна ось high, или объём недостаточен для (б) — остаётся дефолтная
    модель инлайн, без исключений.

---

LargeCorpusAnalysis:
  trigger:
    files: ">=10"
    types:
      - archive
      - large database
      - document corpus
    large_context: true
    unpredictable_scope: true
    note: >
      Счётный порог (10+ файлов) — одна эвристика среди прочих, не единственное
      условие. Любое исследование с заранее непредсказуемым объёмом сырого
      материала уходит в изолированный контекст, даже если файлов меньше 10.
  preferred:
    - Gemini
    - Kimi K3
  fallback:
    - Claude
  model_tier_default: >
    Разведочный проход по умолчанию — на более дешёвой/быстрой модели, если
    задача не требует архитектурного суждения. Рекомендация, не жёсткое
    требование — конкретный выбор модели остаётся за исполнителем и не
    фиксируется здесь, чтобы не привязывать AI_OS к ценовой модели провайдера.
  kimi_k3_note: >
    Добавлен 2026-07-20. Предпочтителен вместо Gemini ТОЛЬКО при объёме
    >200K токенов — на этом объёме тариф Gemini 3.1 Pro переходит на
    long-context ставку $4/$18 за 1M против плоских $3/$15 у K3 (цены на
    2026-07-20 — это дешевле по опубликованным API-тарифам, не гарантия
    итоговой экономии: число проходов, качество синтеза и потребность в
    доп. валидации могут изменить полную стоимость задачи). Ниже 200K
    Gemini дешевле — K3 не становится дефолтом безусловно.

    Data policy (обязательное условие, не рекомендация): применимо только к
    несекретным/публичным корпусам (GitHub, статьи, open source,
    документация) — Moonshot AI китайская компания, юрисдикция иная. Для
    внутренних данных экосистемы (финансы, клиентские материалы Мегаполиса,
    коммерческая информация) K3 не используется по умолчанию — остаётся
    текущий маршрут (Gemini/Claude), переход требует явного подтверждения
    Марии каждый раз, не разового решения здесь.

---

ArchitectureReview:
  trigger:
    new_agent: true
    ownership_change: true
    existing_agent_redefinition: true
    high_risk: true
    sst_violation_risk: true
    execution_drift: true
  preferred:
    - Codex
  fallback:
    - Claude

---

CodeReview:
  trigger:
    significant_code_change: true
    before_delivery: true
  preferred:
    - Codex
  fallback:
    - Claude

---

WorldResearch:
  trigger:
    idea_calibration_step2: true
    architecture_review_research: true
  preferred:
    - Exa
  fallback:
    - WebSearch
  note: >
    Capability не меняется. Меняется executor.
    Exa — семантический поиск (концептуальные запросы).
    WebSearch — точные запросы (имена, версии, конкретные URL).

---

OpportunityDiscovery:
  trigger:
    new_technology: true
    new_model_release: true
    video_article_research: true
    github_mcp_sdk_api: true
    startup_or_tool: true
    note: >
      Не рутинные задачи (баг-фиксы, точечные правки внутри уже выбранной
      архитектуры, обычная разработка) — только технологический/исследова-
      тельский вход для экосистемы. Mandatory once matched — как Architecture
      Review при достижении порога, не факультативный вызов.
  preferred:
    - Claude
  fallback:
    - Claude
  skill: skills/opportunity-discovery.md

---

CapabilityDesign:
  trigger:
    build: true
    note: >
      Capability Map показывает пустой узел, связанный со стратегической
      целью, либо запрос независимо повторился (см. CLAUDE.md → Роль AO).
  preferred:
    - Claude
  fallback:
    - Claude

---

CapabilityEvolution:
  trigger:
    evolve: true
    note: >
      Событие — новый источник/модель/инструмент, накопленный опыт
      использования агента; не календарь. Включает периодическую проверку
      определения самого AO после каждого реального цикла Build/Evolve
      (см. CLAUDE.md → Capability Registry → Capability Evolution).
  preferred:
    - Claude
  fallback:
    - Claude

---

ExternalSystemsAssimilation:
  trigger:
    external_system_brought: true
  preferred:
    - Claude
  fallback:
    - Claude

---

OutcomeAccountability:
  trigger:
    artifact_completion_with_claimed_external_result: true
  preferred:
    - Claude
  fallback:
    - Claude
