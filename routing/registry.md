# Routing Registry

Декларативная конфигурация: при каких условиях активировать capability
и кто сейчас является лучшим исполнителем.

Этот файл меняется при смене стека. Архитектура (CLAUDE.md) от этого не меняется.
Capabilities определены в CLAUDE.md → Capability Registry.

---

Execution:
  trigger:
    default: true
  preferred:
    - Claude
  fallback:
    - Gemini

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
  fallback:
    - Claude
  model_tier_default: >
    Разведочный проход по умолчанию — на более дешёвой/быстрой модели, если
    задача не требует архитектурного суждения. Рекомендация, не жёсткое
    требование — конкретный выбор модели остаётся за исполнителем и не
    фиксируется здесь, чтобы не привязывать AI_OS к ценовой модели провайдера.

---

ArchitectureReview:
  trigger:
    new_agent: true
    ownership_change: true
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
