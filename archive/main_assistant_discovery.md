---
Версия: 1.1
Дата: 2026-06-15
Тип: Discovery Summary
Статус: Архив — история создания MAIN_ASSISTANT, мигрированного в AI_OS (2026-07)
---

# MAIN_ASSISTANT_DISCOVERY
## История Architecture Discovery нового Level-1 сиблинга MAIN_ENGINEER

> Фиксация выводов Discovery-сессии перед созданием MAIN_ASSISTANT Stage S0. Не CORE, не постоянная память.

---

## 1. INITIAL PROBLEM

### Боль
Мария обозначила потребность в стратегическом AI-партнёре, сопровождающем её в жизни и бизнесе — параллельная MAIN_ENGINEER сущность: MAIN_ASSISTANT покрывает Личную жизнь, Здоровье, Финансы, Бизнесы, Идеи, Цели, Решения, Память.

### Первоначальные предположения
- MAIN_ASSISTANT нужна собственная отдельная память/база знаний
- Telegram-бот нужен с самого начала как интерфейс захвата
- Марию нужно "научить Obsidian" как программу
- MAIN_ASSISTANT строится сопоставимо мощным MAIN_ENGINEER с первого дня

### Что оказалось ошибочным
- ❌ Отдельная память → заменена на filesystem как Long-Term Memory
- ❌ Telegram сразу → вынесен в будущие этапы (не блокирует Computer Mode)
- ❌ "Учить Obsidian" → заменено на "Ассистент пишет в Obsidian, Мария разговаривает"
- ❌ Полноразмерная архитектура с первого дня → заменена на Stage S0 + один working loop

---

## 2. KEY ARCHITECTURAL DISCOVERIES

| Открытие | Суть |
|---|---|
| Level 1 sibling, не Level 2 агент | "Куда смотреть / на чём фокус" ≠ "как строить" — разные роды вопросов |
| Роль — Strategic Chief of Staff | Strategic Partner + Knowledge Manager: Capture → Organize → Connect → Distill → Retrieve |
| Follow Maria's Vision | ≈ Human Override Priority — финальное слово за Марией |
| Challenge with Evidence | ≈ Root Cause First + Intellectual Honesty + Routing Falsification, применённые к жизни/бизнесу |
| Role Boundary | Асимметричный доступ: MAIN_ASSISTANT читает registry.md MAIN_ENGINEER; обратного доступа нет |
| Distilled Inheritance | CORE — производное от мета-слоёв MAIN_ENGINEER_CORE, retargeted |
| Filesystem = Long-Term Memory | "Мария → Ассистент → файлы", не наоборот. Filesystem — библиотека за спиной ассистента |
| Computer Mode vs Mobile Mode | Два канала захвата: за компьютером (разговор) и в движении |
| Distill/Persist Gap vs Capture Gap | Computer Mode: Capture уже работает, разрыв — в Distill/Persist. Mobile Mode: разрыв в самом Capture |
| Telegram — будущий этап | Решает Mobile Capture Gap, не блокирует Stage S0 |
| Executive Layer ≠ PROJECT_STATE.md | Executive Layer — карта внимания CEO, а не статус одного проекта |

---

## 3. FAILED PATHS AND WHY REJECTED

| Путь | Почему отклонён |
|---|---|
| Полная 4-слойная memory-архитектура с первого дня | Simple Before Scalable — нечего организовывать без реального контента |
| DOMAINS/ создаются заранее | Single Responsibility + lazy creation — домены должны вырасти из реального INBOX, не быть угаданы |
| Перенос MAIN_ENGINEER в MARIA_OPERATING_SYSTEM сейчас | Stage-несоответствие: высокий blast radius ради выгоды, доступной позже бесплатно |
| Telegram-бот на Stage S0 | Решает Mobile Capture Gap, который не является текущим узким местом |
| "Научить Марию Obsidian" как предусловие | Барьер адопции — система, которой не будут пользоваться |

---

## 4. FINAL ARCHITECTURE DECISION

### Stage S0 структура

```
MAIN_ASSISTANT/
├── README.md
├── MAIN_ASSISTANT_CORE.md     ← хаб, Distilled Inheritance от MAIN_ENGINEER_CORE
├── MAIN_ASSISTANT_STATE.md    ← Executive Layer
└── DECISIONS/
    └── 2026-06-13_main_assistant_design.md
```

### Первый Working Loop

1. Мария ↔ MAIN_ASSISTANT — разговор (Computer Mode)
2. По команде "зафиксируй" — Distill в заметку с паспортом (DECISIONS/)
3. По запросу "покажи, что мы думали про X" — Retrieve из заметок

---

## 5. SUCCESS CRITERIA

### Первый Working Loop (S0) — механика Capture → Distill → Retrieve

- ✅ Мария регулярно (без напоминаний) выгружает мысли в разговоре
- ✅ Команда "зафиксируй" реально создаёт заметку, которую можно найти позже
- ✅ MAIN_ASSISTANT по запросу напоминает прошлые решения
- ✅ Executive Briefing (STATE.md) даёт ценность при просмотре — карта внимания, а не пустой шаблон

---

*MAIN_ASSISTANT_DISCOVERY v1.1 | История Discovery до Stage S0 | Архивировано при миграции в AI_OS 2026-07*
