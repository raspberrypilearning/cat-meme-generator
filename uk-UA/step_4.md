## Отримання малюнка та тексту

We want people to be able to use their own picture and text to make the meme, so we need a way for them to provide these. Let's add a form that our user can fill in.

If you're using a file on your computer, put this code between `<body>` and `</body>`. If you're using CodePen, put this code in the HTML section.

- Add the tags `<form>,` which indicates the start of the form, and `</form>,` which indicates the end of the form.

    ```html
    <form>
    </form>
    ```

- Inside your `<form>`, add a text box so that you can type in the meme text:

  ```html
  <form>
  Meme text: <input type="text" id="user_text" maxlength="70"><p>
  </form>
  ```

- Save your code and refresh your browser to see the box you created.

    ![First box](images/first-box.png)

- Add code to create another input box on the line below your first box. This time the input box will not be a text box, but a special box to select the image file for the meme. The input type should be `file`, and the name of the input should be `user_picture`.

--- hints ---

--- hint --- Here's what the code you already wrote does:

  * `input` says we are creating a way for the user to provide some data
  * `type="text"` says that the data will be text
  * `id="user_text"` gives this particular box a name or ID, a bit like a variable name
  * `maxlength="70"` is optional - it stops you from typing in more than 70 letters so your text doesn't take up space past the bottom of the image
  * The `<p>` tag after the input box adds a paragraph (a bit of space before the next input box)

Can you work out how to create another input box using this information?

--- /hint ---

--- hint ---

You will need to change the parts of the code highlighted with `***` below:

```html
Select a picture <input type="***" id="***"><p>
```

--- /hint ---

--- hint --- Here is the code you need to add:

```html
Select a picture <input type="file" id="user_picture"><p>
```
--- /hint ---

--- /hints ---

- You can use these boxes to type into and to select a file, but nothing will happen yet. **Note**: all images are kept on your computer - this program does not upload anything to the internet.
