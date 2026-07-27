---
Версия: 1.0
Дата: 2026-07-26
Тип: Итоговая Capability Map профессии «Маркетолог» — Направления 4-6
     + сборка. Независимое исследование, не опирается на выводы цикла
     2026-07-25 как на истину (по прямому указанию Марии)
Статус: ЗАФИКСИРОВАНО (2026-07-26, решение Марии). Capability Model не
        пересматривается без новых внешних фактов — Decision Monotonicity.
        Два пункта остаются сознательно открытыми — Marketing Effectiveness
        Review, Go-to-Market/Distribution — не закрывать эвристически без
        новых данных. Проектирование агента/SaaS — следующая фаза, живёт
        отдельно от исследования профессии (см. См. также)
---

# Capability Map профессии «Маркетолог»

Основа: `2026-07-26_marketer-agreement-matrix.md` (подтверждена, не
перерабатывается). 11 Candidate Capabilities, 2 открытых пункта.

---

## Направление 4 — Capability Decomposition

Не линейный пайплайн из брифа-иллюстрации — реальная структура, выведенная
из матрицы, имеет **backbone + два cross-cutting слоя**, это не было задано
заранее, а стало видно только после матрицы.

### Backbone (последовательная зависимость по входу/выходу)

```
Audience Research
      ↓ (Audience Profile / JTBD-инсайт)
Positioning & Category Definition ←── Brand Strategy & Equity Management
      ↓ (Positioning Statement)        (персистентный актив, не разовый шаг —
Messaging & Persuasion Design           см. Направление 5)
      ↓ (Messaging Framework)
Content Production
      ↓ (Published Content)
Campaign / Journey Orchestration ←── Go-to-Market/Distribution Strategy
      ↓ (Executed Touchpoints)         (ОТКРЫТО: одна способность или несколько)
Measurement & Reporting
      ↓ (Performance Signal) ──────────┐
                                        │ обратная связь
Growth Experimentation ←────────────────┘
```

**Offer & Value Proposition Design** — не встроен в цепочку однозначно
(Underdetermined в матрице): тематически ближе всего к Positioning, но
недостаточно данных, чтобы утверждать зависимость. Помечаю рядом с
Positioning пунктиром, не как решённое место в графе.

### Cross-cutting (не стадия пайплайна, а функция, применяемая к любой стадии)

- **Growth Experimentation** — не шаг после Measurement, а методология
  тестирования, применимая к Messaging, Offer, Content, каналу одновременно.
  В матрице у неё паттерн Research Gap, но по факту метода (Balfour/Ellis)
  она горизонтальна, не последовательна — это стало видно только при
  попытке встроить её в пайплайн, не было очевидно на этапе матрицы.
- **Marketing Effectiveness Review** — по функции (Ritson) тоже
  горизонтальна: проверяет решения на любой стадии backbone, не только в
  конце. **Место в графе — горизонтальная проверка, это не то же самое, что
  решение о её таксономическом статусе (Capability vs Specialization) —
  тот вопрос остаётся открытым, как договорились.**

---

## Направление 5 — Interface (входы/выходы профессии)

Проверено по исследованию, не собрано заранее по шаблону брифа — где
шаблон Марии («ICP, сегменты, JTBD, positioning, messaging, GTM, контентная
стратегия, KPI») подтвердился, а где потребовал уточнения, показано явно.

### Вход в профессию целиком (не в отдельную capability)

- Существующий бизнес/продукт — ЗНАЕМ по Kotler-определению (Направление 1):
  маркетинг формирует спрос на существующее предложение, не создаёт нужды
  из ничего — то есть вход не «идея из воздуха», а всегда что-то уже
  существующее (продукт, ниша, актив).
  Идея/ниша без продукта — эта опция бриф-шаблона Марии здесь не
  подтверждена материалом исследования как типовой сценарий — не
  опровергнута, просто не встретилась ни в одном источнике; не заявляю её
  ни фактом, ни исключённым случаем.
- Существующий бренд-актив (голос/идентичность), если есть — вход для
  Positioning и Content Production, по прецеденту Мегаполис-модели,
  независимо подтверждён общей логикой Brand Strategy как persistent asset.
- Внешние сигналы рынка/конкурентов — вход для Positioning &amp; Category
  Definition (границы профессии, Направление 1).
- Данные о клиентах, если есть — вход для Audience Research (углубление, не
  обязательное условие для старта — Fishkin/SparkToro-метод явно работает
  и без внутренних данных, «где аудитория уже слушает»).

### Выходы — по каждой capability (не общий список, привязка к источнику)

| Capability | Выход (артефакт) | Подтверждено |
|---|---|---|
| Audience Research | Audience Profile / JTBD-инсайт | Направления 1-2 |
| Positioning &amp; Category Definition | Positioning Statement, категория | Направления 1-2 |
| Messaging &amp; Persuasion Design | Messaging Framework | Направление 2 |
| Offer &amp; Value Proposition Design | Value Proposition (статус выхода такой же неопределённый, как и статус capability) | слабо, Underdetermined |
| Brand Strategy &amp; Equity Management | Brand Identity/Asset (персистентный, не разовый) | Направление 2 |
| Content Production | Published Content | Направления 1-3 |
| Campaign/Journey Orchestration | Campaign Plan, Executed Touchpoints | Направление 3 |
| Growth Experimentation | Подтверждённые/опровергнутые гипотезы | Направление 2 |
| Go-to-Market/Distribution Strategy | Channel Mix Decision | ОТКРЫТО — состав выхода зависит от нерешённого вопроса |
| Measurement &amp; Reporting | Performance Signal/Report | Направление 3 |
| Marketing Effectiveness Review | Effectiveness Verdict | Направление 2 (Ritson) |

Шаблон Марии «ICP, сегменты» — ближе всего к Audience Profile (не отдельный
выход, входит в него). «KPI» как отдельная сущность — не встретился как
самостоятельный выход исследования, ближе всего к Performance Signal
(Measurement) — уточнение шаблона, не противоречие ему.

---

## Направление 6 — AI-декомпозиция

**Критерий уточнён (правка Марии, 2026-07-26).** Ценность capability
определяется Теорией+Практиками — это устойчивый факт, не зависит от
возможностей AI. AI-срез отвечает на отдельный вопрос: строить самим или
взять готовое — и это решение пересматривается по Capability Evolution
(событие — новая модель), не по календарю. Появление модели, которая
научится позиционированию, не отменяет саму Capability Positioning — только
повод пересмотреть, кто её исполняет.

**Ядро агента «Маркетолог» — четыре capability, не пять (правка Марии).**
Разные единицы анализа (Направление 1: клиент/job, категория, психологический
сдвиг, репутация во времени) и разные именные практики без пересечения
экспертизы (Направление 2: Данфорд не занимается измерением бренда, Шарп не
занимается JTBD) — не объединяются в одну capability:
- Audience Research
- Positioning &amp; Category Definition
- Messaging &amp; Persuasion Design
- Brand Strategy &amp; Equity Management

**Growth Experimentation исключена из ряда как пятая равная capability.**
Это метод, применяемый ко всем четырём выше — уже была названа
«горизонтальной» в Направлении 4, но ошибочно поставлена в один ряд с
остальными здесь же (нестыковка внутри этого же документа, не новая
находка, замечена по прямому вопросу Марии). По той же логике под вопросом
и Marketing Effectiveness Review — остаётся открытым пунктом, не решаю
здесь.

Режим — Advisory, не автономное исполнение — это не архитектурное
предпочтение AI_OS, а прямое отражение того, как уже ведёт себя рынок
(Направление 3, п.5): 32%/7% доверие, обязательное согласование в
Klaviyo/Blueshift.

**Skills внутри этого агента (не отдельные агенты — воспроизводимые
методики, см. Skills as Executable Knowledge в CLAUDE.md):**
конкретные фреймворки из Направления 2 — JTBD-интервью протоколы
(Ulwick/Moesta/Bourgoin), принципы Cialdini, стадии осведомлённости
Schwartz, Trigger Technique. Каждый — методика внутри соответствующей
Capability, не самостоятельная сущность.

**Внешняя Capability / не строить заново (Adopt before Build,
Content Production — единственный чистый Core, полностью коммодитизирован
рынком):**
- Content Production — независимо подтверждает уже существующее архитектурное
  решение Мегаполис (отдельный Content Production Agent, не слит с
  Маркетологом) — сходится с независимым выводом, не скопировано оттуда.

**Делегируется другому агенту (операционный/инфраструктурный слой,
AI-led/недотеоретизировано в матрице):**
- Campaign/Journey Orchestration, Measurement &amp; Reporting — рынком уже
  решены как операционная функция, не требуют суждения такого же уровня, как
  Research Gap-кластер. По прецеденту Мегаполис соответствует
  Distribution Agent / CRM-Retention Agent, не ядру Маркетолога — вывод
  получен независимо, не скопирован из прецедента.

**Растворена в ядро, не отдельный узел графа:**
- **Growth Experimentation** — метод, применяемый агентом к любой из четырёх
  ядровых capability, не пятая координатная способность (см. правку выше).

**Не классифицирую — открытые пункты, не закрываю эвристически:**
- **Go-to-Market/Distribution Strategy** — размещение (агент-ядро/делегирование
  вовне) зависит от нерешённого вопроса «одна способность или несколько»;
  решать до появления дополнительных данных нельзя.
- **Marketing Effectiveness Review** — функция найдена (Ritson), AI-покрытие
  нулевое, но статус (Capability vs Specialization vs governance-подобный
  слой по аналогии с Architecture Review в самой AI_OS) не решён. Возможная
  архитектурная гипотеза для будущей проверки, не решение сейчас: эта
  функция может не нуждаться в отдельном узле графа вообще, а реализовываться
  как периодическая проверка выходов агента «Маркетолог» — по тому же
  паттерну, что AI_OS уже применяет Architecture Review к себе. Отмечаю как
  ПРЕДПОЛАГАЕМ, не встраиваю в решение.
- **Offer &amp; Value Proposition Design** — Underdetermined на этапе матрицы,
  остаётся underdetermined и здесь: недостаточно оснований отнести ни к
  ядру, ни к делегированию.

---

## Итоговая Capability Map (сводка)

| Capability | Тип по матрице | AI-декомпозиция |
|---|---|---|
| Content Production | Core | Внешняя Capability (не строить) |
| Audience Research | Research Gap | Ядро агента, Advisory |
| Positioning &amp; Category Definition | Research Gap | Ядро агента, Advisory |
| Messaging &amp; Persuasion Design | Research Gap | Ядро агента, Advisory |
| Brand Strategy &amp; Equity Management | Research Gap | Ядро агента, Advisory |
| Growth Experimentation | Research Gap | Метод внутри ядра, не отдельный узел (правка Марии) |
| Campaign/Journey Orchestration | AI-led/недотеоретизировано | Делегируется (execution-агент) |
| Measurement &amp; Reporting | AI-led/недотеоретизировано | Делегируется (execution-агент) |
| Offer &amp; Value Proposition Design | Underdetermined | ОТКРЫТО |
| Go-to-Market/Distribution Strategy | (открыт состав) | ОТКРЫТО |
| Marketing Effectiveness Review | Specialization (формально, с напряжением) | ОТКРЫТО |

Два пункта остаются открытыми по прямому указанию — не эвристика, факт
недостаточности данных, дальнейшее решение требует либо дополнительного
исследования, либо решения Марии напрямую, не автоматического заполнения.

---

## Следующая фаза

Контракт ответственности верхнего AI и дальнейшее проектирование агента/SaaS
вынесены в отдельный документ — это уже проектирование системы, не
исследование профессии, разные типы знания, разные владельцы решения
(Марии — по правке 2026-07-26). См. `2026-07-26_marketer-agent-design.md`.

## См. также

`2026-07-26_marketer-agreement-matrix.md` ·
`2026-07-26_marketer-candidate-capabilities.md` ·
`2026-07-26_marketer-capability-knowledge-extraction.md` ·
`2026-07-26_marketer-agent-design.md` (следующая фаза — проектирование)
