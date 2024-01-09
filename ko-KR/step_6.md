## 텍스트 표시하기

지금까지 작성한 코드는 모두 HTML과 CSS 코드로, 페이지에 **어떻게 표시돼야할 지** 알려줍니다. 이제 우리는 자바스크립트 코드를 추가해 **무엇을 할 지**를 페이지에게 알려줄 것입니다.

누군가가 텍스트 상자에 텍스트를 입력하면 우리는 그 텍스트가 방금 우리가 만든 `<div id="meme_text">`에 나타나게 해야합니다.

- 컴퓨터에서 파일을 작성하고 있는 경우, 다음 태그를 `<div>` 태그 아래에 추가해 자바 스크립트 코드를 추가할 영역을 만듭니다. CodePen을 사용하는 경우 이 단계를 건너뛸 수 있습니다. - 이미 만들어져 있는 자바 스크립트 영역에 코드를 작성하세요.

  ```html
  <script type="text/javascript">
  </script>
  ```

- 먼저 자바 스크립트의 함수를 이용해 웹페이지에게 input 상자에 있는 텍스트를 가져와서 "meme_text" `<div>`에 표시하게 할 겁니다. 방금 만든 두 개의 `<script>` 사이에 다음 코드를 추가하세요: 지금까지 작성했던 코드와는 매우 다르게 생겼습니다. 이 언어는 자바 스크립트로 다른 언어이기 때문이죠.

  ```JavaScript
  function update_text(){

  }
  ```

  방금 자바스크립트 함수인 `update_text()`를 만들었습니다. 중괄호 사이에 아무 코드가 없으므로 이 함수는 아직 아무 일도 하지 않을 겁니다.

- 꼬불꼬불한 중괄호 `{ }` 사이에 다음 코드를 붙여 넣어 `user_text` 변수를 설정하고, 사용자가 밈에 추가할 텍스트를 입력하는 텍스트 상자를 가리키게 하세요.

  ```JavaScript
  var user_text = document.getElementById("user_text");
  ```

- 이제 코드를 작성할 차례입니다. 방금 작성한 줄 아래에 `meme_text` 변수를 설정하고, 밈 텍스트가 나타날 ID `meme_text`를 가리키게 하세요. 이건 우리가 이전에 만든 `<div>` 입니다.

--- hints --- --- hint --- 작성한 코드를 분석하여 그 기능을 이해해 보겠습니다:

* `var user_text`는 "user_text"라는 이름의 변수를 새로 만듭니다.
* `=` 이 변수의 값을 ...으로 설정하세요.
* ...`document.getElementById("user_text")`는 웹페이지에서 ID가 `user_text`인 요소(방금 만든 입력 텍스트 상자)를 찾아 가리킵니다.

이 정보를 이용하여 새 코드 줄을 추가할 방법을 알아낼 수 있겠나요? --- /hint ---

--- hint --- 변경해야 할 코드 부분은 `***`로 강조 표시되어 있습니다:
```JavaScript
var *** = document.getElementById("***");
```
--- /hint ---

--- hint --- 추가해야 하는 코드는 다음과 같습니다:

```JavaScript
var meme_text = document.getElementById("meme_text");
```
--- /hint ---

--- /hints ---


- `meme_text`에 사용자가 입력한 텍스트가 'meme_text' `<div>`에 저장되게 해야합니다. 다음 코드 줄을 JavaScript 함수 하단에 추가합니다.

  ``` JavaScript
  meme_text.innerHTML = user_text.value;
  ```

  * `.innerHTML`는 `<div>`에 보여지는 내용을 나타냅니다.
  * `.value`는 `user_text`이라는 텍스트 상자에 입력된 내용을 나타냅니다.

- 마지막으로 누군가 텍스트 상자에 무언가를 입력하면 방금 작성한 함수를 호출하여 밈의 텍스트가 바뀌도록 해야합니다. 텍스트 박스의 코드를 찾아 **속성**에  `oninput="update_text()"`를 추가해 다음과 같도록 합니다:

  ```html
  Meme text: <input type="text" id="user_text" maxlength="70" oninput="update_text()"><p>
  ```

 - 페이지를 저장하고 새로고침한 다음 텍스트 상자에 입력하고 어떤 일이 발생하는지 확인하십시오. 코드가 제대로 작동하는 경우 입력한 텍스트가 마법처럼 밈 텍스트로 표시되어야합니다!
