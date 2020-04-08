## Obteniendo la imagen y el texto

Queremos que las personas puedan usar su propia imagen y texto para crear el meme, por lo que necesitamos una forma para que puedan proporcionarlos. Agreguemos un formulario que nuestro usuario pueda completar.

Si estás usando un archivo en tu ordenador, pon este código entre `<body>` y `</body>`. Si estás usando CodePen, pon este código en la sección HTML.

- Agrega las etiquetas `<form>,` que indican el inicio del formulario y `</form>,` que indican el final del formulario.

    ```html
    <form>
    </form>
    ```

- Dentro de tu `<form>`, añade un cuadro de texto para que puedas escribir el texto del meme:

  ```html
  <form>
  Texto del meme: <input type="text" id="user_text" maxlength="70"><p>
  </form>
  ```

- Guarda tu código y actualiza tu navegador para ver la casilla que creaste.

    ![First box](images/first-box.png)

- Agrega código para crear otra casilla de entrada en la línea debajo de tu primera casilla. Esta vez, la casilla de entrada no será una casilla de texto, sino una casilla especial para seleccionar el archivo de la imagen para el meme. The input type should be `file`, and the name of the input should be `user_picture`.

--- hints ---

--- hint --- Here's what the code you already wrote does:

  * `input` says we are creating a way for the user to provide some data
  * `type="text"` says that the data will be text
  * `id="user_text"` gives this particular box a name or ID, a bit like a variable name
  * `maxlength="70"` is optional - it stops you from typing in more than 70 letters so your text doesn't take up space past the bottom of the image
  * The `<p>` tag after the input box adds a paragraph (a bit of space before the next input box)

Can you work out how to create another input box using this information?

--- /hint ---

--- hint ---

You will need to change the parts of the code highlighted with `***` below:

```html
Select a picture <input type="***" id="***"><p>
```

--- /hint ---

--- hint --- Here is the code you need to add:

```html
Select a picture <input type="file" id="user_picture"><p>
```
--- /hint ---

--- /hints ---

- You can use these boxes to type into and to select a file, but nothing will happen yet. **Note**: all images are kept on your computer - this program does not upload anything to the internet.
