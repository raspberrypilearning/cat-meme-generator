## Muestra la imagen

Ahora vamos a escribir código para coger la imagen del gato que el usuario ha seleccionado y mostrarla en el meme.

- Define a new JavaScript function called `update_image`. Ten cuidado y escribe este código después de la llave de cierre `}` de la función que creaste antes.

[[[generic-javascript-create-a-function]]]

- Inside the `update_image` function, create two new variables:

    ```javascript
    var img = document.querySelector('img');
    ```

    Esta primera variable selecciona la primera (¡y única!) etiqueta `<img>` del documento para que podamos indicar a la página dónde mostrar la imagen seleccionada.

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    Esta segunda variable apunta al archivo con la imagen del gato seleccionada.

- Establece la etiqueta de imagen (img) para que contenga la imagen que el usuario ha subido:

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- Now add some code to tell the file input to call the `update_image()` function `onchange` when someone selects a file.

--- hints ---

--- hint --- Remember that, in the previous step, you called the function `update_text()` when new text was written into the `user_text` input box. Using what you learned then, can you work out how to call the function `update_image()` when the user selects a file in the `user_file` input box? --- /hint ---

--- hint --- Necesitarás añadir `onchange=""` y luego reemplazar el `***` con la función que te gustaría llamar:
```javascript
Selecciona una imagen <input type="file" id="user_picture" onchange="***">
```
--- /hint ---

--- hint --- Find the line of code for the file input box and add `onchange="update_image()"` like this:
```html
Selecciona una imagen <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- Guarda y actualiza la página. If your code is working, when you select a picture using the **Select a picture** input box, that picture should appear in the meme box below. Si también escribes algo en el cuadro de texto, tu texto meme debería aparecer encima de la imagen.

![Meme terminado](images/finished-meme.png)
