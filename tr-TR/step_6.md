## Metni görüntüle

Şimdiye kadar yazdığınız tüm kodlar HTML ve CSS kodudur,  sayfaya ** ın nasıl gözükmesi gerektiğini gösterir **. Şimdi sayfaya ** ne yapacağımızı söylemek için JavaScript kodu ekleyeceğiz ** .

Birisi metin kutusuna metin yazdığında, metninin az önce oluşturduğumuz `<div id="meme_text">` içinde görüntülenmesini isteriz.

- Bilgisayarınızda bir dosya kullanıyorsanız, JavaScript kodunun yazılacağı bir bölüm oluşturmak için bu etiketleri `<div>` etiketlerinizin altına ekleyin. CodePen kullanıyorsanız, bu adımı atlayabilirsiniz - kodunuzu hali hazırda olan JavaScript bölümüne yazın.

  ```html
  <script type="text/javascript">
  </script>
  ```

- İlk olarak, web sayfasına giriş kutusundaki herhangi bir metni almasını ve "meme_text" `<div>`'da gösterilmesini söyleyen bir JavaScript işlevi yazacağız. Yeni oluşturduğunuz iki `<script>` etiket arasına aşağıdaki kodu ekleyin. Şimdiye kadar yazdığımız koddan oldukça farklı görünüyor, çünkü JavaScript, farklı bir dil.

  ```JavaScript
  function update_text(){

  }
  ```

  Az önce `update_text()` adında bir JavaScript işlevi oluşturdunuz. Şu anda parantez içinde talimat yok, bu nedenle işlev henüz hiçbir şey yapmayacak.

- Kullanıcının mem üzerinde görünmesini istediği metni yazdığı metin kutusunu işaret etmek için dalgalı parantezlerin arasına `{ }` , `user_text` değişkenini ayarlamak için aşağıdaki kodu ekleyin.

  ```JavaScript
  var user_text = document.getElementById ("user_text");
  ```

- Şimdi bir kod satırı yazma sırası sizde. Below the line you just wrote, create code to set the variable called `meme_text` to point to the element with the ID `meme_text`, which is where the meme text will display. This is the `<div>` we created earlier.

--- hints --- --- hint --- Let's break down the code you already wrote so that you understand what it does:

* `var user_text` creates a new variable with the name "user_text"
* `=` sets the value of this variable to...
* ...`document.getElementById("user_text")`, which looks through the web page and points to the element with the ID `user_text`, the input text box we created earlier

Using this information, can you work out how to create the new line of code? --- /hint ---

--- hint --- The parts of the code you need to change are highlighted with `***` in the code below:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- The code you need to add is here:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- We want to set the 'meme_text' `<div>` to contain the same text the user has typed into the `meme_text` textbox. Add this line of code to the bottom of your JavaScript function:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` refers to what is displayed inside the `<div>`
  * `.value` refers to what is typed into the text box called `user_text`

- Lastly, we need to tell the text box that when someone types into it, it should call the function we just wrote so that the text in the meme will update. Find the code for your text box and add in an **attribute** for `oninput="update_text()"` so that it now looks like this:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Save and refresh your page, then try typing into your text box and see what happens. If your code is working, the text you type should appear as the meme text, almost like magic!
