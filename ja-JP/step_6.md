## テキストを表示する

これまでのところ、作成したコードはすべてHTMLおよびCSSコードであり、これはページの**見た目**を表現しています 。 次に、JavaScriptコードを追加して、ページに**何をすべきか**を伝えます 。

テキストボックスにテキストを入力すると、作成した`<div id="meme_text">`内にテキストが表示されます。

- コンピューターでファイルを使用している場合は、これらのタグを`<div>`タグの下に追加して、JavaScriptコードを書き込むセクションを作成します。 CodePenを使用している場合は、このステップをスキップできます。既製のJavaScriptセクションにコードを記述してください。

  ```html
  <script type="text/javascript">
  </script>
  ```

- まず、JavaScript関数を記述して、Webページに入力ボックス内のテキストを取得して、"meme_text"`<div>`に表示するよう指示します。 作成した2つの`<script>`タグの間に、以下のコードを追加します。 JavaScriptは別の言語であるため、これまでに作成したコードとはかなり異なります。

  ```JavaScript
  function update_text(){

  }
  ```

  `update_text()`というJavaScript関数を作成しました 。 現時点では括弧内に指示がないため、関数はまだ何もしません。

- 中括弧`{ }`の間 に、以下のコードを追加して、変数` user_text`を設定します。この変数は、ユーザーがミームに表示するテキストを入力するテキストボックスをポイントします。

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- 今度はあなたがコード行を書く番です。 先ほど書いた行の下に、`meme_text`という変数を用意し、IDが`meme_text`である要素をポイントするようにします。これは、ミームテキストが表示される場所です。 これは、以前に作成した`<div>`です。

--- hints --- --- hint --- すでに記述したコードを分解して、その機能を理解しましょう。

* `var user_text` は「user_text」という名前の新しい変数を作成します
* `=` (イコール記号) は、変数に次の値をセットします。
* `document.getElementById("user_text")`、これはウェブページ全体を調べ、ID `user_text`の要素をポイントします。 user_textは、以前に作成した入力テキストボックスです。

この情報を使用して、新しいコード行を作成する方法を理解できますか？ --- /hint ---

--- hint --- 変更する必要があるコードの部分は、以下のコードで`***`で強調表示されています：
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- 追加する必要があるコードは次のとおりです。

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- ユーザーが`meme_text`テキストボックスに入力したのと同じテキストになるように'meme_text' `<div>`を設定することにします。 次のコード行をJavaScript関数の下部に追加します。

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * ` .innerHTML` は、 `<div>`内に表示されるものを参照します。
  * `.value`は、`user_text`というテキストボックスに入力した内容を参照します

- 最後に、誰かがテキストボックスに入力したときに、先ほど書いた関数を呼び出してミーム内のテキストが更新されるようにテキストボックスに伝える必要があります。 テキストボックスのコードを見つけて、**属性**に` oninput&#61"update_text()"`を追加します。次のようになります。

  ```html
  ミームテキスト：< input type="text" id="user_text" maxlength="70" oninput="update_text()"> < p>
  ```

 - ページを保存して更新してから、テキストボックスに入力してみてください。 コードが機能している場合、入力したテキストは、まるで魔法のようにミームテキストとして表示されます。
