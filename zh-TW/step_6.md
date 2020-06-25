## 顯示文字

到目前為止，你所編寫都是用來決定頁面**外觀** 的HTML和CSS程式碼。 現在，我們將要來加入一些JavaScript程式碼來命令此頁面**要做的事情**。

當有使用者在文字框中輸入文字時，我們希望他們的文字顯示在我們剛才建立的`<div id="meme_text">`標籤內。

- 如果你想要使用電腦中的檔案，請將這些標籤加入在你的`<div>`標籤下方來建立一個撰寫JavaScript程式碼的區塊。 如果您使用的是CodePen，則可以跳過此步驟-在現成的JavaScript區塊中編寫你的程式碼。

  ```html
  <script type="text/javascript">
  </script>
  ```

- 首先，我們將編寫一個JavaScript函數來告訴網頁接受輸入框中的任何文本，並將其顯示在“ meme_text” `<div>`中。 在你剛建立的兩個`<script>`標籤之間，加入以下程式碼。 這些看起來和我們截至目前所編寫的程式碼很不一樣，因為這是JavaScript，一個不一樣的程式語言。

  ```JavaScript
  function update_text(){

  }
  ```

  你剛剛建立了一個叫做 `update_text()` 的JavaScript函數。 目前這個函數不會做任何事情，因為在大括號裡面並沒有任何指令。

- 在大括號 `{ }` 之間，加入以下程式碼來設定變數 `user_text` ，指向使用者輸入的文字框，也就是使用者想要在迷因中顯示的文字。

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- 現在，輪到你來寫一行程式碼了！ 在你剛編寫的那行程式碼下面，建立新的程式碼來設定名為 ` meme_text` 的變數，指向ID為 ` meme_text` 的元素，也就是迷因文字的顯示位置。 這是我們之前建立的`<div>`標籤。

---提示--- ---提示--- 讓我們拆解一下您已經編寫的程式碼，來讓你了解它的作用：

* ` var user_text ` 建立了一個名稱為 “ user_text” 的新變數
* `=` 請將此變數的值設定為...
* ...`document.getElementById("user_text")`，這將會瀏覽整個網頁並指向ID為 `user_text` 的元素，也就是我們之前建立的文字輸入框。

透過以上這些資訊，你可以想出如何編寫新的一行程式碼嗎？ --- /hint ---

---提示--- 你需要更改的部分程式碼已經透過 ` ***` 標籤標示在下面的程式碼中：
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

---提示--- 你需要新增的程式碼在這裡：

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- 我們要設置“ meme_text” `<div>`來容納使用者在` meme_text` 文字框中輸入的相同文字。 將以下這行程式碼新增到你的JavaScript函數的底部：

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` 指向在`<div>`標籤內部顯示的內容
  * `.value` 指向在名為 `user_text` 文字框中輸入的內容

- 最後，我們需要命令文字框，當有人輸入內容時，文字框應該要呼叫我們剛才編寫的函數，如此迷因中的文字才會被更新。 找出你的文字框的程式碼，並新增一個 **attribute** 帶有 `oninput="update_text()"`，應該看起來會像這樣：

  ```html
  迷因的文字: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - 保存並重新整理頁面，然後嘗試在文字框中輸入內容，看看會發生什麼事情。 如果你的程式碼可以成功運作，你剛才輸入的文字應該會出現在迷因文字裡，就像是變魔術一樣！
