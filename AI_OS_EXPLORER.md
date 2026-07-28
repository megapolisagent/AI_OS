# 🗺 Исследовать систему

[[AI_OS_DASHBOARD|🏠 Сегодня →]]

Каждый раздел ниже свёрнут по умолчанию — клик по названию раскрывает его
(родной механизм Obsidian, callout-блоки, без плагинов). Числа посчитаны
вручную по факту на 2026-07-27, не живые.

> [!note]- 📁 Направления (10)
> - Финансы — приоритет 1, направление без своего Проекта в AI_OS
> - Мегаполис — приоритет 2 → см. «Проекты»
> - Здоровье — приоритет 3 — **пусто**, ни Проекта, ни Агента
> - Дети/Родители — приоритет 4 — **пусто**
> - Спорт — приоритет 5 — **пусто**
> - Личная жизнь, Саморазвитие, Путешествия, Духовное развитие, Дом/Дача — фоновые, **пусто**

> [!note]- 📁 Проекты (8)
> - **Мегаполис** (PRJ-007) — Маркетолог: Фаза 1 (Архитектура) закрыта 2026-07-27 (v1.4), Фаза 2 (Реализация) не начата
>   - 🤖 Агенты (2): [[specializations/marketing_agent|Маркетолог]], [[specializations/landing_page_agent|Агент лендингов]]
>   - 📚 Документ: [[projects/registry.md|запись в реестре]]
> - MAIN_ENGINEER (PRJ-001) — В работе — ⚠️ путь не подтверждён (2026-07-28), см. `projects/registry.md`
> - hh-parser (PRJ-002) — В работе — ⚠️ путь не подтверждён (2026-07-28)
> - seo-machine (PRJ-003) — Активен — ⚠️ путь не подтверждён (2026-07-28)
> - vibe-test (PRJ-004) — Активен — ⚠️ путь не подтверждён (2026-07-28)
> - property-analyst (PRJ-005) — заблокирован, ждёт объект от Марии — ⚠️ путь не подтверждён (2026-07-28)
> - MAIN_ASSISTANT (PRJ-006) — мигрирован → AI_OS — ⚠️ путь не подтверждён (2026-07-28), см. `projects/registry.md`
> - Onboarding Template (INF-001) — Активен — ⚠️ путь не подтверждён (2026-07-28), не найден и в archive/

> [!note]- 🤖 Агенты (3)
> - **[[specializations/marketing_agent|Маркетолог]]**
>   - Проект: Мегаполис
>   - Skills: нет (Фаза 2 не начата)
>   - Решения (3): [[decisions/system/2026-07-26_marketer-agent-design|marketer-agent-design]], [[decisions/system/2026-07-26_marketer-capability-map-final|marketer-capability-map-final]], [[decisions/system/2026-07-26_saas-architecture-patterns-research|saas-architecture-patterns-research]]
> - **[[specializations/landing_page_agent|Агент лендингов]]**
>   - Проект: Мегаполис и связанные инициативы
>   - Skills: [[skills/conversion-method/SKILL|conversion-method]]
> - **[[specializations/fear_to_action_coach|Коуч «Страх → Действие»]]**
>   - Проект: нет — кросс-направленческий
>   - [[specializations/maria_coaching_brief|Client Profile]], [[specializations/fear_to_action_coach_log|Calibration Log]]

> [!note]- 🧩 Skills (7)
> - [[skills/idea-calibration|idea-calibration]] — gate перед архитектурными решениями
> - [[skills/capability-creation-methodology|capability-creation-methodology]]
> - [[skills/architecture-review|architecture-review]]
> - [[skills/opportunity-discovery|opportunity-discovery]]
> - [[skills/conversion-method/SKILL|conversion-method]] — использует: Агент лендингов
> - [[skills/taste-capture|taste-capture]] — не привязан ни к одному агенту
> - [[skills/youtube-analysis|youtube-analysis]] — не привязан ни к одному агенту

> [!note]- 🧠 Способности AI_OS (10)
> Операционный слой самой AI_OS, не бизнес-функции.
> ![[CLAUDE.md#Реестр способностей (Capability Registry)]]

> [!note]- 📄 Решения (24 — открытых: 7)
> ```dataview
> TABLE WITHOUT ID file.link AS "Файл", Тип, Статус, Дата
> FROM "decisions"
> WHERE contains(lower(Статус), "открыт")
> SORT Дата DESC
> ```

> [!note]- 📚 Исследования
> ```dataview
> TABLE WITHOUT ID file.link AS "Файл", Тип, Дата
> FROM "decisions"
> WHERE contains(lower(Тип), "research")
> SORT Дата DESC
> ```

> [!note]- 🗂 Контекст (3)
> - [[context/life_context.md|Жизнь]] — карта внимания, актуальна на 2026-06-16
> - [[context/user_maria.md|Профиль Марии]]
> - [[context/strategic_questions.md|Стратегические вопросы]]

> [!note]- 🗄 Архив (3)
> - [[archive/wheel_of_life_baseline.md|wheel_of_life_baseline]]
> - [[archive/system_bootstrap.md|system_bootstrap]]
> - [[archive/main_assistant_discovery.md|main_assistant_discovery]]

> [!note]- 🗺 Карта связей (Canvas/Graph)
> Пока — встроенный Graph view Obsidian (иконка графа в левой панели).
> Выбор инструмента подчинён [[decisions/system/2026-07-27_ai-os-interaction-principles.md|10 принципам взаимодействия]] — решается отдельно, идёт отдельное исследование.

---

## О странице

> Ничего не хранит — собирает уже существующие `.md`-файлы в представления
> (запросы, вставки, вручную сверенные счётчики), не копии. Источник истины
> не меняется: если раздел выше пуст, значит не заполнен исходный файл, не
> сломана эта страница. Термины — по
> [[decisions/system/2026-07-27_ai-os-knowledge-graph-layer.md|глоссарию визуального слоя]]
> и [[decisions/system/2026-07-27_ai-os-interaction-principles.md|10 принципам взаимодействия]].

**Требование для работы:**
1. Открыть папку `AI_OS` как vault (Obsidian → Open folder as vault).
2. Включить community-plugin **Dataview**: Settings → Community plugins →
   Turn off restricted mode → Browse → «Dataview» → Install → Enable.

Без Dataview блоки выше показываются как обычный код, не как таблицы —
это ожидаемо, не поломка. Свёрнутые блоки (callouts) — стандартная функция
Obsidian, плагин для них не нужен.

**Открыть эту страницу автоматически при загрузке vault** —
**ПРЕДПОЛАГАЕМ, не проверено:** обычно это делает community-plugin
**Homepage**. Если важно — поставить так же, как Dataview, и указать эту
страницу.
