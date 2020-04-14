## Constroi o meme

Precisamos criar uma área onde o meme será exibido. Essa área começará em branco porque, quando a página for carregada pela primeira vez, não saberemos qual imagem ou qual texto a pessoa deseja usar.

- Debaixo da ` </form>` tag, adicione uma nova linha de código:

  ```html
  <div id="meme_text">Exemplo de texto aqui</div>
  ```

  Este é um elemento `<div>` - é uma caixa invisível que eventualmente terá o texto do nosso meme. Demos a ele um Id ` ` assim como fizemos nas caixas de entrada.

- Agora adicione outro `<div>` abaixo do anterior:

  ```html
    <div id="meme_picture"><img src="" height="500" width="600"></div>
    ```

    Dentro desta `<div>`, há também outra tag que exibe uma imagem. `src=""` indica qual imagem exibir. Nesse caso, deixamos a imagem em branco, porque ainda não temos a imagem do utilizador.

- Guardar e Atualizar. A imagem será uma caixa em branco e o texto de exemplo será exibido na fonte padrão, que não é muito parecido com um meme:

    ![Exemplo de fonte padrão de texto](images/example-text-default.png)

- Se você estiver usando um arquivo em seu computador, encontre a seção `<head>` do seu código e adicione este código entre `<head>` e `</head>`. (Pule este passo se estiveres a usar o CodePen.)

  ```html
  <style type="text/css">
  </style>
  ```

- Copia o código abaixo entre as tags `<style>` para dar ao seu texto um estilo de meme. Se estiveres a usar o CodePen, coloca este código na secção CSS.

    ```css
    #meme_text {
        background-color: transparent;
        font-size: 40px;
        font-family: "Impact";
        color: white;
        text-shadow: black 0px 0px 10px;
        width: 600px;
        position: absolute;
        left: 15px;
        top: 400px;
    }
    ```

  As linhas `left: 15 px` e `top: 400 px` determinam a que distância o texto está da esquerda e da parte superior da página. Podes alterar esses números para fazer o texto aparecer em um lugar diferente no teu meme, se quiseres. Se gostavas de saber mais sobre estilos CSS, visita a referência CSS [w3schools ](http://www.w3schools.com/CSSref/){:target="_blank"}.

  ![Exemplo de texto no meme](images/example-text-memey.png)
