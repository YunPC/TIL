# CSS

## 이보다 쉬울 수 없는 CSS 문법

CSS 문법은 HTML 보다 더 쉽다.

```css
div {
    font-size: 20px;
    color: red;
}

/* 다음과 같이 이해할 수 있다 */
선택자 {
    속성: 값;
    속성: 값;
}
```

## 선택자의 역할

선택자는 HTML에 스타일(CSS)를 적용하기 위해 HTML의 특정한 요소를 선택하는 사인(sign)이다. "빨강 글자색(CSS, `color: red;`)을 저기 제목(HTML, `<h1></h1>`)에 적용하겠어!"와 같이 적용할 스타일을 속성(`color`)과 값(`red`)으로 나타내고 적용할 대상(H1, P)을 선택자로 나타낸다.

위 내용을 코드로 구성하면 다음과 같다.

```html
<div>
    <h1>제목..</h1>
    <p>본문..<p>
</div>
```

```css
h1 {
    color: red;
}
p {
    color : blue;
}
```