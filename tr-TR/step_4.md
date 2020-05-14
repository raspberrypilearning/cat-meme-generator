## Resim ve metin alma

İnsanların memi yapmak için kendi resimlerini ve metinlerini kullanabilmelerini istiyoruz, bu yüzden bunları sağlamak için bir yola ihtiyacımız var. Kullanıcılarımızın doldurabileceği bir form ekleyelim.

Bilgisayarınızda bir dosya kullanıyorsanız, bu kodu `<body>` ile `</body>`arasına yerleştirin. CodePen kullanıyorsanız, bu kodu HTML bölümüne yerleştirin.

- Formun başlangıcını gösteren `<form>,` ve formun sonunu gösteren `</form>,` etiketlerini ekleyin.

    ```html
    <form>
    </form>
    ```

- `<form>` içinde, mem yazısı yazabilmek için metin kutusu ekleyin:

  ```html
  <form>
  Meme metni: <input type="text" id="user_text" maxlength="70"><p>
  </form>
  ```

- Kodunuzu kaydedin ve oluşturduğunuz kutuyu görmek için tarayıcınızı yenileyin.

    ![First box](images/first-box.png)

- İlk kutunuzun altındaki satırda başka bir giriş kutusu oluşturmak için kod ekleyin. Bu kez giriş kutusu bir metin kutusu değil, mem için görüntü dosyasını seçmek için özel bir kutu olacaktır. Giriş türü `file`ve giriş adı `user_picture`olmalıdır.

--- ipuçları ---

--- ipucu --- İşte zaten yazdığınız kodun yaptığı:

  * `input` kullanıcının bazı veri girişi için bir yol oluşturduğumuzu söylüyor
  * `type = "text"` , verilerin metin olacağını söylüyor
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
