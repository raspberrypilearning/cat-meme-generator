## ミームを構築する

ミームを表示する領域を作成する必要があります。 ページが最初に読み込まれたとき、ユーザーが使用したい画像やテキストがわからないため、この領域は空白で始まります。

- `</form>`タグの下に、新しいコード行を追加します：

  ```html
  <div id="meme_text">ここに例文</div>
  ```

  これは`<div>`要素です-最終的に私たちのミームのテキストを保持する非表示のボックスです。 入力ボックスのときと同様、`id`を付けます。

- 次に、別の`<div>`を、前のdivの下に追加します。

  ```html
    <div id="meme_picture"><img src="" height="500" width="600"></div>
    ```

    この`<div>`内には、画像を表示するための別のタグもあります。 `src=""`は、表示する画像を示します。 この場合、ユーザーからの写真がまだないため、画像は空白のままにします。

- 保存して更新します。 画像は空白のボックスになり、サンプルテキストはデフォルトのフォントで表示されます。ミームらしくありません。

    ![サンプルテキストのデフォルトフォント](images/example-text-default.png)

- コンピューターでファイルを使用している場合は、コードで`<head>`セクションを見つけ、次のコードを`<head>`と`</head>`の間に追加します 。 （CodePenを使用している場合は、この手順をスキップしてください。）

  ```html
  <style type="text/css">
  </style>
  ```

- 以下のコードを`<style>`タグの間に貼り付けて、テキストにミームスタイルを付けます。 CodePenを使用している場合は、CSSセクションに貼り付けます。

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

  `left: 15px`と`top: 400px` 行は、テキストがページの左と上からどれだけ離れているかを決定します。 これらの数字を変更して、必要に応じてテキストをミームの別の場所に表示することができます。 CSSスタイルについて詳しく知りたい場合は、[w3schools CSS reference](http://www.w3schools.com/CSSref/) {:target="_blank"}を参照してください。

  ![ミームのテキストの例](images/example-text-memey.png)
