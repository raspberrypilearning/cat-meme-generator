## Afficher le texte

Jusqu'à présent, tout le code que tu as écrit est du code HTML et CSS, qui indique à la page à quoi elle devrait **ressembler**. Maintenant, nous allons ajouter du code JavaScript pour dire à la page **ce qu'il faut faire**.

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

  Tu viens de créer une fonction JavaScript appelée `update_text()`. Il n'y a aucune instruction entre parenthèses pour le moment, donc la fonction ne fera rien encore.

- Entre les accolades `{ }`, ajoute le code ci-dessous pour définir la variable `user_text` pour pointer vers la zone de texte où l'utilisateur tape le texte qu'il souhaite voir apparaître sur le mème.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Maintenant c'est à ton tour d'écrire une ligne de code. Sous la ligne que tu viens d'écrire, crée du code pour définir la variable appelée `meme_text` pour pointer vers l'élément avec l'ID `meme_text`, qui est l'endroit où le texte du mème s'affiche. C'est le `<div>` que nous avons créé plus tôt.

--- hints ---
--- hint ---

Décomposons le code que tu as déjà écrit afin de comprendre ce qu'il fait:

* `var user_text` crée une nouvelle variable avec le nom « user_text »
* `=` définit la valeur de cette variable à ...
* ... `document.getElementById("user_text")`, qui parcourt la page Web et pointe vers l'élément portant l'ID `user_text`, la zone de texte d'entrée que nous avons créée précédemment

À l'aide de ces informations, peux-tu déterminer comment créer la nouvelle ligne de code?
--- /hint ---

--- hint ---
Les parties du code que tu dois modifier sont surlignées avec `***` dans le code ci-dessous:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint ---
Le code que tu dois ajouter est ici :

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Nous voulons définir le « meme_text » `<div>` pour qu'il contienne le même texte que l'utilisateur a tapé dans le la zone de texte `meme_text`. Ajoute cette ligne de code en bas de ta fonction JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` fait référence à ce qui est affiché à l'intérieur du `<div>`
  * `.value` fait référence à ce qui est tapé dans la zone de texte appelée `user_text`

- Enfin, nous devons dire à la zone de texte que lorsque quelqu'un tape dedans, il doit appeler la fonction que nous venons d'écrire pour que le texte dans le mème soit mis à jour. Recherche le code de ta zone de texte et ajoute un **attribut** pour `oninput="update_text()"` de sorte qu'il ressemble maintenant à ceci:

  ```html
  Texte du mème : <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Enregistre et actualise ta page, puis essaie de taper dans ta zone de texte et vois ce qui se passe. Si ton code fonctionne, le texte que tu tapes devrait apparaître comme le texte du mème, presque comme par magie!
