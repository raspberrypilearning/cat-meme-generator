## Exibir o texto

Até agora, todo o código que você escreveu é HTML e CSS, que informa à página **como ela deve se parecer**. Agora vamos adicionar um código JavaScript para informar à página **o que fazer**.

Quando alguém digitar um texto na caixa de texto, nós queremos que o seu texto seja exibido dentro do `<div id="meme_text">` que acabamos de criar.

- Se você estiver usando um arquivo do teu computador, adiciona estas tags abaixo de suas tags `<div>` para criar uma seção na qual possa escrever código JavaScript. Se você estiver usando o CodePen, você pode pular esta etapa - escreva seu código na seção JavaScript pronta.

  ```html
  <script type="text/javascript">
  </script>
  ```

- Primeiro, escrevemos uma função JavaScript para dizer à página da web que utilize qualquer texto na caixa de entrada e o exiba no "meme_text" `<div>`. Entre as duas tags `<script>` que você acabou de criar, adicione o código abaixo. Ele está bem diferente do código que escrevemos até agora, porque é JavaScript, que é uma linguagem diferente.

  ```JavaScript
  function update_text(){

  }
  ```

  Você acabou de criar uma função JavaScript chamada `update_text()`. No momento, não há instruções entre chaves, portanto a função não fará nada ainda.

- Entre as chaves `{ }`, adicione o código abaixo para definir a variável `user_text` para apontar para a caixa de texto onde o usuário digita o texto que deseja que apareça no meme.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- Agora é sua vez de escrever uma linha de código. Abaixo da linha que você acabou de escrever, crie o código para definir a variável chamada `meme_text` apontar para o elemento com o ID `meme_text`, que é onde o texto do meme será exibido. Este é o `<div>` que criamos anteriormente.

--- hints ---
 --- hint --- Vamos detalhar o código que você já escreveu para entender o que ele faz:

* `var user_text` cria uma nova variável com o nome "user_text"
* `=` define o valor dessa variável como...
* ...`document.getElementById("user_text")`, que olha pela página da web e aponta para o elemento com ID `user_text`, a caixa de texto que criamos anteriormente

Usando essas informações, você pode descobrir como criar a nova linha de código?
--- /hint ---


--- dica --- As partes do código que você precisa alterar são destacadas com `***` no código abaixo:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- O código que você precisa adicionar está aqui:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- Queremos definir o 'meme_text' `<div>` para conter o mesmo texto que o usuário digitou no `meme_text` caixa de texto. Adicione esta linha de código na parte inferior da sua função JavaScript:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` refere-se ao que é exibido dentro do `<div>`
  * `.value` refere-se ao que é digitado na caixa de texto chamada `user_text`

- Por fim, precisamos informar à caixa de texto que, quando alguém digitar nela, ela deverá chamar a função que acabamos de escrever para que o texto no meme seja atualizado. Encontre o código para sua caixa de texto e adicione um **atributo** para `oninput="update_text()"` para que agora fique assim:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Salve e atualize sua página, tente digitar na sua caixa de texto e veja o que acontece. Se o seu código estiver funcionando, o texto digitado deve aparecer como o texto do meme, quase como mágica!
