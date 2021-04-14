# \<form>

웹 서버에 정보를 제출하기 위한 양식 범위를 정의

- \<form>이 다른 \<form>을 자식 요소로 포함할 수 없음

|속성|의미|값|기본값|
|------|---|---|---|
|action|전송한 정보를 처리할 웹페이지의 URL|URL|
|autocomplete|사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부|`on`, `off`|`on`|
|method|서버로 전송할 HTTP 방식|`Get`, `POST`|`GET`|
|name|고유한 방식의 이름|
|novalidate|서버로 전송시 양식 데이터의 유효성을 검사하지 않도록 지정|
|target|서버로 전송 후 응답받을 방식을 지정|`_self`, `_blank`| `_self`|

```css
form {display: block;}
```

