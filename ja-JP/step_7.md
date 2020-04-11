## 画像を表示する

次に、ユーザーが選択した猫の画像を取得してミームに表示するコードを記述します。

- `update_image`という新しいJavaScript関数を定義します 。 以前に作成した関数の閉じ中括弧`}`の後にこのコードを入力するように注意してください。

[[[generic-javascript-create-a-function]]]

- ` update_image`関数の中に、2つの新しい変数を作成します。

    ```javascript
    var img = document.querySelector('img');
    ```

    この最初の変数は、ドキュメント内の最初の（そして唯一の！）`<img>`タグを選択します。これにより、選択した画像を表示する場所をページに伝えることができます。

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    この2番目の変数は、選択した猫の画像ファイルを指します。

- ユーザーがアップロードした写真を含むようにイメージタグを設定します。

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- 次に、誰かがファイルを選択したとき `onchange`イベントで 、`update_image()`関数を呼び出すように指示するコードを追加します。

--- hints ---

--- hint --- Remember that, in the previous step, you called the function `update_text()` when new text was written into the `user_text` input box. Using what you learned then, can you work out how to call the function `update_image()` when the user selects a file in the `user_file` input box? --- /hint ---

--- hint --- You will need to add `onchange=""` and then replace the `***` with the function you would like to call:
```javascript
Select a picture <input type="file" id="user_picture" onchange="***">
```
--- /hint ---

--- hint --- Find the line of code for the file input box and add `onchange="update_image()"` like this:
```html
Select a picture <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- Save and refresh the page. If your code is working, when you select a picture using the **Select a picture** input box, that picture should appear in the meme box below. If you also type something into the text box, your meme text should appear on top of the picture.

![Finished meme](images/finished-meme.png)
