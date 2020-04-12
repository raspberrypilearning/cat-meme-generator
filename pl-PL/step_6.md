## Wyświetl tekst

Do tej pory cały kod, który napisałeś, to kod HTML i CSS, które mówią stronie, jak powinna **wyglądać**. Teraz dodamy kod JavaScript, aby powiedzieć stronie **co zrobić**.

Gdy ktoś wpisuje tekst w polu tekstowym, chcemy, aby jego tekst był wyświetlany wewnątrz `<div id="meme_text">`, którą właśnie utworzyliśmy.

- Jeśli używasz pliku na komputerze, dodaj te tagi pod tagami `<div>`, aby utworzyć sekcję, w której można pisać kod JavaScript. Jeśli używasz CodePen, możesz pominąć ten krok - napisz swój kod w gotowej sekcji JavaScript.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Najpierw napiszemy funkcję JavaScript, która każe stronie internetowej pobrać dowolny tekst z pola wprowadzania i wyświetlić go w „meme_text” `<div>`. Pomiędzy dwoma tagami `<script>` które właśnie utworzyłeś, dodaj poniższy kod. Wygląda dość inaczej niż kod, który dotychczas napisaliśmy, ponieważ jest to JavaScript, który jest innym językiem.

  ```JavaScript
  function update_text(){

  }
  ```

  Właśnie utworzyłeś funkcję JavaScript o nazwie `update_text()`. W tej chwili nie ma instrukcji w nawiasach, więc funkcja jeszcze nic nie zrobi.

- Między nawiasami klamrowymi `{ }`, dodaj poniższy kod, aby ustawić zmienną `user_text` aby wskazać pole tekstowe, w którym użytkownik wpisuje tekst, który ma być wyświetlany w memie.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Teraz twoja kolej napisać wiersz kodu. Pod wierszem, który właśnie napisałeś, utwórz kod, aby ustawić zmienną o nazwie `meme_text` wskazywać na element o identyfikatorze `meme_text`, gdzie będzie wyświetlany tekst memu. To jest `<div>` stworzona wcześniej.

--- hints --- --- hint --- Przeanalizujmy kod, który już napisałeś, aby zrozumieć, co to robi:

* `var user_text` tworzy nową zmienną o nazwie "user_text"
* `=` ustawia wartość tej zmiennej na...
* ... `document.getElementById ("user_text”)`, który przegląda stronę internetową i wskazuje element o identyfikatorze `user_text`, wejściowe pole tekstowe, które wcześniej utworzyliśmy

Korzystając z tych informacji, czy potrafisz wypracować, jak utworzyć nową linię kodu? --- /hint ---

--- hint --- Części kodu, które musisz zmienić, są zaznaczone na `***` w poniższym kodzie:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- Kod, który musisz dodać, jest tutaj:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Chcemy ustawić 'meme_text' `<div>` aby zawierał ten sam tekst, który użytkownik wpisał w polu tekstowym `meme_text`. Dodaj tą linię kodu na dole twojej funkcji JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` odnosi się do tego, co jest wyświetlane wewnątrz `<div>`
  * `.value` odnosi się do tego, co jest wpisywane w polu tekstowym `user_text`

- Na koniec musimy powiedzieć polu tekstowemu, że gdy ktoś do niego napisze, powinno wywołać funkcję, którą właśnie napisaliśmy, aby tekst w memie został zaktualizowany. Znajdź kod dla swojego pola tekstowego i dodaj w **attribute** dla `oninput="update_text()"` tak, aby wyglądało to tak:

  ```html
  Treść mema:<input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Zapisz i odśwież stronę, a następnie spróbuj wpisać w polu tekstowym i zobacz co się stanie. Jeśli twój kod działa, wpisany tekst powinien być wyświetlany jako tekst mema, prawie jak magia!
