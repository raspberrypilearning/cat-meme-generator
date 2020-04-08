## Tekst weergeven

Tot dusver is alle code die je hebt geschreven HTML- en CSS-code, die de pagina vertelt hoe deze er **uit moet zien**. Nu gaan we wat JavaScript-code toevoegen om de pagina **te vertellen wat hij moet doen**.

Wanneer iemand tekst in het tekstvak typt, willen we dat hun tekst wordt weergegeven in de `<div id="meme_text">` die we zojuist hebben gemaakt.

- Als je een bestand op je computer gebruikt, voeg je deze tags toe onder je `<div>`-tags om een sectie te maken waarin je JavaScript-code kunt schrijven. Als je CodePen gebruikt, kun je deze stap overslaan - schrijf je code in de kant-en-klare JavaScript-sectie.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Ten eerste zullen we een JavaScript-functie schrijven om de webpagina te vertellen dat elke tekst die in het invoervak staat, moet worden opgenomen in de "meme_text" `<div>`. Voeg de onderstaande code toe tussen de twee zojuist gemaakte `<script>`-tags. Het ziet er behoorlijk anders uit dan de code die we tot nu toe hebben geschreven, omdat het JavaScript is, een andere taal.

  ```JavaScript
  function update_text(){

  }
  ```

  Je hebt zojuist een JavaScript-functie gemaakt met de naam `update_text()`. Er staan momenteel geen instructies tussen de accolades, dus de functie doet nog niets.

- Voeg tussen de accolades `{ }` de onderstaande code toe om de variabele `user_text` te laten verwijzen naar het tekstvak waarin de gebruiker de tekst typt die hij in de meme wil laten verschijnen.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Nu is het jouw beurt om een regel code te schrijven. Onder de regel die je zojuist hebt geschreven, maak je code om de variabele `meme_text` in te stellen om te verwijzen naar het element met het ID `meme_text`, wat de plek is waar de meme-tekst wordt weergegeven. Dit is de `<div>` die we eerder hebben gemaakt.

--- hints --- --- hint --- Laten we de code die je al schreef opsplitsen zodat je begrijpt wat het doet:

* `var user_text` maakt een nieuwe variabele aan met de naam "user_text"
* `=` stelt de waarde van deze variabele in op...
* ... `document.getElementById("user_text")`, die naar de webpagina kijkt en verwijst naar het element met het ID `user_text`, het invoer tekstvak dat we eerder hebben gemaakt

Kunt je met behulp van deze informatie bepalen hoe je de nieuwe coderegel maakt? --- /hint ---

--- hint --- De delen van de code die je moet wijzigen, zijn gemarkeerd met `***` in de onderstaande code:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- De code die je moet toevoegen, is deze:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- We willen de 'meme_text' `<div>` zo instellen dat deze dezelfde tekst bevat die de gebruiker in het `meme_text` tekstveld heeft in getypt. Voeg deze regel code toe aan de onderkant van je JavaScript-functie:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` verwijst naar wat wordt weergegeven in de `<div>`
  * `.value` verwijst naar wat is getypt in het tekstvak met de naam `user_text`

- Ten slotte moeten we het tekstvak vertellen dat wanneer iemand iets erin typt, het de functie moet aanroepen die we zojuist hebben geschreven, zodat de tekst in de meme wordt bijgewerkt. Zoek de code voor je tekstvak en voeg ervoor een **attribute** toe `oninput="update_text()"` zodat het er nu zo uitziet:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Bewaar en vernieuw je pagina, typ vervolgens wat in je tekstvak en kijk wat er gebeurt. Als je code werkt, zou de tekst die je typt moeten verschijnen als de meme-tekst, het lijkt wel magie!
