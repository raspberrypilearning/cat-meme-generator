## 显示文本

到目前为止，你编写的所有代码都是HTML和CSS代码，它可以控制页面 **看起来** 是什么样的。 现在，我们将添加一些 JavaScript 代码来告诉页面 **要做什么** 。

当有人在文本框中输入文本时，我们希望他们的文本显示在我们刚创建的 `<div id="meme_text">` 中。

- 如果您正在使用计算机上的文件，请在 `<div>` 标记下添加这些标记，用于添加 JavaScript 代码。 如果你正在使用 CodePen, 你可以跳过这个步骤 - 将你的代码写入准备好的 JavaScript 部分。

  ```html
  <script type="text/javascript">
  </script>
  ```

- 首先，我们将编写一个 JavaScript 函数来告诉网页接受输入框中的任何文本，并将其显示在 "meme_text" `<div>` 中。 在你刚创建的两个 `<script>` 标记之间，添加以下代码。 它看起来与目前为止我们编写的代码完全不同，因为它是JavaScript，这是另一种语言。

  ```JavaScript
  function update_text(){

  }
  ```

  你刚刚创建了一个名为 `update_text()` 的 JavaScript 函数。 目前大括号中没有指令，因此该函数没有任何功能。

- 在大括号 `{ }` 之间， 添加下面的代码来设置变量 `user_text`，它的值是用户在文本框中输入的想要在模因中显示的文本。

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- 现在轮到你自己写一行代码了。 在你刚刚写的行下面，创建代码以设置名为 `meme_text`的变量，指向 ID 为 `meme_text` 的元素，用以控制模因文本的显示位置。 这是我们先前创建的`<div>`。

---提示--- ---提示--- 让我们分解一下你已经编写的代码，以便你了解它的作用：

* `var user_text`创建一个名称为 "user_text" 的新变量
* `=` 将此变量的值设置为...
* ... `document.getElementById("user_text")`，它会遍历网页并指向我们之前创建的输入文本框中 ID 为 `user_text` 的元素。

使用已有的代码，你能想出如何添加新的代码吗？
--- /hint ---


---提示--- 在下面的代码中，你需要更改的代码部分突出显示为 `***`：
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

---提示--- 你需要添加的代码在这里：

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- 我们想要设置 "meme_text" `<div>` 来保存用户输入到`meme_text` 文本框中的文本。 将以下代码行添加到 JavaScript 函数的底部：

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` 是指在 `<div>` 中显示的内容
  * `.value` 指的是在文本框 `user_text` 中输入的内容

- 最后，我们需要告诉文本框，当有人在其中键入内容时，它应该调用我们刚编写的函数，以便更新模因中的文本。 找到你的文本框的代码，并对`oninput="update_text()"` 添加一个 **attribute**，现在看起来像这样：

  ```html
  模因文字：<input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - 保存并刷新页面，然后尝试在文本框中输入内容，然后看看会发生什么。 如果你的代码有效，则你键入的文本应显示为模因文本，几乎就像魔术一样！
