## पाठ (text) को दिखाएं

अब तक आपके द्वारा लिखे गए सभी कोड HTML और CSS के कोड हैं जो पेज को बताता है कि उसे **कैसा दिखना चाहिए** । अब हम पेज को ये बताने के लिए कि **अब क्या करना है** कुछ जावास्क्रिप्ट (JavaScript) के कोड जोड़ने जा रहे हैं ।

जब कोई व्यक्ति टेक्स्ट बॉक्स (text box) में पाठ टाइप करता है तो हम चाहते हैं कि उनका पाठ `<div id="meme_text">` के अंदर प्रदर्शित हो।

- यदि आप अपने कंप्यूटर के फ़ाइल का उपयोग कर रहे हैं तो जावास्क्रिप्ट (JavaScript) कोड लिखने के लिए इन टैग्स (tags) को अपने `<div>` टैग (tag) के नीचे लिखें। यदि आप CodePen का उपयोग कर रहे हैं तो आप इस भाग को छोड़ सकते हैं - बना बनाया जावास्क्रिप्ट (JavaScript) भाग में अपना कोड लिखें।

  ```html
  <script type="text/javascript">
  </script>
  ```

- सबसे पहले हम वेबपेज को इनपुट बॉक्स में किसी भी टेक्स्ट को लेने के लिए एक जावास्क्रिप्ट फंक्शन (JavaScript function) लिखेंगे और इसे हम ऐसे दिखाएंगे "meme_text" `<div>`। आपके द्वारा अभी बनाए गए दो `<script>` टैग्स (tags) के बीच नीचे दिया गया कोड को जोड़ें। यह उस कोड से बहुत अलग है जो हमने अब तक लिखा है क्योंकि यह JavaScript (जावास्क्रिप्ट) है, जो कि एक अलग भाषा है।

  ```JavaScript
  function update_text(){

  }
  ```

  आपने अभी `update_text()` नामक एक जावास्क्रिप्ट फ़ंक्शन (JavaScript function) बनाया है । फिलहाल कोष्ठक (brackets) में कोई निर्देश नहीं हैं इसलिए फ़ंक्शन (function) अभी कुछ भी नहीं करेगा।

- इस तरह दिखने वाले घुंघराले कोष्ठक (brackets)`{ }` के बीच नीचे दिया गया कोड जोड़ें ताकि वेरिएबल (variable) `user_text` उस टेक्स्ट बॉक्स (text box) को संकेत करता है जहां उपयोगकर्ता (user) उस पाठ को टाइप करते है जिसे वे अपने मज़ेदार चित्र (meme) पर दिखाना चाहते हैं।

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- अब कोड की एक पंक्ति लिखने की आपकी बारी है। आपके द्वारा अभि लिखी गई पंक्ति के नीचे `meme_text` नामक वेरियबल (variable) को यह तत्व `meme_text` के तरफ संकेत करने के लिए कोड बनाएं जहां मज़ेदार चित्र (meme) का पाठ (text) दिखेगा । यह `<div>` हमने पहले बनाया था।

--- hints --- --- hint --- आइए अब आपके द्वारा पहले से लिखा गया कोड को तोड़ें ताकि आप समझ सकें कि यह क्या करता है:

* `var user_text` एक नया वेरियबल (variable) बनाता है जिसका नाम है "user_text"
* `=` यह इस वेरिएबल (variable) का एक मूल्य (value) सेट करता है जो...
* ...`document.getElementById("user_text")` जो वेबपेज को छांटता है और `user_text`, वह इनपुट टेक्स्ट बॉक्स (text box) जिसे हमने पहले बनाया था, उसकी तरफ संकेत करता है

इस जानकारी का उपयोग करके, क्या आप कोड की नई लाइन बना सकते हैं? --- /hint ---

--- hint --- कोड के जिन हिस्सों को आपको बदलने की आवश्यकता है, उन्हें `***` के साथ नीचे दिए गए कोड में हाइलाइट (highlight) किया गया है:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- जिस कोड को आपको जोड़ना है वह यहां है:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- हमें 'meme_text' `<div>` को ऐसे सेट करना कि वो वही पाठ दिखाए जो उपयोगकर्ता (user) ने `meme_text` टेस्टबोक्स (text box) में लिखा था । अपने जावास्क्रिप्ट फ़ंक्शन (JavaScript function) के नीचे इस कोड को जोड़ें:

  ``` JavaScript
  meme_text.innerHTML = user_text.value
  ```

  * `.innerHTML` यह बताता है कि `<div>` के अंदर क्या दिखेगा
  * `.value` यह बताता है कि `user_text` नामक टेस्टबोक्स (text box) के अंदर क्या टाइप किया जाता है

- अंत में, हमें टेक्स्ट बॉक्स (text box) को यह बताने की आवश्यकता है कि जब कोई व्यक्ति या उपयोगकर्ता इसमें टाइप करता है तो उसे उस फ़ंक्शन (function) का प्रयोग करना चाहिए जिस्सेकी हमने जो पाठ अभि मज़ेदार चित्र (meme) के लिए टाइप किया था वो अपडेट होजाये । अपने टेक्स्ट बॉक्स (text box) का कोड ढूंढें और `oninput="update_text()"` में एक ** एट्रिब्यूट (attribute) ** जोड़ें ताकी यह अब इस तरह दिखे:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - अपना पेज को सहेजें (save) और रिफ्रेश (refresh) करें फिर अपने टेक्स्ट बॉक्स (text box) में टाइप करके देखें कि क्या होता है। यदि आपका कोड काम कर रहा है तो आपके द्वारा लिखा गया पाठ (text) मज़ेदार चित्र (meme) टेक्स्ट के रूप में दिखाई देना चाहिए, लगभग जादू जैसा!
