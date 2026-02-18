# 1.3: Ваши первые задачи PM

- **Время выполнения:** 30 минут
- **Требования:** Модули 1.1 и 1.2 завершены

> **Начните этот модуль в Claude Code:** Запустите `/start-1-3` для начала интерактивного обучения.

## Обзор

Модуль 1.3 учит вас использовать Claude Code для реальной PM-работы: обработка заметок встреч, синтез исследований, анализ визуального контента и создание переиспользуемых шаблонов. Здесь теория становится практикой.

**Главное:** Claude Code — это файл-ориентированный, визуально способный ассистент, который может экономить вам 2-3 часа в неделю на рутинных PM-документационных задачах.

## Базовые возможности

Этот модуль охватывает пять основных навыков:

| Возможность | Чему вы научитесь |
|------------|-------------------|
| **Чтение/запись файлов** | Ссылаться на файлы с помощью `@`, читать несколько документов, создавать/редактировать файлы |
| **Анализ контента** | Превращать заметки в action items, синтезировать исследования, извлекать паттерны |
| **Вставка изображений** | Вставлять скриншоты прямо в терминал с помощью Ctrl+V (все платформы) |
| **Визуальный анализ** | Получать отзывы о макетах, анализировать конкурентов, проверять визуализации данных |
| **Стили вывода** | Создавать переиспользуемые шаблоны форматирования для повторяющихся типов документов |

## Символ @ - Система ссылок на файлы

Символ `@` говорит Claude, какие файлы читать, анализировать или на которые ссылаться.

### Базовый синтаксис

```
Read @meeting-notes.txt and summarize action items
```

```
Compare @competitor-a.md and @competitor-b.md
```

```
Analyze @research/interviews/user-01.txt
```

### Поддерживаемые типы файлов

| Формат | Расширения | Обычное использование |
|--------|-----------|-------------|
| Markdown | `.md` | PRD, документация, заметки |
| Text | `.txt` | Заметки встреч, сырые данные |
| CSV | `.csv` | Результаты опросов, метрики |
| JSON | `.json` | Ответы API, структурированные данные |
| PDF | `.pdf` | Исследовательские статьи, отчёты |
| Изображения | `.png`, `.jpg`, `.gif` | Скриншоты, макеты |

### Работа с несколькими файлами

**Обработка пакета файлов:**
```
Read all files in /meetings/ and extract action items
```

**Перекрёстные ссылки на документы:**
```
Read @prd.md and @user-research.md.
Identify gaps where the PRD doesn't address user pain points.
```

**Синтез из нескольких источников:**
```
Read all files in /interviews/ and create @research-synthesis.md with:
- Top 5 pain points
- Common feature requests
- User personas
```

## Вставка изображений - Критически важная комбинация клавиш

### Универсальная команда: Ctrl+V

**КРИТИЧЕСКИ ВАЖНО: Используйте Ctrl+V на ВСЕХ платформах, включая Mac**

| Платформа | Правильно | Неправильно |
|----------|---------|-------|
| Mac | **Ctrl+V** | Command+V |
| Windows | **Ctrl+V** | - |
| Linux | **Ctrl+V** | - |

**Почему Mac отличается?** В терминалах `Ctrl+V` универсален для всех ОС. `Command+V` — это вставка GUI в Mac и не работает в терминальных окружениях.

### Как вставлять изображения

1. **Скопируйте изображение в буфер обмена**
   - Скриншот: `Cmd+Shift+4` (Mac) или `Win+Shift+S` (Windows)
   - Копировать из браузера/Figma: `Cmd+C` (Mac) или `Ctrl+C` (Windows)

2. **Вставьте в Claude Code**
   - Нажмите **Ctrl+V** в терминале
   - Изображение появится в разговоре

3. **Запросите анализ**
   ```
   Analyze this mockup and provide:
   - UX feedback from PM perspective
   - Technical challenges
   - Accessibility concerns
   - Missing user flow elements
   ```

### Что можно вставлять

| Категория | Примеры |
|----------|----------|
| **Дизайн и продукт** | Макеты Figma, wireframes, user journeys |
| **Данные и аналитика** | Скриншоты дашбордов, графики, метрики |
| **Конкурентные исследования** | Скриншоты конкурентов, pricing pages |
| **Коллаборация** | Фото досок, диаграммы встреч |
| **Техническое** | Сообщения об ошибках, архитектурные диаграммы |

## Трансформация контента

Базовый навык PM — коммуницировать одну и ту же информацию для разных аудиторий.

### Матрица коммуникации

| Аудитория | Формат | Тон | Фокус |
|----------|--------|------|-------|
| Разработка | Slack | Неформальный, технический | Детали реализации |
| Стейкхолдеры | Email | Профессиональный, стратегический | Бизнес-результаты |
| Клиенты | Release notes | Дружественный, ориентированный на выгоды | Доставленная ценность |
| Документация | Notion doc | Всеобъемлющий, структурированный | Полный справочник |
| Руководители | Brief | Краткий, метрико-ориентированный | Влияние и следующие шаги |

### Пример: Мультиформатная коммуникация

```
Read @sprint-planning-notes.txt and create:
1. @slack-update.md - Casual team announcement
2. @stakeholder-email.md - Professional executive summary
3. @notion-doc.md - Complete reference documentation
```

## Стили вывода - Переиспользуемые шаблоны

Стили вывода — это шаблоны форматирования, которые устраняют повторяющиеся объяснения форматирования.

### Создание стиля вывода

**Метод 1: Определите формат**
```
Create output style Executive Briefing with:
- Maximum 3 paragraphs
- Paragraph 1: What happened (outcomes, metrics)
- Paragraph 2: Why it matters (business impact)
- Paragraph 3: What's next (forward-looking)
- Use bullet points for metrics
- No jargon, active voice
```

**Метод 2: Покажите пример**
```
Create output style User Story formatted like:

**As a** [persona]
**I want** [capability]
**So that** [benefit]

**Acceptance Criteria:**
- Given [context]
  When [action]
  Then [outcome]
```

### Использование стилей вывода

```
Convert @meeting-notes.txt to Executive Briefing style
```

```
Format @sprint-work.md as Weekly Update style
```

### Основные PM-стили вывода

Создайте свою библиотеку с этими форматами:

1. **Executive Briefing** - Стратегическая сводка из 3 параграфов
2. **User Story** - As a/I want/So that с acceptance criteria
3. **Linear/Jira Issue** - Заголовок, описание, AC, приоритет, оценка
4. **Weekly Update** - Shipped/In Progress/Blocked/Next Week
5. **Release Notes** - Ориентированные на клиента, фокус на выгодах
6. **PRD Section** - Problem/Solution/Metrics/Stories
7. **Slack Announcement** - Неформальный, emoji-дружественный
8. **Stakeholder Email** - Профессиональный, с контекстом

## Реальные PM-workflow

### Обработка встреч (Еженедельно)

**Без Claude Code:** 35 минут
- Просмотр заметок: 10 мин
- Извлечение action items: 15 мин
- Организация по владельцам: 5 мин
- Форматирование для распространения: 5 мин

**С Claude Code:** 2 минуты
```
Process all files in /meetings/today/ and create @action-items-summary.md with:
- Table of action items organized by owner
- Priority and due date
- Grouped by meeting source
```

**Сэкономленное время:** 33 мин/неделю = 2.75 часа/месяц

### Синтез user research

**Без Claude Code:** 2 часа 40 минут
- Прочитать 8 транскриптов: 60 мин
- Выделить темы: 30 мин
- Извлечь цитаты: 20 мин
- Организовать находки: 20 мин
- Написать синтез: 30 мин

**С Claude Code:** 5 минут
```
Read all files in /user-interviews/ and create @research-synthesis.md with:
- Top 5 pain points (mentioned by 3+ users)
- Supporting quotes for each finding
- Feature requests ranked by frequency
- Refined personas with real data
- Recommended next steps
```

**Сэкономленное время:** 2.5 часа за цикл исследования

### Коммуникация со стейкхолдерами

**Без Claude Code:** 45 минут
- Набросок сообщения в Slack: 10 мин
- Написать email стейкхолдеру: 15 мин
- Создать Notion doc: 15 мин
- Обеспечить согласованность: 5 мин

**С Claude Code:** 3 минуты
```
Read @product-sync-notes.md and create three formats:

1. Slack Update - Casual, emoji-friendly, celebrate wins
2. Stakeholder Email - Business outcomes, metrics, risks
3. Notion Document - Complete reference with dependencies
```

**Сэкономленное время:** 42 мин/спринт = 1.4 часа/месяц

## Лучшие практики

### Делайте:

**Используйте @ ссылки явно**
```
Good: Read @user-research.md and summarize pain points
Better: Read @user-research.md and create @pain-points-summary.md
```

**Запрашивайте структурированный вывод**
```
Create table with: Action Item | Owner | Due Date | Priority
```

**Предоставляйте контекст для анализа**
```
We're deciding between Feature A and B for Q2.
Read @user-research.md and recommend which addresses more critical pain points.
```

**Комбинируйте несколько операций**
```
Read all /interviews/, synthesize findings, create @executive-summary.md and @detailed-insights.md
```

**Создавайте библиотеку стилей вывода постепенно**
- Создавайте стили по мере возникновения повторяющихся потребностей
- Не создавайте все сразу

### Не делайте:

**Не забывайте символ @**
```
Bad: Summarize meeting-notes.txt
Good: Summarize @meeting-notes.txt
```

**Не используйте Command+V на Mac**
- Всегда используйте Ctrl+V для изображений (все платформы)

**Не ожидайте, что Claude запомнит несохранённую работу**
- Сохраняйте файлы с именами для последующих ссылок

**Не вставляйте конфиденциальную информацию**
- Сначала редактируйте конфиденциальные данные из скриншотов

**Не создавайте слишком сложные стили**
- Держите простым и сфокусированным
- Лучше: 10 простых стилей, чем 1 сложный

## Устранение неполадок

**Command+V не работает на Mac**
- Решение: Используйте **Ctrl+V** вместо этого
- Почему: Терминалы используют Ctrl-комбинации на всех платформах

**Claude не может найти указанный файл**
- Проверьте орфографию имени файла (чувствительно к регистру)
- Проверьте путь к файлу: `What files are in /meetings/?`
- Спросите Claude: `Does @meeting-notes.txt exist?`

**Изображение вставлено, но нет анализа**
- Проверьте, что изображение появилось в разговоре
- Попробуйте другой формат (.png или .jpg)
- Проверьте размер (держите менее 10MB)
- Вставьте заново с Ctrl+V

**Стиль вывода форматирует неправильно**
- Покажите конкретный пример желаемого формата
- Будьте конкретны в структуре
- Тестируйте и уточняйте итеративно
- Начните с простого, добавляйте сложность постепенно

**Файл создан, но не виден в Obsidian**
- Обновите Obsidian
- Проверьте, что он не в скрытой папке .claude/
- Посмотрите в Finder/Explorer
- Спросите Claude: `Where did you save the file?`

## Что дальше?

**Модуль 1.4: Агенты для параллельной работы**

Научитесь клонировать Claude для одновременных задач:
- Обрабатывать 10 заметок встреч параллельно
- Исследовать 5 конкурентов одновременно
- Строить мультиагентные workflow
- Делать 5 часов работы за 30 минут

Интерактивный трек: Введите `/start-1-4`

## Быстрая справка

**Основные команды:**
- `@filename` - Ссылка на файл
- `Ctrl+V` - Вставить изображение (все платформы)
- `Read @file and create @output` - Базовый workflow

**Операции с файлами:**
```
Один: @meeting-notes.txt
Несколько: @file1.txt, @file2.txt, @file3.txt
Папка: All files in /meetings/
```

**Трансформация контента:**
```
Transform @source.txt into:
1. @casual-slack.md - Team-friendly
2. @formal-email.md - Stakeholder-appropriate
3. @comprehensive-doc.md - Complete reference
```

**Стили вывода:**
```
Create: Create output style [Name] with rules: [format]
Use: Format @content.txt in [Name] style
```

**Анализ изображений:**
1. Скопируйте изображение (Cmd+Shift+4 / Win+Shift+S)
2. Вставьте с Ctrl+V
3. Запросите анализ

## Ресурсы

Практикуйте эти workflow во время интерактивного модуля (`/start-1-3`) для выработки мышечной памяти на ссылки на файлы, вставку изображений и стили вывода.

---

**О курсе**

Следи за развитием эпохи AI, подписывайся на канал: [@create_products](https://t.me/create_products).
