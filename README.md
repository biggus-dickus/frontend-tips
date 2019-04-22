# Советы по верстке, или как делать хорошо сразу

Помимо основной работы, я наставничаю на интенсивах HTML Академии по верстке ([базовом](https://htmlacademy.ru/intensive/htmlcss) и [продвинутом](https://htmlacademy.ru/intensive/adaptive)). Из раза в раз многие мои студенты совершают одни и те же оплошности, которые потом приходится разбирать на код-ревью и консультациях. Поскольку мне порядком надоело говорить об одном и том же, я решил создать небольшое руководство, где будут описаны самые частые из них, приведены примеры кода, даны советы по наиболее удачному разрешению типовых интерфейсных задач и собраны ссылки на подробное описание разбираемой проблемы.

Что-то нижеописанного может показаться несущественным или даже пустяшным, но как раз эти пустяки в своей массе становятся причиной более серьезных проблем. Из личного опыта отмечу, что именно версточные &laquo;косяки&raquo; активнее всего пожирают время фронтенд-разработчика. А жизнь слишком коротка и быстротечна, чтобы растрачивать ее на написание костылей.

Уверен, что помимо новичков, определенную пользу из этого текста вынесут и т. н. фулл-стэки, особенно если их представления о верстке застряли на уровне 3-го Бутстрапа, флоатов или не дай б-г фреймов и таблиц. В конце концов, от продуманного, доступного, качественно сверстанного (и как следствие&nbsp;— красивого) интерфейса выигрывают как пользователи, так и разработчики. Первым он помогает решать свои задачи быстрее и удобнее, а вторым&nbsp;— разрабатывать, внедрять и поддерживать функционал с минимумом трудозатрат и стресса.

##### Содержание
* **Разметка и стилизация**
  * [Так кнопка или ссылка?](#%D1%82%D0%B0%D0%BA-%D0%BA%D0%BD%D0%BE%D0%BF%D0%BA%D0%B0-%D0%B8%D0%BB%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0)
  * [Следите, чтобы документы не ссылались сами на себя, и учитывайте это в CSS](#%D1%81%D0%BB%D0%B5%D0%B4%D0%B8%D1%82%D0%B5-%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-%D0%BD%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%B0%D0%BB%D0%B8%D1%81%D1%8C-%D1%81%D0%B0%D0%BC%D0%B8-%D0%BD%D0%B0-%D1%81%D0%B5%D0%B1%D1%8F-%D0%B8-%D1%83%D1%87%D0%B8%D1%82%D1%8B%D0%B2%D0%B0%D0%B9%D1%82%D0%B5-%D1%8D%D1%82%D0%BE-%D0%B2-css)
* **Типографика**
  * [Не пишите высоту строки в пикселях](#%D0%BD%D0%B5-%D0%BF%D0%B8%D1%88%D0%B8%D1%82%D0%B5-%D0%B2%D1%8B%D1%81%D0%BE%D1%82%D1%83-%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8-%D0%B2-%D0%BF%D0%B8%D0%BA%D1%81%D0%B5%D0%BB%D1%8F%D1%85)
* **Практические советы**
  * [Не привязывайте CSS-правила к HTML-селекторам и их расположению в документе](#%D0%BD%D0%B5-%D0%BF%D1%80%D0%B8%D0%B2%D1%8F%D0%B7%D1%8B%D0%B2%D0%B0%D0%B9%D1%82%D0%B5-css-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA-html-%D1%81%D0%B5%D0%BB%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0%D0%BC-%D0%B8-%D0%B8%D1%85-%D1%80%D0%B0%D1%81%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8E-%D0%B2-%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B5)
  * [Избегайте чрезмерных обобщений, собирайте макет как конструктор](#%D0%B8%D0%B7%D0%B1%D0%B5%D0%B3%D0%B0%D0%B9%D1%82%D0%B5-%D1%87%D1%80%D0%B5%D0%B7%D0%BC%D0%B5%D1%80%D0%BD%D1%8B%D1%85-%D0%BE%D0%B1%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9-%D1%81%D0%BE%D0%B1%D0%B8%D1%80%D0%B0%D0%B9%D1%82%D0%B5-%D0%BC%D0%B0%D0%BA%D0%B5%D1%82-%D0%BA%D0%B0%D0%BA-%D0%BA%D0%BE%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D0%BE%D1%80)
  * [Не используйте настройки Автопрефиксера по умолчанию](#%D0%BD%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B0%D0%B2%D1%82%D0%BE%D0%BF%D1%80%D0%B5%D1%84%D0%B8%D0%BA%D1%81%D0%B5%D1%80%D0%B0-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E)

## Разметка

### Так кнопка или ссылка?

Тут всё просто: ссылка, которая никуда не ведет, является кнопкой.

Ваша задача как верстальщика&nbsp;— обеспечить идентичность отображения вне зависимости от используемых тэгов в разметке. Сделать, чтобы кнопка выглядела как ссылка, [достаточно просто](https://codepen.io/code_monkey/pen/yrqRMg).

<h3 id="self-linking">Следите, чтобы документы не ссылались сами на себя, и учитывайте это в CSS</h3>

**В чем профит:** рациональность и здравый смысл. Зачем повторно грузить страницу, которая загружена и так?

*Исключение:* there are no exceptions to rule 34.

Один из основных законов ориентирования в вебе и гипертекстовой навигации&nbsp;— ничто не должно содержать ссылку на само себя. Самый простой способ этого добиться&nbsp;— убирать хреф-атрибуты у текущих навигационных ссылок (меню, хлебные крошки, пагинация и т. п.). Но! При этом не следует забывать, что данное правило нужно учитывать и при стилизации. **У текущих навигационных элементов не должно быть вообще никаких визуальных подсказок,** что с ними можно как-то взаимодействовать (наведение, нажатие, фокус). Ведь у ссылки нет хреф-атрибута, по ней никуда не перейдешь, тогда зачем вводить пользователя в заблуждение будто бы этот элемент интерактивен?

Простой способ это реализовать без лишних переопределений и раздувания кода:

```
/* Ссылка с классом `.nav-link` будет иметь состояния при наведении и нажатии только если у нее есть хреф-атрибут. */
.nav-link[href]:hover {
 ...
}

.nav-link[href]:active {
 ...
}
```

[Интерактивная демонстрация](https://codepen.io/code_monkey/pen/gqzxRa)

## Типографика

### Не пишите высоту строки в пикселях
**В чем профит:** текст одинаково удобно читается при любом размере шрифта, не надо заново подгонять интерлиньяж.

*Исключение:* вертикальное однострочное центрирование (если вы на 100% уверены, что текст будет всегда в одну строку).

Текстовые параметры в макете задаются в пикселях и, как правило, переносятся в CSS тоже в пикселях. Хорошая практика — писать высоту строки множителем, без каких-либо единиц измерения. Нужное соотношение можно получить, разделив замерянную высоту строки на размер шрифта и округлив полученный результат до сотых или тысячных.

##### CSS здорового человека

```
.text-block {
  font-size: 14px;
  line-height: 1.5;
}
```

##### CSS копипаст-девелопера

```
.text-block {
  font-size: 14px;
  line-height: 21px;
}
```

**Вывод:** интерлиньяж должен всегда следовать за шрифтом.

Поподробнее и с примерами:
* [Кантор о верстке](http://learn.javascript.ru/font-size-line-height#%D0%BC%D0%BD%D0%BE%D0%B6%D0%B8%D1%82%D0%B5%D0%BB%D1%8C-%D0%B4%D0%BB%D1%8F-line-height)
* [Nope, nope, nope, line-height is unitless](https://allthingssmitty.com/2017/01/30/nope-nope-nope-line-height-is-unitless/)

## Практические советы

### Не привязывайте CSS-правила к HTML-селекторам и их расположению в документе
**В чем профит:** верстка не развалится от первого залетевшего дятла.

*Исключение:* вы стилизуете пользовательский текст, наполняемый через админку. Тут каскад по текстовым селекторам только поощряется. Контент-менеджеру достаточно знать основные тэги и очищать форматирование перед вставкой в хтмл-редактор.

Логика документа и его стилизация — две отдельные абстракции, и чем меньше они пересекаются, тем легче жизнь фронтендщика и окружающих. Наглядный пример — заголовки. Многие пишут стили для них каскадом, но это делает стили очень хрупкими.

* Какой-нибудь сеошник посчитает, что тут нужен заголовок другого уровня (или вообще не заголовок).
* К проекту приступил другой разработчик (или вы возвращаетесь к нему через продолжительное время) и что-то поменял в разметке, забыв про стилизацию.

Всё, дизайн &laquo;поехал&raquo;, и нужно либо писать новое правило, либо адаптировать текущие, а это лишняя трата времени и концентрации внимания.

Поэтому для заголовков (или просто крупных текстов, которые выглядят как заголовки) рационально заводить классы `title-primary`, `title-secondary`, `title-tertiary` и т. п. с нужными вам свойствами. Тогда их можно будет повесить на абсолютно любой хтмл-элемент, а верстка станет более надежной и устойчивой.

##### CSS здорового человека

```
.title-primary {...}
.title-secondary {...}
.text-highlighted {...}
.text-muted {...}
```

##### CSS нуба/лентяя/мракобеса

```
.slider h1 {...}
.text-about > div h2 {...}
div.sepho-bl #search p + p {...}
.product .price p span {...}
```

**Вывод:** крупный текст != html-заголовок (почти всегда).


### Избегайте чрезмерных обобщений, собирайте макет как конструктор
**В чем профит:** компактный CSS, состоящий из готовых к использованию, независимых и легко масштабируемых интерфейсных компонент.

*Исключение:* срочные лендинги/визитки без дальнейшей поддержки и с минимальным включением мозга.

Грамотно спроектированные и хорошо сверстанные сайты/приложения — это набор презентационных или функциональных компонент. Они атомарны, независимы друг от друга, могут легко комбинироваться и образовывать самостоятельные секции и сложные системы.

Приступая к новому макету, внимательно изучите его, выделите повторяющиеся микроблоки и начинайте верстку именно с них. С вероятностью 100% такими блоками станут:

* кнопки;
* модальные окна;
* поля ввода и управляющие элементы форм;
* заголовки и крупные тексты, похожие на заголовки;
* прелоадеры и плейсхолдеры;
* текст повествовательный обыкновенный;
* специфические интерфейсные решения (карточки товара, слайды в карусели, всплывающие подсказки, выпадающие списки и т. п.).

Если на проекте используется препроцессор, то каждый из перечисленных блоков должен быть вынесен в отдельный файл.

Продумывайте, проектируйте, но не забывайте, что чрезмерное усердие неизбежно приведет к написанию очередного никому не нужного CSS-фреймворка.


### Не используйте настройки Автопрефиксера по умолчанию
**В чем профит:** меньше кода в сборке — меньший размер файла, выше скорость его загрузки и обработки браузером.

*Исключение:* вы <del>— латентный некрофил</del> вынужденно или сознательно поддерживаете браузеры, от которых отказались даже их разработчики.

Найдите время, чтобы разобраться, как работает Автопрефиксер, что такое Postcss, Browserslist и почему ищут правды на caniuse.com. Не полагайтесь на выставленные дефолты (на момент написания этого текста — `last 4 version`, т. е. последние 4 версии КАЖДОГО браузера)! А если вам всё-таки лень, то для охвата большинства современных браузеров значения `browserslist: ["> 1%"]` должно хватить с головой.
