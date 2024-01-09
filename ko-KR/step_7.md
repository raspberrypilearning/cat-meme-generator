## 이미지 표시하기

이제 사용자가 선택한 고양이 이미지를 가져와 밈에 표시하는 코드를 작성합니다.

- 새 자바스크립트 함수 `update_image`를 정의합니다. 이전에 만든 함수에서의 닫는 중괄호 `}` 뒤에 이 코드를 입력해야합니다.

[[[generic-javascript-create-a-function]]]

- `update_image` 함수 안에 두개의 새 변수를 만듭니다.

    ```javascript
    var img = document.querySelector('img');
    ```

    이 첫번째 변수는 첫 번째 `<img>`태그 만을 선택해서 이미지를 표시할 위치를 우리가 정할 수 있도록 합니다.

    ```javascript
    var file = document.querySelector('input[type=file]').files[0];
    ```

    이 두번째 변수는 고양이 사진 파일을 가리킵니다.

- 사용자가 업로드한 사진을 갖도록 이미지 태그를 설정합니다.

    ```javascript
    img.src =  window.URL.createObjectURL(file);
    ```

- 이제 코드를 조금 추가해서 누군가 파일을 설정해서 입력된 파일이 `update_image()`함수와 `onchange`를 호출하도록 합니다.

--- hints ---

--- hint --- 이전 단계에서 `user_text` 입력 상자에 새 텍스트를 쓸 때, `update_text()` 함수를 호출했습니다. 그 때 배운 것을 이용하여 사용자가 `user_file` 입력 상자에서 파일을 선택할 때, `update_image()` 함수를 호출하는 방법을 알아낼 수 있나요? --- /hint ---

--- hint --- `onchange=""`를 추가해서 `***`를 호출하고자 하는 함수로 바꿔야합니다:
```javascript
이미지를 선택하세요 <input type="file" id="user_picture" onchange="***">
```
--- /hint ---

--- hint --- 파일 입력 상자 코드를 찾아 다음과 같이 `onchange="update_image()"`를 추가합니다:
```html
이미지를 선택하세요 <input type="file" id="user_picture" onchange="update_image()">
```

--- /hint ---

--- /hints ---

- 페이지를 저장하고 새로고칩니다. 코드가 작동하는 경우 **이미지를 선택하세요** 입력 상자를 사용하여 그림을 선택하면, 해당 그림이 아래 밈 상자에 나타납니다. 또 무언가를 텍스트 상자에 입력하면 밈 텍스트도 이미지 상단에 나타날 것입니다.

![완성된 밈](images/finished-meme.png)
