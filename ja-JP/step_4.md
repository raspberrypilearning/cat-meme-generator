## 画像とテキストを取得する

ミームを作るために、ユーザが持っている写真とテキストを使えるようにしたいので、それを入力する方法が必要です。 ユーザーが入力できるフォームを追加しましょう。

あなたがコンピュータ上のファイルを使用している場合は、 `<body>` と`</body>`の間にこのコードを配置します。 CodePenを使用している場合は、このコードをHTMLセクションに配置します。

- `<form>` タグを追加してください。これはフォームの開始を示します。 `</form>` はフォームの終了を示します。

    ```html
    <form>
    </form>
    ```

- `<form>`中にテキストボックスを追加して、ミームテキストを入力できるようにします。

  ```html
  <form>
  ミームテキスト： <input type="text" id="user_text" maxlength="70"><p>
  </form>
  ```

- コードを保存し、ブラウザーを更新して、作成したボックスを表示します。

    ![最初のボックス](images/first-box.png)

- 最初のボックスの下の行に別の入力ボックスを作成するコードを追加します。 今回は、入力ボックスはテキストボックスではなく、ミームの画像ファイルを選択するための特別なボックスになります。 The input type should be `file`, and the name of the input should be `user_picture`.

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
