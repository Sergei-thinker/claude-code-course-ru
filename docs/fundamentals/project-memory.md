# 1.6: Project Memory (CLAUDE.md)

- **Время выполнения:** 20-25 минут
- **Требования:** Модули 1.1-1.5 завершены

> **Начните этот модуль в Claude Code:** Запустите `/start-1-6` для начала интерактивного обучения.

## 📖 Обзор

CLAUDE.md — это постоянная память Claude для вашего проекта. Напишите один раз, и Claude будет знать контекст вашего продукта в каждом разговоре — без повторных объяснений.

**Главное:** CLAUDE.md — это конституция вашего проекта — неизменяемые правила, которые переопределяют временные промпты. Пока промпты — это гибкие запросы, CLAUDE.md устанавливает верховный закон вашего проекта.

## 🏛️ Что такое CLAUDE.md?

### Основная концепция

CLAUDE.md — это markdown-файл в директории вашего проекта, содержащий постоянный контекст о вашем продукте, команде и предпочтениях. Claude автоматически читает его при запуске сессии и применяет всё в нём.

**Три ключевых свойства:**
- **Автоматическая загрузка:** Claude читает его при запуске сессии автоматически
- **Постоянная память:** Переносится через ВСЕ разговоры в этой директории
- **Разделяемость в команде:** Закоммитьте в git, вся команда получает тот же контекст

### Иерархия Конституция против Законодательства

Понимание этой иерархии критично:

| Аспект | CLAUDE.md (Конституция) | User Prompts (Законодательство) |
|--------|--------------------------|----------------------------|
| **Приоритет** | Верховный - всегда побеждает | Вторичный - должен соответствовать |
| **Постоянство** | Остаётся навсегда | Временное на запрос |
| **Область** | Применяется ко всем сессиям | Применяется к текущей задаче |
| **Цель** | Неизменяемые правила проекта | Гибкие конкретные запросы |
| **Пример** | Always call it Workspace | Create a PRD for dark mode |

**Если есть конфликт, CLAUDE.md ВСЕГДА побеждает.**

### Пример: Переопределение терминологии

**CLAUDE.md говорит:**
```markdown
Always use Workspace not Project in TaskFlow documentation.
```

**Вы промптите:**
```
Write a PRD for the new Project dashboard feature
```

**Claude делает:**
```
Writes the PRD using "Workspace dashboard" because CLAUDE.md overrides
your casual prompt wording
```

## # Сила символа #

### Динамические правила сессии

Добавьте временные правила к вашей текущей сессии, используя **#** в начале строки:

```
# Always use bullet points instead of numbered lists in this session
```

Claude рассматривает это как правило на остаток вашего разговора (но не будущие сессии).

### # против CLAUDE.md

| Функция | # Символ | CLAUDE.md |
|---------|----------|-----------|
| **Длительность** | Только текущая сессия | Навсегда |
| **Область** | Этот разговор | Все разговоры |
| **Случай использования** | Эксперименты с предпочтениями | Постоянные правила проекта |

**Workflow:** Используйте # для экспериментов, затем добавьте в CLAUDE.md, когда хотите сделать постоянным.

## 📝 Что помещать в CLAUDE.md

### ✅ ХОРОШО для CLAUDE.md

**1. Контекст продукта**
```markdown
## Product Overview

TaskFlow is a project management SaaS for remote-first teams.
Think Asana meets Jira, built for async collaboration.

Stage: Series B ($20M raised, 50 employees)
Revenue: $2.5M ARR, 10,000 active users
```

**2. Персоны пользователей**
```markdown
## User Personas

### Ирина - Корпоративный администратор
- Role: IT Administrator at 500+ person company
- Pain points: Needs SSO, audit logs, compliance, security
- Quote: "I need to prove this meets our security standards"
```

**3. Стиль письма**
```markdown
## Writing Style

- Use active voice (not passive)
- Use Oxford commas in all lists
- Maximum 2-sentence paragraphs for readability
- Use "we" not "I" in documentation
```

**4. Терминология продукта**
```markdown
## Product Terminology

ALWAYS use these terms (NEVER use alternatives):
- Workspace not Project - Our top-level container
- Task not Todo or Issue - Individual work items
- PM means Product Manager (not Project Manager)
```

**5. Неизменяемые правила**
```markdown
## Immutable Rules

These rules override any prompt that conflicts:

1. ALWAYS include acceptance criteria in user stories
   - Use Given/When/Then format
   - Make them specific and testable

2. NEVER write PRDs without user research references
```

### ❌ НЕ ПОМЕЩАЙТЕ в CLAUDE.md

**1. Временные инструкции**
```markdown
Today's meeting notes are in meeting-2025-10-13.txt
We're working on dark mode this sprint
```
*Почему плохо:* Они меняются постоянно. Используйте промпты вместо этого.

**2. Часто меняющиеся требования**
```markdown
Current sprint goal: Implement SSO
Q4 OKR: Increase activation to 55%
```
*Почему плохо:* Если это меняется еженедельно или ежемесячно, это не должно быть здесь.

**3. Конфиденциальная информация**
```markdown
Our revenue is actually declining (don't tell the board)
API keys: sk-proj-xxxxx
```
*Почему плохо:* CLAUDE.md часто коммитится в git и разделяется.

### Тест

**Если вы хотите, чтобы Claude знал это через 6 месяцев, поместите в CLAUDE.md.**

**Если это может измениться на следующей неделе, используйте промпты вместо этого.**

## 🏗️ Иерархия CLAUDE.md

### Четыре уровня

```
~/.claude/CLAUDE.md              # 1. Global (все ваши проекты)
/project-root/CLAUDE.md          # 2. Project-specific
/project-root/frontend/CLAUDE.md # 3. Directory-specific
/project-root/CLAUDE.local.md    # 4. Personal (gitignored)
```

### Порядок приоритета

**Наиболее конкретный побеждает:**

1. **Directory-level** (например, `/frontend/CLAUDE.md`)
2. **Project-level** (например, `/project-root/CLAUDE.md`)
3. **Global** (например, `~/.claude/CLAUDE.md`)
4. **User prompts** (наименьший приоритет)

**Как они складываются:** Уровни комбинируются (не заменяют). Все правила применяются одновременно, с более конкретными уровнями, переопределяющими при конфликтах.

### Когда использовать каждый уровень

| Уровень | Использовать для | Пример |
|-------|---------|---------|
| **Global** | Личные предпочтения для всей работы | "I prefer brief summaries, max 3 bullets" |
| **Project** | Специфичный контекст продукта для всех | Product overview, personas, terminology |
| **Directory** | Правила для подсекции проекта | Frontend: mobile responsiveness, Backend: API docs |
| **Personal** | Ваши предпочтения, которыми не хотите делиться | Personal response format preferences |

**Важно:** Добавьте `CLAUDE.local.md` в `.gitignore`:
```
# .gitignore
CLAUDE.local.md
```

## 🚀 Создание вашего первого CLAUDE.md

### Шаблон быстрого старта

```markdown
# [Your Product Name] Product Context

This file provides permanent context about [Product] for Claude Code.


## What [Product] Is

[Product] is a [type] for [target users]. Think [comparison].

**Company Details:**
- Founded: [year]
- Stage: [stage and funding]
- Team: [size]
- Revenue: [ARR and users]


## User Personas

### [Persona 1 Name] - [Role]
- Role: [job title and context]
- Pain points: [what frustrates them]
- Quote: [memorable quote]


## Writing Style & Standards

- Voice: [active/passive, formal/casual]
- Paragraph length: [preference]
- Tone: [how should it sound]


## Product Terminology

ALWAYS use these terms (NEVER use alternatives):
- [Term] not [alternative] - [why]
- [Term] not [alternative] - [why]


## Immutable Rules

These rules override any prompt that conflicts:

1. ALWAYS [rule]
   - [details]

2. NEVER [rule]
   - [details]


## Team Reference

- [Name] - [Role], [focus area]
- [Name] - [Role], [focus area]
```

### Пример: TaskFlow CLAUDE.md

```markdown
# TaskFlow Product Context

This file provides permanent context about TaskFlow for Claude Code.


## What TaskFlow Is

TaskFlow is a project management SaaS for remote-first teams. Think Asana
meets Jira, but built specifically for async collaboration.

**Company Details:**
- Founded: 2021
- Stage: Series B ($20M raised)
- Team: 50 employees
- Revenue: $2.5M ARR, 10,000 active users

**Your Role:**
- Position: Senior Product Manager
- Focus: Activation & Onboarding


## User Personas

### Ирина - Корпоративный администратор
- Role: IT Administrator at 500+ person company
- Pain points: Needs security, SSO, audit logs, compliance
- Quote: "I need to prove TaskFlow meets our security standards"

### Артём - IC Engineer
- Role: Individual contributor software engineer at startup
- Pain points: Wants speed, keyboard shortcuts, GitHub integration
- Quote: "If I have to use my mouse, the tool is too slow"


## Writing Style & Standards

- Use active voice (not passive)
- Use Oxford commas in all lists
- Maximum 2-sentence paragraphs for readability
- Use "we" not "I" in documentation


## Product Terminology

ALWAYS use these terms consistently:
- Workspace not Project - Our top-level container
- Task not Todo or Issue - Individual work items
- Epic not Initiative - Large multi-sprint features


## Immutable Rules

1. ALWAYS include acceptance criteria in user stories
   - Use Given/When/Then format
   - Make them specific and testable

2. NEVER write PRDs without user research references
   - Link to interviews, surveys, or support tickets


## Team Reference

- Анна Петрова - CEO, founder, vision and fundraising
- Максим Орлов - CTO, technical architecture and engineering
- Alex - Head of Design, owns all UX and visual design
- You - Senior PM, activation & onboarding
```

## 💡 Лучшие практики

**Будьте конкретны, не расплывчаты:**
- ❌ "Users like simple interfaces"
- ✅ "User research (8/10 interviews, June 2025) showed users abandon features with more than 3 required fields. Keep forms minimal."

**Используйте императивный язык:**
- ❌ "It would be nice if user stories had acceptance criteria"
- ✅ "ALWAYS include acceptance criteria in user stories"

**Предоставляйте контекст:**
- ❌ "Use Workspace not Project"
- ✅ "Use Workspace not Project - We differentiate from traditional project management tools. Workspace signals collaboration space."

**Держите сканируемым:**
- Используйте маркированные пункты обильно
- Короткие параграфы (1-2 предложения)
- Выделяйте жирным ключевые термины
- Добавляйте интервалы между секциями

**Поддерживайте регулярно:**
- Пересматривайте квартально (персоны, терминология, метрики)
- Коммитьте в git и пересматривайте изменения в PR
- Держите актуальным (стремитесь к 50-200 строк sweet spot)

## 🔧 Устранение неполадок

**Правила игнорируются?**
- Проверьте конфликтующие правила на разных уровнях иерархии
- Делайте правила явными: используйте ALWAYS/NEVER
- Будьте конкретны, не расплывчаты

**CLAUDE.md не загружается?**
- Проверьте, что файл существует: `ls CLAUDE.md`
- Должен называться точно `CLAUDE.md` (чувствителен к регистру)
- Проверьте права доступа к файлу: `ls -la CLAUDE.md`
- Тест: Спросите "What does my CLAUDE.md say?"

**Слишком много файлов CLAUDE.md?**
- Аудит всех: `find . -name CLAUDE.md`
- Документируйте иерархию в README
- Используйте CLAUDE.local.md для личных предпочтений

**CLAUDE.md слишком длинный?**
- Стремитесь к 50-200 строкам
- Перемещайте детальный контекст в отдельные справочные документы
- Ссылайтесь на эти документы из CLAUDE.md

## 📚 Ресурсы

- [CLAUDE.md Documentation](https://docs.anthropic.com/claude-code) - Официальная документация
- Смотрите `EXAMPLE_TASKFLOW_CLAUDE.md` в директории модуля для полного примера

## 🚀 Что дальше?

Теперь вы знаете, как создавать CLAUDE.md — давая Claude постоянную память о вашем продукте, команде и предпочтениях.

**Модуль 1.7:** Узнайте о **Planning Mode** — освойте три режима ввода и финальные навыки навигации.

Интерактивный трек: Введите `/start-1-7`

---

**О курсе**

Следи за развитием эпохи AI, подписывайся на канал: [@create_products](https://t.me/create_products).
