# HtmlForms

### Формы в html представляют один из способов для ввода и отправки данных. Все поля формы помещаются между тегами <form> и </form>
 ```
 <form method="post" action="http://localhost:8080/login.php">
            <input name="login"/>
            <input type="submit" value="Войти" />
        </form>
```

Для настройки форм у элемента form определены следующие атрибуты:

method: устанавливает метод отправки данных на сервер. Допустимы два значения: post и get.

Значение post позволяет передать данные на веб-сервер через специальные заголовки. А значение get позволяет передать данные через строку запроса.

action: устанавливает адрес, на который передаются данные формы

enctype: устанавливает тип передаваемых данных. Он свою очередь может принимать следующие значения:

application/x-www-form-urlencoded: кодировка отправляемых данных по умолчанию

multipart/form-data: эта кодировка применяется при отправке файлов

text/plain: эта кодировка применяется при отправке простой текстовой информации


### Автодополнение. 
Часто веб-браузеры запоминают вводимые данные, и при вводе браузеры могут выдавать список подсказок из ранее введенных слов:
Это может быть не всегда удобно, и с помощью атрибута autocomplete можно отключить автодополнение:
```
<form method="post" autocomplete="off" action="http://localhost:8080/login.php">
    <input name="login" />
    <input name="password" />
    <input type="submit" value="Войти" />
</form>
```

Если нам надо включить автодополнение только для каких-то определенных полей, то мы можем применить к ним атрибут autocomplete="on":
```
<form method="post" autocomplete="off" action="http://localhost:8080/login.php">
    <input name="login" />
    <input name="password" autocomplete="on" />
    <input type="submit" value="Войти" />
</form>
```

### Элементы форм

Формы состоят из определенного количества элементов ввода. Все элементы ввода помещаются между тегами <form> и </form>

Наиболее распространенным элементом ввода является элемент input. Однако реальное действие этого элемента зависит от того, какое значение установлено у его атрибута type. А он может принимать следующие значения:

text: обычное текстовое поле

password: тоже текстовое поле, только вместо вводимых символов отображаются звездочки, поэтому в основном используется для ввода пароля

radio: радиокнопка или переключатель. Из группы радиокнопок можно выбрать только одну

checkbox: элемент флажок, который может находиться в отмеченном или неотмеченном состоянии

hidden: скрытое поле

submit: кнопка отправки формы

color: поле для ввода цвета

date: поле для ввода даты

datetime: поле для ввода даты и времени с учетом часового пояса

datetime-local: поле для ввода даты и времени без учета часового пояса

email: поле для ввода адреса электронной почты

month: поле для ввода года и месяца

number: поле для ввода чисел

range: ползунок для выбора числа из некоторого диапазона

tel: поле для ввода телефона

time: поле для ввода времени

week: поле для ввода года и недели

url: поле для ввода адреса url

file: поле для выбора отправляемого файла

image: создает кнопку в виде картинки

Кроме элемента input в различных модификациях есть еще небольшой набор элементов, которые также можно использовать на форме:

button: создает кнопку

select: выпадающий список

label: создает метку, которая отображается рядом с полем ввода

textarea: многострочное текстовое поле

### Атрибуты name и value
У всех элементов ввода можно установить атрибуты name и value. Эти атрибуты имеют важное значение. По атрибуту name мы можем идентифицировать поле ввода, а атрибут value позволяет установить значение поля ввода
```
<form method="get" action="index.html">
            <input type="text" name="login" value="Tom"/>
            <input type="password" name="password"/>
            <input type="submit" value="Войти" />
        </form>
```
### Кнопки
Кнопки представлены элементом button.   Так, в зависимости от значения атрибута type мы можем создать различные типы кнопок:
submit: кнопка, используемая для отправки формы
reset: кнопка сброса значений формы
```
<form>
            <p><input type="text" name="login"/></p>
            <p><input type="password" name="password"/></p>
            <p>
                <button type="submit" formmethod="get" formaction="index.html">Отправить</button> 
                <button type="reset">Отмена</button>
            </p>
        </form>
```
Кроме элемента button для создания кнопок можно использовать элемент input, у которого атрибут равен submit или reset. Например:
```
<form>
            <p><input type="text" name="login"/></p>
            <p><input type="password" name="password"/></p>
            <p>
                <input type="submit" value="Отправить" /> 
                <input type="reset" value="Отмена" />
            </p>
        </form>
```
И еще один элемент input с атрибутом type="image" позволяет использовать в качестве кнопки изображение:
```
<form>
            <p>
                <input type="text" name="search" />
                <input type="image" src="search.png" name="submit" />
            </p>
        </form>
```
### Текстовые поля
С помощью ряда дополнительных атрибутов можно настроить текстовое поле:

dirname: устанавливает направление текста

maxlength: максимально допустимое количество символов в текстовом поле

pattern: определяет шаблон, которому должен соответствовать вводимый текст

placeholder: устанавливает текст, который по умолчанию отображается в текстовом поле

readonly: делает текстовом поле доступным только для чтения

required: указывает, что текстовое поле обязательно должно иметь значение

size: устанавливает ширину текстового поля в видимых символах

value: устанавливает значение по умолчанию в текстовом поле

```
<form>
            <p><input type="text" name="userName" placeholder="Введите имя" size="18" /></p>
            <p><input type="text" name="userPhone" placeholder="Введите номер телефона" size="18" maxlength="11" /></p>
            <p>
                <button type="submit">Отправить</button> 
                <button type="reset">Отмена</button>
            </p>
        </form>
```

Атрибуты readonly и disabled делают текстовое поле недоступным, однако сопровождаются разным визуальным эффектом. В случае с disabled текстовое поле затеняется:
```
<p><input type="text" name="userName" value="Том" readonly /></p>
<p><input type="text" name="userPhone" value="+12345678901" disabled /></p>
```
Среди атрибутов текстового поля также следует отметить такой атрибут как list. Он содержит ссылку на элемент datalist, который определяет набор значений, появляющихся в виде подсказки при вводе в текстовое поле.
```
<form>
            <p><input list="phonesList" type="text" name="model" placeholder="Введите модель" /></p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
        <datalist id="phonesList">
            <option value="iPhone 6S" label="54000"/>
            <option value="Lumia 950">35000</option>
            <option value="Nexus 5X"/>
        </datalist>
```

### Поле ввода пароля
Для ввода пароля используется элемент input с атрибутом type="password". Его отличительной чертой является то, что вводимые символы маскируются точками:
```
<form>
    <p><input type="text" name="login" /></p>
    <p><input type="password" name="password" /></p>
    <input type="submit" value="Авторизация" />
</form>
```
### Метки и автофокус
Вместе с полями ввода нередко используются метки, которые представлены элементом label. Метки создают аннотацию или заголовок к полю ввода, указывают, для чего это поле предназначено.

Для связи с полем ввода метка имеет атрибут for, который указывает на id поля ввода:
```
<form>
            <p>
                <label for="login">Логин: </label>
                <input type="text" id="login" name="login" />
            </p>
            <p>
                <label for="password">Пароль: </label>
                <input type="password" id="password" name="password" />
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
Также мы можем установить автофокус по умолчанию на какое-либо поле ввода. Для этого применяется атрибут autofocus:
Здесь при запуске страницы фокус сразу же переходит на текстовое поле.
```
<form>
    <p>
        <label for="login">Логин: </label>
        <input type="text" autofocus id="login" name="login" />
    </p>
    <p>
        <label for="password">Пароль: </label>
        <input type="password" id="password" name="password" />
    </p>
    <p>
        <button type="submit">Отправить</button>
    </p>
</form>
```
### Элементы для ввода чисел
Простое числовое поле
Для ввода чисел используется элемент input с атрибутом type="number". Он создает числовое поле, которое мы можем настроить с помощью следующих атрибутов:

min: минимально допустимое значение

max: максимально допустимое значение

readonly: доступно только для чтения

required: указывает, что данное поле обязательно должно иметь значение

step: значение, на которое будет увеличиваться число в поле

value: значение по умолчанию
```
 <form>
            <p>
                <label for="age">Возраст: </label>
                <input type="number" step="1" min="1" max="100" value="10" id="age" name="age"/>
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```

Как и в случае с текстовым полем мы можем здесь прикрепить список datalist с диапазоном возможных значений:
```
<form>
            <p>
                <label for="price">Цена: </label>
                <input type="number" list="priceList"
                    step="1000" min="3000" max="100000" value="10000" id="price" name="price"/>
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
        <datalist id="priceList">
            <option value="15000" />
            <option value="20000" />
            <option value="25000" />
        </datalist>
```
### Ползунок
Ползунок представляет шкалу, на которой мы можем выбрать одно из значений. Для создания ползунка применяется элемент input с атрибутом type="range". Во многом ползунок похож на простое поле для ввода чисел. Он также имеет атрибуты min, max, step и value:
```
 <form>
            <p>
                <label for="price">Цена:</label> 
                1<input type="range" step="1" min="0" max="100" value="10" id="price" name="price"/>100
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
### Флажки и переключатели
Флажок представляет элемент, который может находиться в двух состояниях: отмеченном и неотмеченном. Флажок создается с помощью элемента input с атрибутом type="checkbox":
```
<form>
            <p>
                <input type="checkbox" checked name="html5"/>HTML5
            </p>
            <p>
                <input type="checkbox" name="dotnet"/>.NET
            </p>
            <p>
                <input type="checkbox" name="java"/>Java
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
### Переключатели
Переключатели или радиокнопки похожи на флажки, они также могут находиться в отмеченном или неотмеченном состоянии. Только для переключателей можно создать одну группу, в которой одновременно можно выбрать только один переключатель. Например:
```
<form>
            <h2>Укажите пол</h2>
            <p>
                <input type="radio" value="man" checked name="gender"/>мужской
            </p>
            <p>
                <input type="radio" value="woman" name="gender"/>женский
            </p>
            <h2>Выберите технологию</h2>
            <p>
                <input type="radio" value="html5" checked name="tech"/>HTML5
            </p>
            <p>
                <input type="radio" value="net" name="tech"/>.NET
            </p>
            <p>
                <input type="radio" value="java" name="tech"/>Java
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
### Элементы для ввода цвета, url, email, телефона
За установку цвета в HTML5 отвечает специальный элемент input с типом color:
```
<label for="favcolor">Выберите цвет</label>
<input type="color" id="favcolor" name="favcolor" />
```
С помощью элемента datalist мы можем задать набор цветов, из который пользователь может выбрать нужный:
```
<label for="favcolor">Выберите цвет</label>
<input type="color" list="colors" id="favcolor" name="favcolor" />
<datalist id="colors">
    <option value="#0000FF" label="blue">
    <option value="#008000" label="green">
    <option value="#ff0000" label="red">
</datalist>
```
url, адреса электронной почты и телефонного номера. Они однотипны и во многом отличаются только тем, что для атрибута type принимают соответственно значения email, tel и url.
```
<form>
            <p>
                <label for="email">Email: </label>
                <input type="email" placeholder="user@gmail.com" id="email" name="email"/>
            </p>
            <p>
                <label for="url">URL: </label>
                <input type="url" id="url" name="url"/>
            </p>
            <p>
                <label for="phone">Телефон: </label>
                <input type="tel" placeholder="(XXX)-XXX-XXXX" id="phone" name="phone"/>
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
### Элементы для ввода даты и времени

```
 <form>
            <p>
                <label for="firstname">Имя: </label>
                <input type="text" id="firstname" name="firstname"/>
            </p>
            <p>
                <label for="date">Дата рождения: </label>
                <input type="date" id="date" name="date"/>
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
Применение остальных элементов:
```
<form>
            <p>
                <label for="week">Неделя: </label>
                <input type="week" name="week" id="week" />
            </p>
            <p>
                <label for="localdate">Дата и время: </label>
                <input type="datetime-local" id="localdate" name="date"/>
            </p>
            <p>
                <label for="month">Месяц: </label>
                <input type="month" id="month" name="month"/>
            </p>
            <p>
                <label for="time">Время: </label>
                <input type="time" id="time" name="time"/>
            </p>
            <p>
                <button type="submit">Отправить</button>
            </p>
        </form>
```
### Отправка файлов
```
<form enctype="multipart/form-data" method="post" action="http://localhost:8080/postfile.php">
            <p>
                <input type="file" name="file" />
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
```
При нажатии на кнопку "Выберите файл" открывается диалоговое окно для выбора файла. А после выбора рядом с кнопкой отображается имя выбранного файла.

Важно отметить, что для отправки файла на сервер форма должна иметь атрибут enctype="multipart/form-data".

С помощью ряда атрибутов мы можем дополнительно настроить элементы выбора файла:

accept: устанавливает тип файл, которые допустимы для выбора

multiple: позволяет выбирать множество файлов

required: требует обязательной установки файла

Например, множественный выбор файлов:
```
<form enctype="multipart/form-data" method="post" action="http://localhost:8080/postfile.php">
    <p>
        <input type="file" name="file" multiple />
    </p>
    <p>
        <input type="submit" value="Отправить" />
    </p>
</form>
```
### Список select
Элемент select создает список. В зависимости от настроек это может быть выпадающий список для выбора одного элемента, либо раскрытый список, в котором можно выбрать сразу несколько элементов.
```
<form method="get">
            <p>
                <label for="phone">Выберите модель:</label>
                <select id="phone" name="phone">
                    <option value="iphone 6s">iPhone 6S</option>
                    <option value="lumia 950">Lumia 950</option>
                    <option value="nexus 5x">Nexus 5X</option>
                    <option value="galaxy s7">Galaxy S7</option>
                </select>
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
```
Для создания списка с множественным выбором к элементу select надо добавить атрибут multiple:
```
<form method="get">
            <p>
                <label for="phone">Выберите модель:</label> <br/>
             
                <select multiple id="phone" name="phone">
                    <option value="iphone 6s">iPhone 6S</option>
                    <option value="lumia 950">Lumia 950</option>
                    <option value="nexus 5x">Nexus 5X</option>
                    <option value="galaxy s7">Galaxy S7</option>
                </select>
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
```
Select также позволяет группировать элементы с помощью тега <optgroup>:
```
 <form method="get">
            <p>
                <label for="phone">Выберите модель:</label>
             
                <select id="phone" name="phone">
                    <optgroup label="Apple">
                        <option value="iphone 6s">iPhone 6S</option>
                        <option value="iphone 6s plus">iPhone 6S Plus</option>
                        <option value="iphone 5se">iPhone 5SE</option>
                    </optgroup>
                    <optgroup label="Microsoft">
                        <option value="lumia 950">Lumia 950</option>
                        <option value="lumia 950 xl">Lumia 950 XL</option>
                        <option value="lumia 650">Lumia 650</option>
                    </optgroup>
                </select>
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
``` 
 ### Textarea
 Элемент <input type="text" /> позволяет создавать простое однострочное текстовое поле. Однако возможностей этого элемента по вводу текста бывает недостаточно, и в этой ситуации мы можем использовать многострочное текстовое поле, представленное элементом textarea:
 ```
 <form method="get">
            <p>
                <label for="comment">Ваш комментарий:</label><br/>
                <textarea name="comment" id="comment" placeholder="Не более 200 символов" maxlength="200"></textarea>   
            </p>
            <p>
                <input type="submit" value="Добавить" />
            </p>
        </form>
 ```
 С помощью дополнительных атрибутов cols и rows можно задать соответственно количество столбцов и строк:
 ```
 <form method="get">
            <p>
                <label for="comment">Ваш комментарий:</label><br/>
                <textarea id="comment" name="comment" placeholder="Написать комментарий"
                    cols="30" rows="7"></textarea> 
            </p>
            <p>
                <input type="submit" value="Добавить" />
            </p>
        </form>
 ```
 ### Валидация форм
 Для создания валидации у элементов форм HTML5 используется ряд атрибутов:

required: требует обязательного ввода значения. Для элементов textarea, select, input (с типом text, password, checkbox, radio, file, datetime-local, date, month, time, week, number, email, url, search, tel)

min и max: минимально и максимально допустимые значения. Для элемента input с типом datetime-local, date, month, time, week, number, range

pattern: задает шаблон, которому должны соответствовать вводимые данные. Для элемента input с типом text, password, email, url, search, tel

Атрибут required
Атрибут required требует обязательного наличия значения:
 ```
 <form method="get">
            <p>
                <label for="login">Логин:</label>
                <input type="text" required id="login" name="login" />
            </p>
            <p>
                <label for="password">Пароль:</label>
                <input type="password" required id="password" name="password" />
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
 ```
 Атрибуты max и min
Для ограничения диапазона вводимых значений применяются атрибуты max и min:
 ```
  <form method="get">
            <p>
                <label for="age">Возраст:</label>
                <input type="number" min="1" max="100" value="18" id="age" name="age"/>
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
 ```
 Атрибут pattern
Атрибут pattern задает шаблон, которому должны соответствовать данные. Для определения шаблона используется язык так называемых регулярных выражений. Рассмотрим самые простейшие примеры:
 ```
  <form method="get">
            <p>
                <label for="phone">Телефон:</label>
                <input type="text" placeholder="+1-234-567-8901"
                        pattern="\+\d-\d{3}-\d{3}-\d{4}" id="phone" name="phone" />
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
 ```
 Отключение валидации
Не всегда валидация является желаемой, иногда требуется ее отключить. И в этом случае мы можем использовать либо у элемента формы атрибут novalidate, либо у кнопки отправки атрибут formnovalidate:
 ```
 <form novalidate method="get">
            <p>
                <label for="phone">Телефон:</label>
                <input type="text" placeholder="+1-234-567-8901"
                        pattern="\+\d-\d{3}-\d{3}-\d{4}" id="phone" name="phone" />
            </p>
            <p>
                <input type="submit" value="Отправить" formnovalidate />
            </p>
        </form>
 ```
 ### Элементы fieldset и legend
 Для группировки элементов формы нередко применяется элемент fieldset. Он создает границу вокруг вложенных элементов, как бы создавая из них группу. Вместе с ним используется элемент legend, который устанавливает заголовок для группы элементов:
 ```
 <h2>Вход на сайт</h2>
        <form>
            <fieldset>
                <legend>Введите данные:</legend>
                <label for="login">Логин:</label><br>
                <input type="text" name="login" id="login" /><br>
                <label for="password">Пароль:</label><br>
                <input type="password" name="password" id="password" /><br>
                <input type="submit" value="Авторизация">
            </fieldset>
        </form> 
 ```
 При необходимости мы можем создать на одной форме несколько групп с помощью элементов fieldset.
