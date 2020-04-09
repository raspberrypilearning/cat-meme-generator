## Den Text anzeigen

Bisher ist der gesamte Code, den du geschrieben hast, HTML und CSS Code, welcher der Seite sagt **wie sie aussehen** soll. Jetzt werden wir JavaScript-Code hinzufügen, um der Seite mitzuteilen **was sie tun** soll.

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

- Füge den folgenden Code zwischen die geschweiften Klammern `{ }` ein, um die Variable `user_text` auf die Textbox verweisen zu lassen, in die der Benutzer den Text eingibt, der auf dem Meme angezeigt werden soll.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Jetzt ist es an dir, eine Zeile Code zu schreiben. Erstelle unterhalb der Zeile, die du gerade geschrieben hast, Code um die Variable namens `meme_text` auf das Element mit der ID `meme_text`, welches den Meme-Text anzeigen wird, zeigen zu lassen. Das ist das `<div>`, welches wir vorhin erstellt haben.

--- hints ---
 --- hint --- Lass uns den Code entschlüsseln, den du bisher geschrieben hast, damit du verstehst was er tut:

* `var user_text` erstellt eine neue Variable mit dem Namen "user_text"
* `=` setzt den Wert dieser Variable auf...
* ...`document.getElementById ("user_text")`, das die Webseite durchsucht und auf das Element mit der ID `user_text`, das zuvor erstellte Eingabetextfeld, zeigt

Kannst du mithilfe dieser Informationen herausfinden, wie du die neue Codezeile erstellst?
--- /hint ---


--- Hinweis --- Die Teile des Codes, die du ändern musst, sind im folgenden Code mit `***` hervorgehoben:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- Das ist der Code, den du hinzufügen musst:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

---/hints ---


- Wir möchten das "meme_text"-`<div>` so einstellen, dass es denselben Text enthält, den der Benutzer in das `meme_text`-Textfeld eingegeben hat. Füge diese Codezeile am Ende deiner JavaScript-Funktion hinzu:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` bezieht sich auf das, was im `<div>` angezeigt wird
  * `.value` bezieht sich auf das, was in das Textfeld `user_text` eingegeben wird

- Schließlich müssen wir dem Textfeld sagen, dass es die Funktion, die wir gerade geschrieben haben, aufruft, wenn jemand etwas eingibt, damit der Text im Meme aktualisiert wird. Suche den Code für dein Textfeld und füge ein **Attribut** für `oninput="update_text()"` hinzu, damit es nun so aussieht:

  ```html
  Meme Text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Speichere und lade deine Seite neu, dann versuche etwas in dein Textfeld einzugeben und sieh was passiert. Wenn dein Code funktioniert, sollte der Text, den du eingibst, als Meme-Text erscheinen, wie durch Zauberei!
