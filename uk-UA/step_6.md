## Показ тексту

Поки що весь твій код був написаний на HTML та CSS, що визначає, як сторінка має **виглядати**. А зараз ти додаси трохи коду JavaScript, щоб визначати, що сторінка має **робити**.

Коли хтось вводить текст в текстове поле, ми хочемо, щоб він відобразився всередині `<div id="meme_text">`, який ми щойно створили.

- Якщо ти використовуєш файл на своєму комп’ютері, додай ці теги під тегами `<div>` для створення секції, в якій можна писати код JavaScript. Якщо ж ти використовуєш CodePen, то можеш пропустити цей крок, пиши свій код в окремій JavaScript-секції.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Спочатку ми напишемо JavaScript-функцію, щоб брати будь-який текст, що знаходиться в полі для вводу і відображати його в `<div>` "meme_text". Між двома щойноствореними тегами `<script>` додай нижченаведений код. Він виглядає зовсім інакше від усього коду, який ми писали досі, тому що це — JavaScript, який є іншою мовою.

  ```JavaScript
  function update_text(){

  }
  ```

  Ти щойно створив функцію JavaScript з назвою `update_text()`. Наразі між фігурними дужками немає жодних інструкцій, тому ця функція ще нічого не робить.

- Між фігурними дужками `{ }` додай нижченаведений код, щоб визначити змінну `user_text`, яка буде вказувати на текстове поле, куди користувач вводитиме те, що він хоче побачити в мемі.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Тепер твоя черга написати рядок коду. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. This is the `<div>` we created earlier.

--- hints --- --- hint --- Let's break down the code you already wrote so that you understand what it does:

* `var user_text` creates a new variable with the name "user_text"
* `=` sets the value of this variable to...
* ...`document.getElementById("user_text")`, which looks through the web page and points to the element with the ID `user_text`, the input text box we created earlier

Using this information, can you work out how to create the new line of code? --- /hint ---

--- hint --- The parts of the code you need to change are highlighted with `***` in the code below:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- The code you need to add is here:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- We want to set the 'meme_text' `<div>` to contain the same text the user has typed into the `meme_text` textbox. Add this line of code to the bottom of your JavaScript function:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` refers to what is displayed inside the `<div>`
  * `.value` refers to what is typed into the text box called `user_text`

- Lastly, we need to tell the text box that when someone types into it, it should call the function we just wrote so that the text in the meme will update. Find the code for your text box and add in an **attribute** for `oninput="update_text()"` so that it now looks like this:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Save and refresh your page, then try typing into your text box and see what happens. If your code is working, the text you type should appear as the meme text, almost like magic!
