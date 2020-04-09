## Muestra el texto

Hasta ahora, todo el código que has escrito está en lenguaje HTML y CSS, que le dice a la página el **aspecto** que debería tener. Ahora vamos a añadir algo de código JavaScript para decirle a la página **qué hacer**.

Cuando alguien escribe texto en el cuadro de texto, queremos que su texto se muestre dentro del `<div id="meme_text">` que acabamos de crear.

- Si estás usando un archivo en tu ordenador, añade estas etiquetas debajo de tus etiquetas `<div>` para crear una sección en la que escribir código JavaScript. Si estás usando CodePen, puedes omitir este paso - escribe tu código en la sección de JavaScript.

  ```html
  <script type="text/javascript">
</script>
  ```

- En primer lugar, escribiremos una función JavaScript para decirle a la página web que coja cualquier texto que esté en el cuadro de entrada y que lo muestre en el `<div>` "texto del meme". Entre las dos etiquetas `<script>` que acabas de crear, añade el código indicado abajo. Tiene un aspecto bastante diferente al código que hemos escrito hasta ahora, porque es JavaScript, que es un lenguaje diferente.

  ```JavaScript
  function update_text(){

  }
  ```

  You've just created a JavaScript function called `update_text()`. No hay instrucciones entre los corchetes por ahora, por lo que la función no hará nada todavía.

- Between the curly brackets `{ }`, add the code below to set the variable `user_text` to point to the text box where the user types the text they want to appear on the meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Ahora es tu turno de escribir una línea de código. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. Este es el `<div>` que creamos antes.

--- hints --- --- hint --- Vamos a analizar el código que has escrito para que entiendas lo que hace:

* `var user_text` creates a new variable with the name "user_text"
* `=` establece el valor de esta variable a...
* ...`document.getElementById("user_text")`, which looks through the web page and points to the element with the ID `user_text`, the input text box we created earlier

Usando esta información, ¿puedes averiguar cómo crear la nueva línea de código? --- /hint ---

--- hint --- Las partes del código que necesitas cambiar están resaltadas con `***` en el siguiente código:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- El código que necesitas añadir está aquí:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- We want to set the 'meme_text' `<div>` to contain the same text the user has typed into the `meme_text` textbox. Añade esta línea de código al final de tu función JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` se refiere a lo que se muestra dentro del `<div>`
  * `.value` refers to what is typed into the text box called `user_text`

- Por último, tenemos que decirle al cuadro de texto que cuando alguien escribe en él, debería llamar a la función que acabamos de crear para que el texto en el meme se actualize. Find the code for your text box and add in an **attribute** for `oninput="update_text()"` so that it now looks like this:

  ```html
  Texto del meme: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Guarda y actualiza tu página, y luego intenta escribir en tu cuadro de texto para ver lo que sucede. Si tu código funciona, el texto que escribas debería aparecer como el texto de meme, ¡casi por arte de magia!
