## 显示图像

现在，我们将编写一些代码来回去用户选择的猫图像并将其显示在模因上。

- 定义一个新的 JavaScript 函数，名为 `update_image` 。 请注意在你创建的上一个函数的大括号 `}` 之后输入此代码。

[[[generic-javascript-create-a-function]]]

- 在 `update_image` 函数内，创建两个新变量：

    ```javascript
    var img = document.querySelector('img');
    ```

    这个变量选择文档中的第一个(也是唯一的) `<img>` 标签，这样我们就可以告诉页面在何处显示所选图像。

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    第二个变量指向所选的猫图片文件。

- 设置 img 标签以包含用户上传的图片：

    ```javascript
    img.src = window.URL.createObjectURL(file);
    ```

- 现在添加一些代码，告诉输入控件在选择文件后，也就是 `onchange` 发生时调用 `update_image()` 函数。

--- hints ---

--- hint--- 
记住，在之前步骤中，当新文本被写入`user_text` 输入框时，你调用了`update_text()` 函数。 使用所学的知识， 当用户在 `user_file` 输入框中选择一个文件时，你会调用函数`update_image()`吗？
--- /hint ---


--- hint --- 

你将需要添加 `onchange=""` 然后用你要调用的函数替换`***`：
```javascript
选择图片 <input type="file" id="user_picture" onchange="***">
```
--- /hint ---

--- hint --- 

找到文件输入框的代码行，并添加`onchange="update_image()"` 像这样：
```html
选择图片 <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- 保存并刷新页面。 如果代码有效，则在选择图片时使用 **选择图片** 输入框，该图片应显示在下面的模因框中。 如果你还在文本框中键入了内容，则你的模因文本应出现在图片顶部。

![完成的模因](images/finished-meme.png)
