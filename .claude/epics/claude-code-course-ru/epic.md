---
name: claude-code-course-ru
status: backlog
created: 2026-02-13T12:00:00Z
progress: 0%
prd: .claude/prds/claude-code-course-ru.md
github: [Will be updated when synced to GitHub]
---

# Epic: claude-code-course-ru

## Overview

Русскоязычная адаптация интерактивного курса Claude Code для продакт-менеджеров. Два компонента: сайт-справочник (docsify.js + GitHub Pages) и интерактивные обучающие материалы (slash-команды + CLAUDE.md скрипты). Оригинал: https://github.com/Sergei-thinker/claude-code-pm-course

## Architecture Decisions

- **Сайт**: docsify.js (без сборки, чистый markdown) + GitHub Pages
- **Тема**: theme-simple-dark
- **Структура**: docs/ (сайт) + course-materials/ (интерактив)
- **Перевод**: Естественный русский, PM-термины на английском
- **Контекст**: Адаптированный TaskFlow (русские имена)

## Technical Approach

### Сайт (docs/)
- index.html с docsify конфигурацией
- _sidebar.md — навигация на русском
- ~30 markdown-страниц по модулям
- Поиск, пагинация, copy-code плагины

### Интерактив (course-materials/)
- course-structure.json — маршрутизация
- 22 CLAUDE.md обучающих скрипта
- 22 slash-команды (/start-1-1 ... /start-4-5)
- 3 AI-агента (engineer, executive, user-researcher)
- ~60+ файлов упражнений

### Контекст компании
- COMPANY.md, PRODUCT.md, PERSONAS.md, COMPETITIVE.md
- Адаптированные русские имена и персоны

## Implementation Strategy

1. Скаффолдинг (структура, docsify, sidebar)
2. Контекст компании (4 файла)
3. Инфраструктура курса (commands, agents, course-structure)
4. Модули 0-4 (сайт + скрипты)
5. Дополнительные страницы
6. Развёртывание и проверка

## Dependencies

- Оригинальный репо: ~/temp/claude-code-pm-course/
- docsify.js CDN
- GitHub Pages
- gh CLI для синхронизации

## Success Criteria (Technical)

- Все файлы из course-structure.json существуют
- Все ссылки в sidebar ведут на существующие страницы
- Русские имена консистентны во всех файлах
- GitHub Pages сайт доступен публично
- /start-1-1 запускает скрипт на русском
