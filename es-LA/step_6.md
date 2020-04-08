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

- Entre los corchetes `{ }` , agrega el código a continuación para establecer la variable `user_text` que apunta a la casilla de texto donde el usuario va a escribir el texto que desea que aparezca en el meme.

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

--- hint --- El código que necesitas añadir está aquí:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Queremos establecer el 'meme_text' `<div>` para contener el mismo texto que el usuario ha escrito en la casilla de texto `user_text`. Añade esta línea de código al final de tu función JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` se refiere a lo que se muestra dentro de la `<div>`
  * `.value` se refiere a lo que se escribe en la casilla de texto `user_text`

- Por último, debemos decirle a la casilla de texto que cuando alguien escriba en ella, debe llamar a la función que acabamos de escribir para que el texto del meme se actualice. Encuentra el código para tu casilla de texto y añade un **atributo** para `oninput="update_text()"` para que ahora se vea así:

  ```html
  Texto del meme: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Guarda y actualiza tu página, luego intenta escribir en tu casilla de texto y observa qué sucede. Si tu código está funcionando, el texto que escribas debería aparecer como el texto del meme, ¡casi como mágico!
