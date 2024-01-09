## Exibir o texto

Até agora, todo o código que escreveste é HTML e CSS, que informa à página como deve ser ** **. Agora vamos adicionar um código JavaScript para informar à página ** o que fazer **.

Quando alguém digita texto na caixa de texto, nós queremos que o seu texto seja exibido dentro do `<div id="meme_text">` que acabamos de criar.

- Se estiveres a usar um ficheiro do teu computador, adiciona estas tags abaixo das tuas tags `<div>` para criar uma secção na qual possa escrever código JavaScript. Se estiveres a usar CodePen, podes saltar esta etapa - escreva seu código na seção JavaScript pronta para ser feita.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Primeiro, escrevemos uma função JavaScript para dizer à página da web que utilize qualquer texto na caixa de entrada e o exiba no "meme_text" `<div>`. Entre as duas tags `<script>` que acabaste de criar, adiciona o código abaixo. Parece bastante diferente do código que escrevemos até agora, porque é JavaScript, que é uma linguagem diferente.

  ```JavaScript
  function update_text (){

  }
  ```

  Acabaste de criar uma função JavaScript chamada `update_text()`. Não há instruções nos colchetes no momento, então a função ainda não fará nada.

- Entre os colchetes `{ }` , adicione o código abaixo para definir a variável ` user_text ` para apontar para a caixa de texto onde o utilizador digita o texto que deseja que apareça no meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Agora é a tua vez de escrever uma linha de código. Abaixo da linha que acabaste de escrever, cria um código para definir a variável chamada ` meme_text ` apontar para o elemento com o ID ` meme_text `, que é onde o texto do meme será exibido. Este é o `<div>` que criamos anteriormente.

--- dicas --- --- dica --- Vamos detalhar o código que escreveste para entender o que ele faz:

* `var user_text` cria uma nova variável com o nome "user_text"
* `=` define o valor dessa variável como...
* ...`document.getElementById("user_text")`, que olha pela página da web e aponta para o elemento com ID `user_text`, a caixa de texto que criamos anteriormente

Usando essas informações, podes descobrir como criar a nova linha de código? --- /dica ---

--- dica --- As partes do código que precisas alterar são destacadas com ` *** ` no código abaixo:
```JavaScript
var *** = document.getElementById ("***");
```
--- /dica ---

--- dica --- O código que precisas adicionar está aqui:

```JavaScript
var meme_text = document.getElementById ("meme_text");
```
--- /dica ---

--- /dicas ---


- Queremos definir o 'meme_text' `<div>` para conter o mesmo texto que o utilizador digitou no ` meme_text ` caixa de texto. Adiciona esta linha de código na parte inferior da sua função JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` refere-se ao que é exibido dentro do `<div>`
  * `.value ` refere-se ao que é digitado na caixa de texto chamada ` user_text `

- Por último, precisamos dizer à caixa de texto que quando alguém digita nela, deve chamar a função que acabamos de escrever para que o texto no meme seja atualizado. Encontre o código para sua caixa de texto e adicione um **atributo ** para `oninput="update_text()"` para que fique assim:

  ```html
  Texto do Meme: <input type="text" id="user_text" maxlength="70" oninput="update_text()"> <p>
  ```

 - Guarda e atualiza a tua página, então tenta digitar na caixa de texto e vê o que acontece. Se o teu código está a funcionar, o texto que você digita deve aparecer como o texto do meme, quase como magia!
