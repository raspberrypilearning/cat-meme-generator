## Mostra il testo

Finora, tutto il codice che hai scritto è HTML e CSS, che dice alla pagina come **dovrebbe apparire**. Ora aggiungeremo un po' di codice JavaScript per dire alla pagina **cosa fare**.

Quando qualcuno scrive del testo nella casella di testo, vogliamo che il suo testo sia visualizzato all'interno del `<div id="meme_text">` che abbiamo appena creato.

- Se stai usando un file sul tuo computer, aggiungi questi tag sotto i tuoi tag `<div>` per creare una sezione in cui scrivere codice JavaScript. Se stai usando CodePen, puoi saltare questo passaggio: scrivi il tuo codice nella sezione JavaScript già pronta.

  ```html
  <script type="text/javascript">
</script>
  ```

- In primo luogo, scriveremo una funzione JavaScript per dire alla pagina web di prendere qualsiasi testo presente nella casella di input e visualizzarlo nel `<div>` "meme_text". Tra i due tag `<script>` che hai appena creato, aggiungi il codice qui sotto. Sembra abbastanza diverso dal codice che abbiamo scritto fino ad ora, perché è JavaScript, che è un linguaggio diverso.

  ```JavaScript
  function update_text(){

  }
  ```

  Hai appena creato una funzione JavaScript chiamata `update_text()` ("aggiorna testo"). Al momento non ci sono istruzioni tra parentesi, quindi la funzione non farà ancora nulla.

- Tra le parentesi graffe `{ }`, aggiungi il codice qui sotto per impostare la variabile `user_text` per puntare alla casella di testo dove l'utente digita il testo che vuole apparire sul meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Ora tocca a te scrivere una riga di codice. Sotto la riga che hai appena scritto, crea il codice per impostare la variabile chiamata `meme_text` per puntare all'elemento con l'ID `meme_text`, che è dove apparirà il testo del meme. Questo è il `<div>` che abbiamo creato in precedenza.

--- hints ---
 --- hint --- Separiamo il codice che hai già scritto in modo che tu capisca cosa fa:

* `var user_text` crea una nuova variabile con il nome "user_text"
* `=` imposta il valore di questa variabile a...
* ...`document.getElementById("user_text")`, che cerca nella la pagina web e punta all'elemento con l'ID `user_text`, la casella di testo di input che abbiamo creato in precedenza

Utilizzando queste informazioni, puoi capire come creare la nuova riga di codice?
--- /hint ---


--- hint --- Le parti del codice che devi modificare sono evidenziate con `***` nel codice sottostante:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- Il codice che devi aggiungere è qui:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Vogliamo impostare il `<div>` 'meme_text' in modo che contenga lo stesso testo digitato dall'utente nella casella di testo `meme_text`. Aggiungi questa riga di codice in fondo alla tua funzione JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` si riferisce a ciò che viene visualizzato all'interno di `<div>`
  * `.value` si riferisce a ciò che viene digitato nella casella di testo chiamata `user_text`

- Infine, dobbiamo dire alla casella di testo che quando qualcuno scrive in essa dovrà chiamare la funzione che abbiamo appena scritto in modo che il testo nel meme venga aggiornato. Trova il codice per la tua casella di testo e aggiungi un **attributo** per `oninput="update_text()"` così che ora appaia così:

  ```html
  Testo del meme: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Salva e aggiorna la tua pagina, quindi prova a digitare nella casella di testo e guarda cosa succede. Se il tuo codice funziona, il testo digitato dovrebbe apparire come il testo del meme, quasi come per magia!
