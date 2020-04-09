## Muestra la imagen

Ahora vamos a escribir código para coger la imagen del gato que el usuario ha seleccionado y mostrarla en el meme.

- Define a new JavaScript function called `update_image`. Ten cuidado y escribe este código después de la llave de cierre `}` de la función que creaste antes.

[[[generic-javascript-create-a-function]]]

- Inside the `update_image` function, create two new variables:

    ```javascript
    var img = document.querySelector('img');
    ```

    This first variable selects the first (and only!) `<img>` tag in the document, so that we can tell the page where to display the selected image.

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    This second variable points to the selected cat picture file.

- Set the image tag to contain the picture that the user has uploaded:

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- Now add some code to tell the file input to call the `update_image()` function `onchange` when someone selects a file.

--- hints ---

--- hint --- Remember that, in the previous step, you called the function `update_text()` when new text was written into the `user_text` input box. Using what you learned then, can you work out how to call the function `update_image()` when the user selects a file in the `user_file` input box? --- /hint ---

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
