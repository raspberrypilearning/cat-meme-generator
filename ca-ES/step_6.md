## Mostra el text

Fins ara, tot el codi que has escrit és codi HTML i CSS, que indica a la pàgina **com s'ha de mostrar**. Ara afegiràs algun codi JavaScript per dir-li a la pàgina **què cal fer**.

Quan algú escriu al requadre de text, volem que el seu text es mostri dins del `<div id="meme_text">` que acabem de crear.

- Si utilitzes un fitxer del teu ordinador, afegeix aquestes etiquetes a sota de les teves etiquetes `<div>` per crear una secció on escriure codi JavaScript. Si utilitzes CodePen, pots obviar aquest pas - escriu el codi a la secció ja preparada de JavaScript.

  ```html
  <script type="text/javascript">
  </script>
  ```

- En primer lloc, escriuràs una funció de JavaScript per indicar-li a la pàgina web que agafi qualsevol text que hi hagi al requadre d’entrada i el mostri al `<div>` "meme_text". Entre les dues etiquetes `<script>` que acabes de crear, afegeix el codi següent. Sembla força diferent el codi que hem escrit fins ara, perquè és JavaScript, que és un llenguatge diferent.

  ```JavaScript
  function actualitzar_text(){

  }
  ```

  Acabes de crear una funció de JavaScript que es diu `actualitzar_text()`. En aquest moment no hi ha instruccions entre claus, de manera que la funció encara no farà res.

- Entre les claus `{ }`, afegeix el codi següent per tal que la variable `text_usuari` apunti al requadre de text on l’usuari escriu el text que vol que aparegui al mem.

  ```JavaScript
  var text_usuari = document.getElementById("user_text");
  ```

- Ara és el teu torn per escriure una línia de codi. A sota de la línia que acabes d’escriure, crea el codi per tal que la variable anomenada `text_mem` apunti a l’ID `meme_text`, que és on es mostrarà el text del mem. Aquest és el `<div>` que hem creat anteriorment.

--- hints --- --- hint --- Anem a desglossar el codi que acabes d'escriure per comprendre el que fa:

* `var text_usuari` crea una variable nova amb el nom "text_usuari"
* `=` assigna el valor d'aquesta variable a...
* ... `document.getElementById ("user_text")` examina la pàgina web i apunta a l'element amb l'ID `user_text`, el requadre de text d’entrada que hem creat anteriorment

Amb aquesta informació, pots esbrinar com es pot crear la nova línia de codi? --- /hint ---

--- hint --- Les parts del codi que has de canviar es ressalten amb `***` al codi següent:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- El codi que cal afegir és el següent:

```JavaScript
var text_mem = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Volem que el `<div>` 'text_mem' contingui el mateix text que l'usuari ha escrit al requadre `meme_text`. Afegeix aquesta línia de codi al final de la teva funció de JavaScript:

  ``` JavaScript
  text_mem.innerHTML = text_usuari.value;
  ```

  * `.innerHTML` fa referència al que es mostra dins del `<div>`
  * `.value` fa referència al que s'escriu al requadre de text anomenat `user_text`

- Per acabar, hem de dir al requadre de text que, quan algú hi escriu, hauria de cridar a la funció que acabem d’escriure per tal que el text del mem s’actualitzi. Cerca el codi del requadre de text i afegeix-li un **atribut** `oninput="actualitzar_text()"` per tal que quedi així:

  ```html
  Text del mem: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Desa i actualitza la teva pàgina, a continuació torna a escriure al requadre de text i fixa't què passa. Si el teu codi funciona, el text que escrius hauria d’aparèixer com a text del mem, gairebé com màgia!
