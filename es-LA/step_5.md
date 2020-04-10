## Construye el meme

Necesitamos crear una área donde se mostrará el meme. Esta área comenzará en blanco porque cuando la página se carga por primera vez, no sabremos qué imagen o qué texto quiere usar la persona.

- Debajo de la etiqueta `</form>`, añade una nueva línea de código:

  ```html
  <div id="meme_text">Texto de ejemplo aquí</div>
  ```

  Este es un elemento `<div>`: es un cuadro invisible que al final contendrá el texto para nuestro meme. Le hemos dado una `id` igual como hicimos con los cuadros de input (entrada).
  
- Ahora añade otro `<div>` debajo del anterior: 
     
  ```html
    <div id="meme_picture"><img src="" height="500" width="600"></div>
    ```
    Dentro de este `<div>`, hay también otra etiqueta que muestra una imagen. `src=""` indica que imagen se mostrará. En este caso, hemos dejado la imagen en blanco, porque todavía no tenemos la imagen del usuario.

- Guarda y actualiza. La imagen será un cuadro en blanco y el texto de ejemplo se mostrará en la fuente predeterminada, lo que no es normal en un meme:

    ![Texto de ejemplo con fuente predeterminada](images/example-text-default.png)
  
- Si estás utilizando un archivo en tu ordenador, busca la sección `<head>` en tu código y añade este código entre `<head>` y `</head>`. (Omite este paso si estás usando CodePen.) 
      
  ```html
  <style type="text/css">
  </style>
  ```
  
- Pega el código debajo de las etiquetas `<style>` para dar a tu texto un estilo meme. Si estás usando CodePen, pégalo en la sección CSS. 
      
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
   
  Las líneas de código `left: 15px` y `top: 400 px` determinan qué tan lejos de la izquierda y la parte superior de la página aparecerá el texto. Si quieres puedes modificar estos números para que el texto aparezca en un lugar diferente en tu meme. Si quieres saber más sobre los estilos CSS, visita la referencia [w3schools CSS](http://www.w3schools.com/CSSref/){:target="_blank"}.

  ![Texto de ejemplo en el meme](images/example-text-memey.png)

