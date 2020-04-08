## Mostrar el texto

Hasta ahora, todo el código que has escrito es código HTML y CSS, que le dice a la página cómo **debería ser**. Ahora vamos a añadir algo de código JavaScript para decirle a la página **qué hacer**.

Cuando alguien escribe texto en el cuadro de texto, queremos que su texto se muestre dentro del `<div id="meme_text">` que acabamos de crear.

- Si está utilizando un archivo en tu ordenadora, agrega estas etiquetas debajo de las etiquetas `<div>` para crear una sección en la que escribir el código JavaScript. Si estás usando CodePen, puedes omitir este paso: escribe tu código en la sección de JavaScript ya hecha.

  ```html
  <script type="text/javascript">
</script>
  ```

- En primer lugar, escribiremos una función JavaScript para decirle a la página web que tome cualquier texto que esté en la casilla de entrada y que lo muestre en el "meme_text" `<div>`. Entre las dos etiquetas `<script>` que acabas de crear, añade el código de abajo. Se ve bastante diferente al código que hemos escrito hasta ahora, porque es JavaScript, un idioma diferente.

  ```JavaScript
  function update_text(){

  }
  ```

  Acabas de crear una función JavaScript llamada `update_text()`. No hay instrucciones entre los corchetes en este momento, por lo que la función no hará nada todavía.

- Between the curly brackets `{ }`, add the code below to set the variable `user_text` to point to the text box where the user types the text they want to appear on the meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Ahora es tu turno de escribir una línea de código. Debajo de la línea que acabas de escribir, crea código para establecer la variable `meme_text` que apunta al elemento con ID `meme_text`, que es donde se mostrará el texto de meme. Este es el `<div>` que creamos antes.

--- hints --- --- hint --- Analicemos el código que ya escribiste para que entiendas lo que hace:

* `var user_text` crea una nueva variable con el nombre "user_text"
* `=` establece el valor de esta variable a...
* ...`document.getElementById("user_text")`, que mira a través de la página web y apunta al elemento con el ID `user_text`, la casilla de texto de entrada que hemos creado anteriormente

Usando esta información, ¿puedes averiguar cómo crear la nueva línea de código? --- /hint ---

--- hint --- Las partes del código que necesitas cambiar se resaltan con `***` en el siguiente código:
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
