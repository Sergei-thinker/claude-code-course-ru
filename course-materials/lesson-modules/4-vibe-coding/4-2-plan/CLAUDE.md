# 4.2 План

Прежде чем создавать, нам нужно понять, что мы создаём.

Это называется "требования" - в основном описание того, как ваша викторина должна работать и выглядеть.

STOP: Вам когда-нибудь приходилось давать кому-то расплывчатые инструкции и получать что-то совершенно иное, чем вы ожидали?

USER: Да / Определённо

---

Вот что происходит, когда вы пропускаете требования. Чем больше деталей мы выясним сейчас, тем лучше я смогу создать то, что вы действительно хотите.

Я проведу с вами интервью о вашей викторине. Мы выясним соответствия личности и кофе, стиль, вопросы. Затем я сохраню всё это в файл, чтобы у нас была чёткая спецификация для создания.

STOP: Думайте об этом как о брифинге подрядчика перед началом работы. Чем яснее бриф, тем лучше результат. Готовы начать?

USER: Да

---

Я собираюсь использовать инструмент под названием AskUserQuestion - он даёт вам красивые кнопки для выбора вместо набора текста. Вы можете попросить меня использовать это в любое время, когда захотите более удобный способ принятия решений. Просто скажите "спроси меня" или "дай мне варианты".

Давайте попробуем это сейчас.

ACTION: Use AskUserQuestion with two questions:
- Q1 Header: "Результаты" / Question: "Сколько пар личность/кофе должно быть в вашей викторине?" / Options: "3 - Просто и сфокусировано", "4 - Хорошее разнообразие (Рекомендуется)", "5 - Больше различий", "6 - Максимальное разнообразие"
- Q2 Header: "Стиль вопросов" / Question: "Какой стиль вопросов вы хотите?" / Options: "Весёлая поп-культура (Гарри Поттер, Netflix и т.д.)", "Образ жизни и предпочтения (путешествия, еда, выходные)", "Абстрактное и причудливое (цвета, сценарии, гипотетические)", "Микс всего"

USER: [Выбирает варианты]

Отличный выбор! Теперь давайте выберем ваши фактические пары личность-кофе.

---

Помните: викторина рекомендует КОФЕ на основе личности. Поэтому нам нужно решить, какие личности соответствуют каким напиткам.

Вот 10 идей пар. Выберите [X] на основе того, сколько результатов вы выбрали ранее. Просто введите номера, например "1, 4, 7":

1. **Смелый Авантюрист** → Двойной эспрессо - "Вы живёте ради интенсивности"
2. **Уютная Классика** → Средней обжарки дрип-кофе - "Комфорт в каждой чашке"
3. **Сладкий Энтузиаст** → Карамельный латте - "Жизнь слишком коротка для горечи"
4. **Дзен Минималист** → Чёрный кофе, моносорт - "Просто. Чисто. Совершенно."
5. **Социальная Бабочка** → Капучино - "Кофе лучше в компании"
6. **Ночная Сова** → Red Eye (кофе + порция эспрессо) - "Сон необязателен"
7. **Заботящийся о Здоровье** → Американо на овсяном молоке - "Здоровье в каждом глотке"
8. **Ремесленный Сноб** → Пуровер, моносорт - "Вы знаете, что вам нравится"
9. **Практичный Прагматик** → Большой дрип, что есть свежего - "Просто чтобы работало"
10. **Балующий себя Любитель Удовольствий** → Мокко со взбитыми сливками - "Кофе - это десерт"

STOP: Введите номера, которые хотите (например, "1, 3, 5, 8")

USER: [Вводит номера]

ACTION: Note their selections for use in REQUIREMENTS.md

---

Отлично! Теперь нам нужно выяснить "логику".

Логика - это закулисные правила того, как что-то работает. Если пользователи делают X, что происходит? Если они нажимают это, что они видят? Это "если это, то то" вашего продукта.

У каждого приложения, веб-сайта или инструмента есть логика. Когда вы что-то планируете, вам всегда нужно продумывать, как это должно фактически себя вести. Я могу помочь вам обдумать варианты.

Вот как будет работать эта викторина: каждый вопрос имеет ответы, и каждый ответ соответствует одной из ваших личностей. В конце мы подсчитываем, какая личность была выбрана чаще всего.

Вопрос в том: как мы показываем результат? Два варианта:

**Вариант A: Одна рекомендация** - "Вы Смелый Авантюрист! Попробуйте наш двойной эспрессо."

**Вариант B: Показать все проценты** - "Вы на 50% Смелый Авантюрист, на 30% Уютная Классика, на 20% Сладкий Энтузиаст" со всеми рекомендациями кофе.

STOP: Что вы предпочитаете - одну рекомендацию (A) или показать проценты (B)?

USER: [Отвечает A или B]

ACTION: Note their choice for REQUIREMENTS.md

Отличный выбор! Так что если чьи-то ответы соответствуют "Смелому Авантюристу" 3 раза и "Уютной Классике" 2 раза:

[If they chose A]: Они получают "Вы Смелый Авантюрист! Ваш кофе: Двойной эспрессо."

[If they chose B]: Они видят все свои результаты с процентами и могут изучить все рекомендации кофе.

Вопросы просто выявляют, какая личность подходит им лучше всего.

STOP: Понятно?

USER: Да

---

Теперь весёлая часть - как это должно ВЫГЛЯДЕТЬ?

Я собираюсь сгенерировать несколько разных визуальных стилей в виде предварительных страниц и открыть их в вашем браузере.

STOP: Готовы увидеть варианты стилей?

USER: Да

ACTION: Generate 3-4 HTML style preview files with different aesthetics:
- Style 1: Playful/colorful (bright colors, rounded shapes, fun fonts)
- Style 2: Minimal/clean (lots of whitespace, simple typography)
- Style 3: Bold/dramatic (dark backgrounds, high contrast, strong typography)
- Style 4: Warm/cozy (earth tones, soft gradients, inviting feel)

Each preview should show a sample quiz card with a question and answer options. Save them to the quiz-project folder as style-preview-1.html, style-preview-2.html, etc.

ACTION: Open all preview files in the browser using bash open commands

Взгляните на эти превью в вашем браузере. Каждая вкладка - это разный стиль.

STOP: Какой стиль вам больше всего нравится? Вы можете выбрать один или сказать мне, что смешать - например "Мне нравятся цвета из №2, но макет из №3"

USER: [Отвечает с предпочтением]

ACTION: Note their style preference. If they want to mix elements, clarify what specifically they want combined.

---

Ещё один визуальный вопрос: хотите ли вы изображения в викторине?

У вас могла бы быть картинка для каждого результата кофе - например, фото эспрессо для "Смелого Авантюриста".

Я могу искать в интернете и загружать изображения для вас - но учтите, это занимает немного времени, так как мне нужно искать, находить хорошие и загружать их.

Как альтернатива, мы можем пропустить изображения сейчас и добавить их позже, когда викторина будет работать.

STOP: Что вы предпочитаете - изображения (занимает дольше) или пропустить сейчас?

USER: [Отвечает]

ACTION: Based on their choice:

If they want IMAGES:
- Ask what images they want for each result (e.g., "espresso shot", "cozy latte", "iced coffee")
- For each image:
  1. Web search for the image (e.g., "espresso shot unsplash")
  2. Fetch a result page to find direct image URLs
  3. Download using curl to public/ folder in quiz-project
- Note: Unsplash is best for stock photos (free, high quality).

If they want to SKIP:
- Move on - can always add images later during iteration

---

Ещё одна вещь: хотите ли вы иконки рядом с каждым вариантом ответа? Например, маленький значок меча для "Гриффиндор" или луны для "Ночное зрение"?

Иконки делают викторину более отполированной и визуальной, но мы также можем сохранить только текст, если вы предпочитаете более чистый вид.

STOP: Иконки или без иконок?

USER: [Отвечает]

ACTION: Note their choice for REQUIREMENTS.md

---

Последняя часть - фактические вопросы, на которые люди будут отвечать.

Вы выбрали стиль вопросов "[их выбор стиля вопросов ранее]", поэтому я сгенерирую 5-7 вопросов, которые соответствуют этому стилю. Каждый вопрос будет иметь ответы, которые соответствуют вашим различным личностям.

Конечно, вы также можете придумать свои собственные вопросы - просто скажите мне, что вы хотите, и я это сделаю.

ACTION: Generate 5-7 quiz questions matching their vibe choice:
- If "Весёлая поп-культура": Harry Potter houses, Netflix shows, fictional characters, movie genres, etc.
- If "Образ жизни и предпочтения": weekend activities, travel styles, food choices, social preferences, etc.
- If "Абстрактное и причудливое": colors, hypothetical scenarios, random objects, desert island choices, etc.
- If "Микс всего": 2-3 from each category

Each question should have answers that clearly map to the personalities they selected. For example, if they picked Bold Adventurer and Cozy Classic, answers should lean toward intensity vs. comfort.

Вот мои предложения. Взгляните - каждый ответ разработан так, чтобы соответствовать одной из ваших личностей.

STOP: Что думаете? Хорошо как есть, хотите изменений или хотите написать свои собственные?

USER: [Одобряет или предлагает изменения]

ACTION: Adjust questions based on feedback. If they want to write their own, help them map answers to personalities.

---

Отлично! У нас есть всё, что нужно. Позвольте мне сохранить всё это в файл требований.

ACTION: Create REQUIREMENTS.md in the quiz-project folder with:
- Personality→Coffee pairings (all selected ones with taglines)
- Result display style (single or percentages)
- Visual style description
- Image/icon decision
- All quiz questions with answer-to-personality mappings

Готово! Откройте REQUIREMENTS.md и взгляните. Это спецификация, по которой я буду создавать.

STOP: Всё выглядит правильно?

USER: Да / [Исправления]

ACTION: Make any corrections if needed

---

**Что вы только что узнали:** Как определить чёткие требования перед созданием - конкретно для движка рекомендаций.

**Где ещё это применимо:**
- Брифинг дизайнера или разработчика по любому проекту
- Написание спецификации продукта или PRD
- Планирование любого творческого проекта - чем яснее видение, тем лучше результат
- Работа с AI инструментами - чем вы конкретнее, тем лучше результат

**Далее:** В 4.3 мы действительно СОЗДАЁМ эту штуку. Вы посмотрите, как я создаю вашу викторину с нуля на основе этих требований. Здесь происходит магия.

STOP: Готовы к 4.3? Скажите "давайте создавать" или введите /start-4-3

USER: Давайте создавать

---

## Important Notes for Claude

- The AskUserQuestion tool should be used for the initial batched questions ONLY - after that, use regular conversation
- When generating style previews, make them actually visually distinct - don't just change colors slightly
- For images: Unsplash works great for stock photos, but always check the URL actually returns an image before downloading
- The REQUIREMENTS.md file is crucial - it's the spec for 4.3. Make sure it's complete and clear.
- If users want to mix styles, get specific about what elements from each
- Adjust the number of questions based on their pairing count (more pairings = more questions needed to differentiate)

## Success Criteria

- User has selected their personality→coffee pairings
- User has chosen result display style (single vs percentages)
- User has selected a visual style
- User has made a decision on images/icons/skip
- User has approved quiz questions
- REQUIREMENTS.md exists with all the above documented
- User is excited to build
