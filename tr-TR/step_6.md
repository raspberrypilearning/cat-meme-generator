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

- Şimdi bir kod satırı yazma sırası sizde. `meme_text` kimliğine sahip öğeye işaret etmek için az önce yazdığınız satırın altında `meme_text` adlı değişkeni ayarlamak için kod oluşturun, burada mem metni görüntülenecektir. Bu daha önce yarattığımız `<div>`.

--- ipuçları --- --- ipucu --- Ne yazdığınızı anlayabilmeniz için önceden yazdığınız kodu parçalayalım:

* ` var user_text ` "user_text" adıyla yeni bir değişken oluşturur
* `=` bu değişkenin değerini ... olarak ayarlar
* ... ` document.getElementById ( "user_text") ` , web sayfasına bakar ve ` kullanıcı_metni kimliğine sahip öğeye işaret eder ` , daha önce oluşturduğumuz giriş metin kutusu

Bu bilgileri kullanarak yeni kod satırını nasıl oluşturacağınızı çözebilir misiniz? --- /ipucu ---

--- ipucu --- Aşağıdaki kodda, kodda değiştirmeniz gereken kısımlar ` ***` ile vurgulanmıştır:
```JavaScript
var *** = document.getElementById ("***");
```
--- /hint ---

--- ipucu --- Eklemeniz gereken kod burada:

```JavaScript
var meme_text = document.getElementById ("meme_text");
```
--- /hint ---

--- /hints ---


- 'meme_text' `<div>` nın kullanıcının ` meme_text` metin kutusunun içine yazdığı aynı metni içerecek şekilde ayarlamak istiyoruz. Bu kod satırını JavaScript işlevinizin altına ekleyin:

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML` `<div>` 'in içinde görüntüleni simgeler.
  * `.value` ise `user_text` metin kutusuna yazılanları simgeler

- Son olarak, metin kutusuna birisi yazdığında, yazdığımız işlevi çağırması gerektiğini söylemeliyiz, böylece memdeki metin güncellenecektir. Metin kutunuzun kodunu bulun ve `oninput="update_text()"` için bir **attribute** ekleyin, şimdi şöyle görünür:

  ```html
  Mem metni: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - Sayfanızı kaydedin ve yenileyin, ardından metin kutunuza yazmayı deneyin ve ne olacağını görün. Kodunuz çalışıyorsa, yazdığınız metnin mem metni olarak görünmesi gerekir, tıpkı sihir gibi!
