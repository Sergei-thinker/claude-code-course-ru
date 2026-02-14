# 4.4 GitHub

Прямо сейчас ваша викторина существует только на вашем компьютере.

Если ваш ноутбук перестанет работать или вы удалите файлы, она исчезнет. И мы пока не можем разместить её в интернете.

Нам нужно сначала сохранить её в облаке. Для этого и нужен GitHub.

STOP: Вы использовали GitHub раньше?

USER: Да / Нет / Немного

---

GitHub - это как Google Drive, но для кода.

Он сохраняет ваш код в облаке, ведёт историю каждого изменения и позволяет отменять ошибки.

Это также способ, которым мы разместим вашу викторину в интернете - сервису, который мы используем, нужно откуда-то взять ваш код.

Ваш проект на GitHub называется "репозиторий" (или "repo" сокращённо). Вы часто услышите, как разработчики используют это слово.

STOP: Понятно?

USER: Да

---

Сначала вам нужен аккаунт GitHub.

STOP: У вас есть аккаунт GitHub? Если нет, я могу открыть страницу регистрации для вас.

USER: У меня есть / Открой для меня / Я сделаю это сам

ACTION: If they want it opened, run: `open https://github.com` (or bash open on Mac)

STOP: Дайте мне знать, когда у вас будет аккаунт и вы готовы продолжить.

USER: Готов

---

Теперь мне нужно подключиться к вашему аккаунту GitHub, чтобы я мог сохранить там ваш код.

Я собираюсь загрузить некоторые инструменты, которые позволяют мне работать с GitHub напрямую - так что вам никогда не придётся вводить страшные команды.

Это может открыть ваш браузер для входа - просто следуйте подсказкам и возвращайтесь, когда это будет сделано.

ACTION: Set up GitHub CLI:

1. Check if already installed:
```
gh --version
```

2. If NOT installed:
   - On Mac: `brew install gh`
   - If brew fails or not on Mac: Tell user to go to https://cli.github.com and download manually, then come back

3. Once installed, authenticate (run in background to avoid blocking):
```bash
gh auth login --web --git-protocol https > /tmp/gh-auth.log 2>&1 &
sleep 2
cat /tmp/gh-auth.log
```

4. Read the output to get the one-time code, then open the device auth page:
```bash
open https://github.com/login/device
```

5. Tell user: "Я только что открыл страницу в вашем браузере. Введите этот код: [CODE FROM OUTPUT]. Нажмите Authorize, затем дайте мне знать, когда закончите."

STOP: Дайте мне знать, когда вы авторизовались.

USER: Готово

ACTION: Verify authentication worked:
```bash
gh auth status
```

If successful, continue. If not authenticated, troubleshoot:
- They may not have completed the browser flow - ask them to try again
- The background process may have timed out - run the auth command again

---

Теперь давайте сохраним ваш код в GitHub. Я сделаю его приватным по умолчанию, чтобы только вы могли его видеть.

ACTION: Run the following commands in order:

1. Navigate to the quiz-project folder:
```
cd [path to quiz-project]
```

2. Initialize git (if not already done):
```
git init
```

3. Add all files:
```
git add .
```

4. Create initial commit:
```
git commit -m "Initial commit - coffee personality quiz"
```

5. Create GitHub repo and push:
```
gh repo create quiz-project --private --source=. --push
```

Готово! Ваш код теперь сохранён в GitHub. Разработчики называют это "пушингом" вашего кода - вы "пушите" его в облако.

Позвольте мне открыть это для вас, чтобы вы могли увидеть.

ACTION: Get the repo URL and open it:
```
gh repo view --web
```
(This opens the GitHub repo in your browser)

STOP: Видите свой проект на GitHub?

USER: Да!

---

Ваша викторина теперь сохранена и готова к публикации.

Отныне, когда вы захотите сохранить свою работу, просто попросите меня "запушить в GitHub", и я сохраню ваши последние изменения.

В GitHub есть гораздо больше - совместная работа, история версий, ветвление - и в будущем будет полный модуль по этому поводу. Но пока важно то, что: ваш код живёт где-то, откуда к нему можно получить доступ, чтобы разместить в интернете.

Это именно то, что мы делаем дальше.

**Далее:** В 4.5 мы размещаем вашу викторину в интернете! Мы собираемся подключить GitHub к сервису под названием Vercel, и вы получите настоящий URL, которым можете поделиться с кем угодно. Это финишная прямая.

STOP: Готовы к публикации? Скажите "поехали" или введите /start-4-5

USER: Поехали

---

## Important Notes for Claude

- GitHub CLI (gh) is the easiest way to handle auth - avoid asking users to set up SSH keys
- The `--private` flag is important - users don't want their quiz code public by default
- If they already have a repo named quiz-project, gh will error - help them pick a different name
- The `gh repo view --web` command is much cleaner than trying to construct the URL
- If brew isn't available, cli.github.com has installers for all platforms
- Next.js projects already have a .gitignore so node_modules won't be committed

## Success Criteria

- User has a GitHub account
- GitHub CLI is installed and authenticated
- Code is committed and pushed to a private GitHub repository
- User can see their repo on github.com
- User understands they can ask to "push to GitHub" to save future changes
