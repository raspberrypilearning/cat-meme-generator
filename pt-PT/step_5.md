## Constroi o meme

Precisamos criar uma área onde o meme será exibido. Essa área começará em branco porque, quando a página for carregada pela primeira vez, não saberemos qual imagem ou qual texto a pessoa deseja usar.

- Debaixo da ` </form>` tag, adicione uma nova linha de código:

  ```html
  <div id="meme_text">Exemplo de texto aqui</div>
  ```

  Este é um elemento `<div>` - é uma caixa invisível que eventualmente terá o texto do nosso meme. Demos a ele um Id ` ` assim como fizemos nas caixas de entrada.

- Now add another `<div>` below the previous one:

  ```html
    <div id="meme_picture"><img src="" height="500" width="600"></div>
    ```

    Inside this `<div>`, there's also another tag which displays an image. `src=""` indicates which image to display. In this case, we've left the image blank, because we don't yet have the picture from the user.

- Save and refresh. The picture will be a blank box and the example text will display in the default font, which isn't very meme-like:

    ![Example text default font](images/example-text-default.png)

- If you're using a file on your computer, find the `<head>` section in your code and add this code between `<head>` and `</head>`. (Skip this step if you're using CodePen.)

  ```html
  <style type="text/css">
  </style>
  ```

- Paste the code below between the `<style>` tags to give your text a meme style. If you're using CodePen, paste it into the CSS section.

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

  The `left: 15px` and `top: 400px` lines determine how far the text is from the left and the top of the page. You can alter these numbers to make the text appear in a different place on your meme if you like. If you would like to know more about CSS styles, visit the [w3schools CSS reference](http://www.w3schools.com/CSSref/){:target="_blank"}.

  ![Example text in meme](images/example-text-memey.png)
