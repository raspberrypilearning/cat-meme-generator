## عرض صورة

سنكتب الآن بعض التعليمات البرمجية لالتقاط صورة القط التي حددها المستخدم وعرضها على النص المضحك.

- حدد وظيفة JavaScript جديدة تسمى `update_image`. كن حذراً لكتابة هذا الرمز بعد قوس المجموعة `}` من الدالة السابقة التي أنشأتها.

[[[generic-javascript-create-a-function]]]

- داخل الدالة `update_image` ، أنشئ متغيرين جديدين:

    ```javascript
    var img = document.querySelector('img');
    ```

    يحدد هذا المتغير الأول العلامة الأولى (والوحيدة!) `<img>` في المستند ، حتى نتمكن من إخبار الصفحة بمكان عرض الصورة المحددة.

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    يشير هذا المتغير الثاني إلى ملف صورة القط المحدد.

- قم بتعيين علامة الصورة بحيث تحتوي على الصورة التي قام المستخدم بتحميلها:

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- أضف الآن بعض التعليمات البرمجية لإخبار إدخال الملف لاستدعاء الوظيفة `update_image ()` `onchange` عندما يقوم شخص ما بتحديد ملف.

--- hints ---

--- hint --- تذكر أنك، في الخطوة السابقة، قمت بتسمية الدالة `update_text()` عندما تم كتابة نص جديد في `user_text` مربع الإدخال. باستخدام ما تعلمته آنذاك، هل يمكنك البحث عن كيفية الاتصال بالدالة `update_image()` عندما يختار المستخدم ملف في مربع الادخال `user_file`؟ --- hint/ ---

--- hint --- ستحتاج إلى إضافة `onchange=""` ثم استبدال `***` بالوظيفة التي ترغب في استدعائها:
```javascript
حدد صورة <input type="file" id="user_picture" onchange="***">
```
--- hint/ ---

--- hint --- Find the line of code for the file input box and add `onchange="update_image()"` like this:
```html
Select a picture <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- Save and refresh the page. If your code is working, when you select a picture using the **Select a picture** input box, that picture should appear in the meme box below. If you also type something into the text box, your meme text should appear on top of the picture.

![Finished meme](images/finished-meme.png)
