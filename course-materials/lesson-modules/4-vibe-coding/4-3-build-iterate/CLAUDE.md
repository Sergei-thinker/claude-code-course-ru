# 4.3 Создание и итерация

Вот и всё. Время создать вашу викторину.

Я займусь всей технической настройкой. Вы просто наблюдайте за магией.

STOP: Готовы?

USER: Да

---

Сначала мне нужно настроить структуру проекта - это создаёт все стартовые файлы, которые нам нужны.

ACTION: Run the following command in the quiz-project folder:
```
npx create-next-app@latest . --typescript --tailwind --eslint --app --no-src-dir --import-alias "@/*" --yes
```
(The --yes flag accepts all defaults automatically)

Готово! Посмотрите в проводник файлов - вы должны увидеть кучу новых файлов в папке quiz-project.

Не беспокойтесь о понимании всех их. Папка `app/` - это где будет находиться ваша викторина. Всё остальное - просто конфигурация.

STOP: Видите новые файлы?

USER: Да

---

Прежде чем я создам, позвольте мне показать вам что-то полезное: режим планирования.

Для больших задач помогает увидеть, что я собираюсь делать, прежде чем я это сделаю. Нажмите **Shift+Tab**, чтобы переключить режимы - вы должны увидеть "Plan mode" как опцию.

STOP: Переключитесь в Plan mode и дайте мне знать, когда будете там.

USER: В режиме планирования

Отлично. Режим планирования означает, что я покажу вам свой план, вы его одобрите, затем я выполню. Давайте сделаем это.

STOP: Попросите меня создать викторину на основе требований.

USER: Создай мою викторину на основе REQUIREMENTS.md

ACTION: Read REQUIREMENTS.md, then create a plan showing:
- Components to create (quiz page, question component, results page)
- Styling approach based on their chosen style
- Quiz logic implementation (how answers map to results)
- Any images/icons to include

Present the plan clearly with bullet points.

Вот мой план. Я создам страницу викторины, компоненты вопросов, страницу результатов и стилизую всё в соответствии с вашими предпочтениями.

STOP: Это выглядит правильно? Есть вопросы перед тем, как я начну?

USER: Выглядит хорошо / [Вопросы]

ACTION: Answer any questions they have, then tell them to switch back to normal mode (Shift+Tab) and you'll execute the plan.

---

Создаю сейчас. Это занимает минуту или две. Вы увидите, как я создаю и редактирую файлы. Просто дайте мне работать.

ACTION: Build the full quiz application based on REQUIREMENTS.md:
1. Create the main quiz page in app/page.tsx
2. Create quiz components (QuizQuestion, Results, etc.)
3. Implement the quiz logic (tracking answers, calculating results)
4. Apply the visual style they chose
5. Add any images/icons based on their preference
6. Make sure the result display matches their choice (single vs percentages)

Take your time and build it properly. This is the core deliverable.

Готово! Ваша викторина создана. Теперь давайте посмотрим на неё в действии.

---

Я собираюсь запустить вашу викторину и открыть её в вашем браузере.

ACTION: Run `npm run dev` in background in the quiz-project folder

ACTION: Wait a few seconds for the server to start, then bash open http://localhost:3000 in browser

Ваша викторина теперь должна быть открыта в вашем браузере!

Эта ссылка "localhost" работает только на ВАШЕМ компьютере - это временная локальная версия. Мы сделаем её публичной позже, когда развернём.

STOP: Видите свою викторину?

USER: Да! / [Проблемы]

ACTION: If they have issues:
- Browser didn't open → Tell them to manually go to http://localhost:3000
- Build errors → Check the terminal output, fix errors
- Blank page → Check for JavaScript errors in browser console

---

Посмотрите на это! У вас есть работающая викторина!

Попробуйте её - ответьте на вопросы и посмотрите свой результат.

STOP: Попробуйте викторину. Она работает? Вы получаете результат в конце?

USER: Да, работает! / [Что-то не так]

ACTION: If something's wrong, debug together. Common issues:
- Result not showing → Check the logic implementation
- Wrong personality mapping → Review the answer mappings
- Style issues → Can fix in iteration

This is normal - first versions often need fixes. Let's get it working first, then polish.

Потрясающе! Вы только что создали веб-приложение. Дайте этому осознаться.

---

Первая версия никогда не бывает идеальной. Давайте итерируем - сделаем 2-3 изменения, пока вам не понравится.

Вот трюк: вы можете сделать скриншот, вставить его здесь с помощью **Ctrl+V** (не Cmd+V на Mac!), и сказать мне, что изменить.

Обведите что-то, укажите на это, что угодно - просто покажите мне, что вы хотите изменить.

Это также отличный способ показать мне баги. Если что-то выглядит неправильно, сделайте скриншот и вставьте его здесь.

Если вы не уверены, что изменить, вот несколько идей:
- Добавить конфетти или анимацию, когда вы получаете результат
- Изменить цвета или шрифты
- Подправить формулировки вопросов или результатов
- Добавить изображения для каждого результата
- Изменить макет или отступы
- Добавить прогресс-бар

STOP: Сделайте скриншот вашей викторины, вставьте его с помощью Ctrl+V и скажите мне, что бы вы хотели изменить.

USER: [Вставляет скриншот и описывает изменение]

ACTION: Make the requested change to the code

Готово! Обновите браузер, чтобы увидеть обновление.

STOP: Как это? Хотите изменить что-то ещё?

USER: [Больше изменений / Доволен этим]

ACTION: Keep iterating until they're satisfied. 2-3 rounds is typical. Common requests:
- Visual tweaks (colors, spacing, fonts)
- Animation additions
- Wording changes
- Layout adjustments

---

Посмотрите на это - это ВАША викторина, точно так, как вы хотите.

Это цикл итерации: скриншот → описание → изменение → обновление → повтор.

Так работает реальная разработка продуктов. И с AI каждая итерация занимает секунды вместо дней.

STOP: Довольны тем, как это выглядит?

USER: Да

---

**Что вы только что узнали:** Как перейти от требований к работающему продукту, затем итерировать, пока это не станет именно тем, что вы хотите.

**Где ещё это применимо:**
- Создание любого веб-проекта - посадочные страницы, инструменты, прототипы
- Быстрое тестирование идей перед инвестированием в "настоящую" разработку
- Работа с дизайнерами/разработчиками - чёткая визуальная обратная связь ускоряет всё

**Далее:** В 4.4 мы сохраняем ваш код в GitHub. Прямо сейчас он существует только на вашем компьютере. Мы собираемся поместить его в облако, чтобы он был сохранён и готов к развёртыванию.

STOP: Готовы сохранить свою работу? Скажите "давайте сделаем GitHub" или введите /start-4-4

USER: Давайте сделаем GitHub

---

## Important Notes for Claude

- The `npm run dev` command should run in background so the user can keep talking
- localhost:3000 is the default Next.js port - if something's already using it, Next.js will suggest another port
- When they paste screenshots, actually look at them and make specific changes
- The Ctrl+V note is important - Mac users often try Cmd+V first
- Keep iterations focused - don't suggest too many changes at once
- If the quiz has bugs, fix them before moving to visual polish
- Plan mode (Shift+Tab) is a real Claude Code feature - make sure they actually use it

## Success Criteria

- Next.js project is scaffolded in quiz-project folder
- Quiz is fully built based on REQUIREMENTS.md
- Dev server is running and quiz is viewable at localhost:3000
- User has done at least 1-2 iterations
- User is satisfied with how their quiz looks
- User is ready for GitHub
