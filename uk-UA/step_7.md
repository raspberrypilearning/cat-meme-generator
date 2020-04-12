## Показ зображення

Тепер ми напишемо код, щоб взяти зображення кота, яке користувач вибрав, і відобразити його в мемі.

- Створи нову функцію JavaScript з іменем `update_image`. Будь уважним, цей код треба ввести після закриваючої фігурної дужки `}` функції, яку ти вже створив.

[[[generic-javascript-create-a-function]]]

- Всередині функції `update_image` створи дві нові змінні:

    ```javascript
    var img = document.querySelector('img');
    ```

    Перша змінна вибирає перший (і єдиний!) тег `<img>` в документі, щоб ми могли сказати, де відображати вибрану картинку.

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    Друга змінна вказує на вибраний файл із зображеннням кота.

- Зроби, щоб тег зображення містив картинку, яку завантажив користувач:

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- Тепер додай код, щоб сказати файловому полю викликати функцію `update_image()`, коли хтось вибирає файл (`onchange`).

--- hints ---

--- hint --- Згадай, що на попередньому кроці ти викликав (-ла) функцію `update_text()` коли новий текст вводився в поле `user_text`. Використовуючи ці знання, чи можеш ти придумати, як викликати функцію `update_image()`, коли користувач вибирає файл в полі `user_file`? --- /hint ---

--- hint --- You will need to add `onchange=""` and then replace the `***` with the function you would like to call:
```javascript
Select a picture <input type="file" id="user_picture" onchange="***">
```
--- /hint ---

--- hint --- Find the line of code for the file input box and add `onchange="update_image()"` like this:
```html
Select a picture <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- Save and refresh the page. If your code is working, when you select a picture using the **Select a picture** input box, that picture should appear in the meme box below. If you also type something into the text box, your meme text should appear on top of the picture.

![Finished meme](images/finished-meme.png)
