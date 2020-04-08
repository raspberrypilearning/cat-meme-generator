## Mostra el text

Fins ara, tot el codi que has escrit és codi HTML i CSS, que indica a la pàgina **com s'ha de mostrar**. Ara afegiràs algun codi JavaScript per dir-li a la pàgina **què cal fer**.

Quan algú escriu al requadre de text, volem que el seu text es mostri dins del `<div id="meme_text">` que acabem de crear.

- Si utilitzes un fitxer del teu ordinador, afegeix aquestes etiquetes a sota de les teves etiquetes `<div>` per crear una secció on escriure codi JavaScript. Si utilitzes CodePen, pots obviar aquest pas - escriu el codi a la secció ja preparada de JavaScript.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Firstly, we'll write a JavaScript function to tell the web page to take any text that's in the input box and display it in the "meme_text" `<div>`. Entre les dues etiquetes `<script>` que acabes de crear, afegeix el codi següent. Sembla força diferent el codi que hem escrit fins ara, perquè és JavaScript, que és un llenguatge diferent.

  ```JavaScript
  function actualitzar_text(){

  }
  ```

  Acabes de crear una funció de JavaScript que es diu `actualitzar_text()`. En aquest moment no hi ha instruccions entre claus, de manera que la funció encara no farà res.

- Between the curly brackets `{ }`, add the code below to set the variable `user_text` to point to the text box where the user types the text they want to appear on the meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Now it's your turn to write a line of code. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. This is the `<div>` we created earlier.

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
