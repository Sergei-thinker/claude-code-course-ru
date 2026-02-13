---
name: claude-code-course-ru
description: Русскоязычная адаптация интерактивного курса Claude Code для продакт-менеджеров
status: backlog
created: 2026-02-13T12:00:00Z
---

# PRD: claude-code-course-ru

## Executive Summary

Создать полную русскоязычную адаптацию курса Claude Code для продакт-менеджеров. Курс состоит из двух компонентов: сайт-справочник на docsify.js (GitHub Pages) и интерактивные обучающие материалы с slash-командами для Claude Code. Оригинал: https://github.com/Sergei-thinker/claude-code-pm-course (сайт: ccforpms.com).

## Problem Statement

Русскоязычные продакт-менеджеры не имеют структурированного курса по использованию Claude Code в своей работе. Оригинальный курс на английском недоступен для большинства русскоговорящей PM-аудитории. Адаптация включает не просто перевод, а локализацию контекста, примеров и персон.

## User Stories

### PM-новичок в AI
Как продакт-менеджер, впервые использующий AI-инструменты, я хочу пройти структурированный курс на русском языке, чтобы научиться использовать Claude Code для PRD, анализа данных и стратегии.

### Опытный PM
Как опытный PM, я хочу изучить продвинутые техники Claude Code (агенты, vibe coding, Nano Banana), чтобы ускорить свою работу и автоматизировать рутинные задачи.

## Requirements

### Functional Requirements

#### FR1: Сайт-справочник (docs/)
- Платформа: docsify.js + GitHub Pages
- Тема: dark theme (theme-simple-dark)
- Навигация: sidebar с 5 модулями
- Функции: поиск на русском, пагинация, copy-code
- Страницы: ~30 markdown-файлов

#### FR2: Интерактивные материалы (course-materials/)
- 22 обучающих скрипта (CLAUDE.md) на русском
- 22 slash-команды (/start-1-1 ... /start-4-5)
- 3 AI-агента (engineer, executive, user-researcher)
- Файлы упражнений: ~60+ (заметки, интервью, тикеты, шаблоны, CSV, фреймворки)
- course-structure.json — маршрутизация уроков

#### FR3: Контекст компании TaskFlow
- Адаптированные профили команды (русские имена)
- Адаптированные персоны (Ирина, Артём, Сергей)
- Сохранена бизнес-логика и SaaS-контекст

### Non-Functional Requirements

- Естественный русский язык, не машинный перевод
- PM-термины на английском (PRD, OKR, sprint, backlog, roadmap)
- Slash-команды на английском
- Имена файлов на английском, контент на русском

## Success Criteria

1. Все 30 страниц сайта доступны и отображаются корректно
2. Все 22 slash-команды запускают скрипты на русском
3. Русские имена консистентны во всех файлах
4. Все пути из course-structure.json ведут на существующие файлы
5. Поиск работает на русском языке
6. GitHub Pages сайт доступен публично

## Constraints & Assumptions

- Лицензия оригинала: CC BY-NC-ND 4.0 — нужно разрешение автора (Carl Vellotti)
- Оригинальный репо доступен для справки: ~/temp/claude-code-pm-course/
- Код (Python, bash) не переводится, только комментарии

## Out of Scope

- Видеоконтент
- Мобильное приложение
- CMS или бэкенд
- Перевод на другие языки
- Изменение структуры уроков оригинала

## Dependencies

- Оригинальный репо: https://github.com/Sergei-thinker/claude-code-pm-course
- docsify.js CDN
- GitHub Pages
- Прism.js для подсветки кода

## Implementation: Epics & Issues

### Epic 1: Скаффолдинг репозитория
- 1.1: Создать структуру директорий (docs/, course-materials/, lesson-modules/)
- 1.2: Настроить docsify (index.html) — dark theme, поиск, пагинация, copy-code
- 1.3: Создать _sidebar.md — навигация по всем модулям на русском
- 1.4: Создать README.md, .gitignore, LICENSE, .nojekyll
- 1.5: Создать docs/assets/css/custom.css — кастомные стили

### Epic 2: Контекст компании TaskFlow
- 2.1: Адаптировать COMPANY.md (русские имена, сохранена бизнес-логика)
- 2.2: Адаптировать PRODUCT.md (перевод + адаптация терминологии)
- 2.3: Адаптировать PERSONAS.md (Ирина, Артём, Сергей — полные профили)
- 2.4: Адаптировать COMPETITIVE.md (перевод анализа конкурентов)
- 2.5: Создать docs/company-context/ (4 зеркальные страницы для сайта)

### Epic 3: Инфраструктура курса
- 3.1: Перевести course-structure.json (все title/description на русском)
- 3.2: Перевести SCRIPT_INSTRUCTIONS.md (правила обучающих скриптов)
- 3.3: Создать 22 slash-команды (start-1-1 через start-4-5)
- 3.4: Перевести агента engineer.md
- 3.5: Перевести агента executive.md
- 3.6: Перевести агента user-researcher.md
- 3.7: Перевести PPTX skill

### Epic 4: Модуль 0 — Начало работы
- 4.1: docs/getting-started/introduction.md — введение в курс
- 4.2: docs/getting-started/installation.md — инструкция установки
- 4.3: docs/getting-started/start-and-clone.md — URL нового репо, инструкция запуска

### Epic 5: Модуль 1 — Основы (7 уроков)
- 5.1: Урок 1.1 Welcome — CLAUDE.md + docs/fundamentals/welcome.md
- 5.2: Урок 1.2 Visualizing Files — CLAUDE.md + 2 упражнения + docs page
- 5.3: Урок 1.3 First Tasks — CLAUDE.md + 15 файлов упражнений + docs page
- 5.4: Урок 1.4 Agents — CLAUDE.md + 31 файл упражнений + docs page
- 5.5: Урок 1.5 Custom Sub-agents — CLAUDE.md + 1 spec + docs page
- 5.6: Урок 1.6 Project Memory — CLAUDE.md + TASKFLOW_CLAUDE.md + docs page
- 5.7: Урок 1.7 Navigation — CLAUDE.md + docs page

### Epic 6: Модуль 2 — Продвинутая PM-работа (3 урока)
- 6.1: Урок 2.1 Write PRD — CLAUDE.md + templates + socratic + research + docs
- 6.2: Урок 2.2 Analyze Data — CLAUDE.md + CSV + framework + docs
- 6.3: Урок 2.3 Product Strategy — CLAUDE.md + frameworks + methods + docs

### Epic 7: Модуль 3 — Nano Banana (7 уроков + скрипты)
- 7.1: Урок 3.1.1 Welcome — CLAUDE.md + docs page
- 7.2: Урок 3.1.2 Basics — CLAUDE.md + docs page
- 7.3: Урок 3.1.3 Style — CLAUDE.md + reference images + docs page
- 7.4: Урок 3.1.4 Style Database — CLAUDE.md + style files + docs page
- 7.5: Урок 3.2.1 Users & Product — CLAUDE.md + docs page
- 7.6: Урок 3.2.2 Strategy & Architecture — CLAUDE.md + docs page
- 7.7: Урок 3.2.3 Marketing & Launch — CLAUDE.md + docs page
- 7.8: Скопировать Python-скрипты и изображения (image_gen.py, style_extract.py)

### Epic 8: Модуль 4 — Vibe Coding (5 уроков)
- 8.1: Урок 4.1 Setup — CLAUDE.md + docs page
- 8.2: Урок 4.2 Plan — CLAUDE.md + docs page
- 8.3: Урок 4.3 Build & Iterate — CLAUDE.md + docs page
- 8.4: Урок 4.4 GitHub — CLAUDE.md + docs page
- 8.5: Урок 4.5 Go Live — CLAUDE.md + docs page

### Epic 9: Дополнительные страницы
- 9.1: Главная страница docs/README.md — обзор курса, CTA, структура
- 9.2: Гид по Cowork docs/cowork.md — полный перевод гида
- 9.3: course-materials/README.md — инструкция запуска

### Epic 10: Развёртывание и проверка
- 10.1: Включить GitHub Pages (сайт доступен по URL)
- 10.2: Создать GitHub Release (zip с course-materials)
- 10.3: Проверка сайта (все ссылки, поиск, изображения, мобильная версия)
- 10.4: Проверка интерактива (/start-1-1 работает на русском)
