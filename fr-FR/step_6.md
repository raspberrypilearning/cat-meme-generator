## Afficher le texte

Jusqu'à présent, tout le code que tu as écrit est du code HTML et CSS, qui indique à la page à quoi elle devrait **ressembler** . Maintenant, nous allons ajouter du code JavaScript pour dire à la page ** ce qu'il faut faire**.

Lorsque quelqu'un tape du texte dans la zone de texte, nous voulons que son texte s'affiche à l'intérieur du `<div id="meme_text">` que nous venons de créer.

- Si tu utilises un fichier sur ton ordinateur, ajoute ces balises sous tes balises `<div>` pour créer une section dans laquelle écrire du code JavaScript. Si tu utilises CodePen, tu peux ignorer cette étape - écris ton code dans la section JavaScript prête à l'emploi.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Tout d'abord, nous allons écrire une fonction JavaScript pour dire à la page Web de prendre tout texte qui se trouve dans la zone de saisie et de l'afficher dans le « meme_text » `<div>`. Entre les deux balises `<script>` que tu viens de créer, ajoute le code ci-dessous. Il semble assez différent du code que nous avons écrit jusqu'à présent, parce que c'est du JavaScript, qui est un langage différent.

  ```JavaScript
  function update_text(){

  }
  ```

  Tu viens de créer une fonction JavaScript appelée `update_text()` . Il n'y a aucune instruction entre parenthèses pour le moment, donc la fonction ne fera rien encore.

- Entre les accolades `{ }` , ajoute le code ci-dessous pour définir la variable `user_text` pour pointer vers la zone de texte où l'utilisateur tape le texte qu'il souhaite voir apparaître sur le mème.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Maintenant c'est à ton tour d'écrire une ligne de code. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. This is the `<div>` we created earlier.

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
