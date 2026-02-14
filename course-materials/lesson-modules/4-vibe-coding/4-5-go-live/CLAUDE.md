# 4.5 Публикация

Вот и всё. Финальный шаг.

Ваша викторина создана, отполирована и сохранена в GitHub. Теперь мы размещаем её в интернете, чтобы любой мог посетить её.

Разработчики называют это "развёртыванием" - вы развёртываете своё приложение в интернете. Вы часто будете слышать это слово.

STOP: Готовы к публикации?

USER: Да

---

Vercel - это бесплатный сервис, который размещает ваш код в интернете.

Это в основном домашняя база vibecoding.

Вы даёте ему свой GitHub проект, и он превращает его в настоящий веб-сайт с настоящим URL.

Он создан теми же людьми, кто создаёт Next.js (фреймворк, который мы использовали), поэтому они работают вместе идеально.

STOP: Звучит хорошо?

USER: Да

---

Сначала вам нужен аккаунт Vercel.

STOP: Хотите, чтобы я открыл vercel.com для вас? Я рекомендую зарегистрироваться с вашим аккаунтом GitHub - это делает всё автоматически связанным.

USER: Да / Я сделаю это сам

ACTION: If they want it opened, run: `open https://vercel.com`

STOP: Дайте мне знать, когда вы создали аккаунт. Убедитесь, что зарегистрировались через GitHub!

USER: Готово

---

Как и с GitHub, я собираюсь загрузить инструменты, которые позволяют мне работать с Vercel напрямую.

Это откроет ваш браузер для входа - просто следуйте подсказкам.

ACTION: Set up Vercel CLI:

1. Check if already installed:
```
vercel --version
```

2. If NOT installed:
```
npm i -g vercel
```

3. Once installed, authenticate (run in background to avoid blocking):
```bash
vercel login > /tmp/vercel-auth.log 2>&1 &
sleep 3
cat /tmp/vercel-auth.log
```

4. Read the output to get the device URL with code, then open it:
```bash
open "https://vercel.com/oauth/device?user_code=[CODE FROM OUTPUT]"
```

5. Tell user: "Я только что открыл Vercel в вашем браузере. Нажмите Authorize, затем дайте мне знать, когда закончите."

STOP: Дайте мне знать, когда вы авторизовались.

USER: Готово

ACTION: Verify authentication worked:
```bash
vercel whoami
```

If successful, continue. If not authenticated, troubleshoot:
- They may not have completed the browser flow - ask them to try again
- The background process may have timed out - run the login command again

---

Теперь давайте разместим вашу викторину в интернете.

ACTION: Deploy to Vercel:

1. Navigate to the quiz-project folder:
```
cd [path to quiz-project]
```

2. Deploy to production:
```
vercel --prod --yes
```

The `--yes` flag accepts all the defaults so you don't have to answer questions. The `--prod` flag means it goes live immediately.

Wait for the deploy to complete - it takes about a minute. Watch for the URL in the output.

Vercel сейчас собирает вашу викторину и размещает её в интернете...

Готово! Ищите URL в выводе - он будет выглядеть примерно так: `quiz-project-abc123.vercel.app`.

---

Ваш URL: [Copy the URL from the deploy output]

Это ВАШ веб-сайт. В настоящем интернете. Любой может посетить его.

Позвольте мне открыть его для вас.

ACTION: Open the deployed URL in the browser using bash open

STOP: Видите свою викторину вживую в интернете?

USER: Да!

---

Откройте этот URL на вашем телефоне. Он должен работать и там - та же викторина, любое устройство.

STOP: Работает на вашем телефоне?

USER: Да!

---

Теперь настоящий тест: отправьте эту ссылку другу. Отправьте её кому-нибудь прямо сейчас. Когда они отреагируют, это ощущение запуска чего-то реального.

Давайте признаем, что только что произошло.

Вы создали настоящее веб-приложение. Вы разместили его в интернете. У вас есть URL, который работает на любом устройстве. Вы сделали это, не написав ни одной строчки кода самостоятельно.

Это vibecoding. Это будущее.

STOP: Как вы себя чувствуете?

USER: [Ответ]

---

Вот что вы теперь знаете:

**План** → Определитесь, что вы строите
**Создание** → Позвольте AI создать это
**Итерация** → Уточняйте, пока не будет правильно
**Сохранение** → Сохраните это в GitHub
**Публикация** → Разместите в интернете (развёртывание)

Это цикл. Вы можете создать что угодно с этим циклом.

STOP: Понятно?

USER: Да

---

Ещё одна вещь: что, если вы захотите обновить викторину позже?

Вот процесс: внесите изменения на вашем компьютере, попросите меня "запушить в GitHub", и Vercel автоматически обновит ваш живой веб-сайт.

Вот и всё. Vercel следит за вашим GitHub и автоматически развёртывает, когда вы пушите изменения. Магия.

STOP: Довольно круто, правда?

USER: Да

---

Что, если бы вы хотели собирать email от людей, которые проходят викторину? Вам бы понадобилась база данных для их сохранения. Это будущий модуль.

Что, если бы вы хотели убедиться, что она не сломается? Вам бы понадобилось тестирование. Тоже будущий модуль.

Что, если бы вы хотели кастомный домен типа вашавикторина.com? Абсолютно возможно - Vercel делает это легко.

Суть в том: у вас теперь есть фундамент. Всё остальное строится на этом.

STOP: Чувствуете себя сильнее?

USER: Да

---

Хотите создать что-то ещё? Начните новую папку проекта и следуйте этому же процессу.

Основные вещи, которые нужно сказать Claude: вы хотите развернуть на Vercel, и что у него есть доступ к Vercel CLI. Он будет знать, что делать.

STOP: Есть идеи, которые зреют?

USER: [Ответ]

---

## Краткие упоминания

**Чтобы узнать о будущих модулях:** Подпишитесь на рассылку Claude Code for PMs на ccforpms.com. Там же вы найдёте подробные руководства и сообщество PM, использующих Claude Code.

STOP: Хотите, чтобы я открыл этот сайт, чтобы вы могли подписаться?

USER: Да / Нет

ACTION: If yes, open https://ccforpms.com in browser

Этот курс создан Carl Vellotti. Если у вас есть отзывы, вопросы или вы просто хотите поздороваться, он всегда рад услышать от вас: [X](https://x.com/carlvellotti) / [LinkedIn](https://www.linkedin.com/in/carlvellotti/)

Если вам понравилось, поделитесь с друзьями и коллегами, которым могут пригодиться эти навыки!

---

**Модуль 4 завершён!**

Вы прошли путь от нуля до развёрнутого веб-приложения. Вы изучили планирование, создание, итерацию, GitHub и публикацию.

Это vibecoding. Это ваша новая суперсила.

**Что дальше:** Будущие модули будут охватывать базы данных, API, более сложные приложения и подключение Claude ко всему. Но теперь у вас есть основной навык - вы можете создавать и запускать вещи.

А пока попробуйте создать что-то для себя. Лучший способ учиться - это делать то, что вы действительно хотите.

STOP: Спасибо, что создавали со мной. Теперь идите и создайте что-нибудь крутое.

USER: (выходит или исследует)

---

## Important Notes for Claude

- The `vercel --prod --yes` flags are critical - `--yes` skips all interactive prompts, `--prod` deploys to production immediately
- Vercel auto-connects to the GitHub repo they created in 4.4 - this is why signing up with GitHub was important
- The URL format is usually `[project-name]-[random].vercel.app`
- Auto-deploy is set up automatically when they link GitHub during Vercel signup
- If deploy fails, common issues:
  - Build errors → Check the Vercel dashboard for logs
  - Not in the right directory → Make sure you're in quiz-project
- The celebration moment (sending to a friend) is crucial - let it breathe, don't rush past it

## Success Criteria

- User has a Vercel account (connected to GitHub)
- Vercel CLI is installed and authenticated
- Quiz is deployed and live on the internet
- User can access the quiz from their phone
- User has sent the link to at least one other person
- User understands the Plan → Build → Iterate → Save → Go Live loop
- User knows how to update: make changes → push to GitHub → auto-deploys
- User feels empowered to build more things
