## Den Text anzeigen

So far, all of the code you have written is HTML and CSS code, which tells the page what it should **look like**. Jetzt werden wir JavaScript-Code hinzufügen, um der Seite mitzuteilen **was sie tun** soll.

Wenn jemand Text in das Textfeld eingibt wollen wir, dass sein Text im soeben erstellten `<div id="meme_text">` angezeigt wird.

- Wenn du eine Datei auf deinem Computer verwendest, füge diese Tags unter deinen `<div>`-Tags hinzu, um einen Abschnitt zu erstellen in den du JavaScript-Code schreiben kannst. Wenn du CodePen verwendest, kannst du diesen Schritt überspringen - schreibe deinen Code in den vorgefertigten JavaScript-Abschnitt.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Zunächst schreiben wir eine JavaScript-Funktion, um die Webseite anzuweisen, jeden Text im Eingabefeld zu nehmen und im "meme_text" `<div>` anzuzeigen. Füge den unten stehenden Code zwischen die zwei `<script>`-Tags ein, die du gerade erstellt hast. Das sieht komplett anders aus als der Code den wir bisher geschrieben haben, weil es JavaScript ist, was eine andere Sprache ist.

  ```JavaScript
  function update_text(){

  }
  ```

  Du hast gerade eine JavaScript-Funktion namens `update_text()` erstellt. In den Klammern befinden sich derzeit keine Anweisungen, sodass die Funktion noch nichts tut.

- Between the curly brackets `{ }`, add the code below to set the variable `user_text` to point to the text box where the user types the text they want to appear on the meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Jetzt ist es an dir, eine Zeile Code zu schreiben. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. Das ist das `<div>`, welches wir vorhin erstellt haben.

--- hints --- --- hint --- Lass uns den Code entschlüsseln, den du bisher geschrieben hast, damit du verstehst was er tut:

* `var user_text` erstellt eine neue Variable mit dem Namen "user_text"
* `=` setzt den Wert dieser Variable auf...
* ...`document.getElementById ("user_text")`, das die Webseite durchsucht und auf das Element mit der ID `user_text`, das zuvor erstellte Eingabetextfeld, zeigt

Using this information, can you work out how to create the new line of code? --- /hint ---

--- Hinweis --- Die Teile des Codes, die du ändern musst, sind im folgenden Code mit `***` hervorgehoben:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- The code you need to add is here:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

---/hints ---


- We want to set the 'meme_text' `<div>` to contain the same text the user has typed into the `meme_text` textbox. Füge diese Codezeile am Ende deiner JavaScript-Funktion hinzu:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` bezieht sich auf das, was im `<div>` angezeigt wird
  * `.value` bezieht sich auf das, was in das Textfeld `user_text` eingegeben wird

- Schließlich müssen wir dem Textfeld sagen, dass es die Funktion, die wir gerade geschrieben haben, aufruft, wenn jemand etwas eingibt, damit der Text im Meme aktualisiert wird. Suche den Code für dein Textfeld und füge ein **Attribut** für `oninput="update_text()"` hinzu, damit es nun so aussieht:

  ```html
  Meme Text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Speichere und lade deine Seite neu, dann versuche etwas in dein Textfeld einzugeben und sieh was passiert. If your code is working, the text you type should appear as the meme text, almost like magic!
