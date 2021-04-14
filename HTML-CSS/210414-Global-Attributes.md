# 전역 속성(Global Attributes)

모든 HTML 요소에서 공통적으로 사용 가능한 속성.

## class

공백으로 구분된 요소의 별칭을 지정
CSS 혹은 JS의 요소 선택기를 통해서 요소를 선택하거나 접근

### id

문서에서 고유한 식별자(Idenifier, ID)를 정의.
CSS 혹은 JS의 요소 선택기를 통해서 요소를 선택하거나 접근

### style

요소에 적용할 CSS 선언

### title

요소의 정보(설명)을 지정

### lang

요소의 언어를 지정

```html
<p lang="en">This paragraph is English</p>
<p lang="ko">이 단락은 한글입니다.</p>
<p lang="fr"></p>
```

### tabindex

`Tab`키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정

- 대화형 콘텐츠(Interactive Context)는 기본적으로 코드 순서대로 탭 순서가 지정됨.
- 비대화형 콘텐츠에 **tabindex="0"** 을 지정하여 대화형 콘텐츠와 같이 탭 순서를 사용
- **tabindex="-1"** 을 통해 포커스는 가능하지만 탭 순서에서 제외 가능.
- **tabindex="1"** 이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않음

```html
<h1 tabindex="0">Sign In</h1>
<label>Username: <input type="text"></label>
<label>Password: <input type="password"></label>
<label>PS: <input type="text" tabindex="-1"></label>
<input type="submit" value="Sign In">
```