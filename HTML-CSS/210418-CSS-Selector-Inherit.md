# CSS / 개요, 선택자, 상속

## 문법

```
선택자 {속성: 속성값; 속성: 속성값;}
```

> 옆으로 길게 작성하는 방식은 '가독성'이 떨어진다. 몇몇 경우를 제외하고는 아래의 방식을 사용하자.

```
선택자 {
    속성: 속성값;
    속성: 속성값;
}
```

## 선택자(Selector)의 역할

속성과 값을 지정할 대상을 검색

```html
<div>HELLO</div>
<span>HELLO</span>
```

```css
div {
    color: red;
}
```

> 첫번째 요소가 검색되어 속성과 값이 적용된다.

## 속성(Property)과 값(Value)의 역할

검색된 대상에 지정될 CSS 명령

```html
<div>HELLO</div>
```

```css
div {
    color: red;
    font-size: 20px;
    font-weight: bold;
}

/* 글자색: 빨강; */
/* 글자크기: 20px; */
/* 글자두께: 두껍게; */
```

> 선택자로 검색한 대상에 각 속성과 값을 삽입하여 스타일을 지정한다.

## /* Comment * /

문서 내 수정사항이나 설명 등을 작성(주석)

```css
/* HEADER SECTION */
header {
    color : #FF0000; 
}
```

## 선언 방식

### 인라인(in-line) 방식

HTML 요소(태그)의 'style' 속성에 직접 작성하는 방식

```html
<div style="color: red; font-size: 20px font-weight: bold;">HELLO</div>
```

> 이 방식은 '선택자'가 필요하지 않다.

### 내장(embedded) 방식

HTML `<style></style>` 안에 작성하는 방식

```html
<head>
    <style>
    div {
        color: red;
        font-size: 20px;
        font-weight: bold;
    }
    </style>
</head>
<body>
    <div>HELLO</div>
</body>
```

### 링크(link)방식

HTML `<link>`를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식

```html
<head>
    <link rel="stylesheet" href="css/common.css">
</head>
<body>
    <div>HELLO</div>
<body>
```

```css
/* common.css */
div {
    color: red;
    font-size: 20px;
    font-weight: bold;
}
```

> 이 방식의 사용을 추천한다.

### @import 방식

CSS `@import`를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식

```html
<head>
    <link rel="sytlesheet" href="css/common1.css">
</head>
<body>
    <div>HELLO</div>
</body>
```

```css
/* common1.css */
@import url("./common2.css");
```

```css
/* common2.css */
div {
    color: red;
    font-size: 20px;
    font-weight: bold;
}
```

## 선택자(Selector)

### 기본 선택자(Basic Selectors)

1. 전체 선택자(Universal Selector)
    - (요소 내부의) 모든 요소를 선택
    ```
    *
    ```

    ```css
    * {
        color: red;
    }
    ```

    ```html
    <div>
        <ul>
            <li>사과</li>
            <li>딸기</li>
            <li>오렌지</li>
        </ul>
        <div>당근</div>
        <p>토마토</p>
        <span>오렌지</span>
    </div>
    ```

2. 태그 선택자(Type Selector)
    - 태그이름이 `E`인 요소 선택
    ```
    E
    ```

    ```css
    li {
        color: red;
    }
    ```

    ```html
    <div>
        <ul>
            <li>사과</li>
            <li>딸기</li>
            <li>오렌지</li>
        </ul>
        <div>당근</div>
        <p>토마토</p>
        <span>오렌지</span>
    </div>
    ```

3. 클래스 선택자(Class Selector)
    - HTML `class`속성의 값이 `E`인 요소 선택
    ```
    .E
    ```

    ```css
    .orange{
        color: red;
    }
    ```

    ```html
    <div>
        <ul>
            <li>사과</li>
            <li>딸기</li>
            <li class="orange">오렌지</li>
        </ul>
        <div>당근</div>
        <p>토마토</p>
        <span class="orange">오렌지</span>
    </div>
    ```

4. 아이디 선택자(ID Selector)
    - HTML `id`속성의 값이 `E`인 요소 선택
    ```
    #E
    ```

    ```css
    #orange {
        color: red;
    }
    ```

    ```html
    <div>
        <ul>
            <li>사과</li>
            <li>딸기</li>
            <li id="orange" class="orange">오렌지</li>
        </ul>
        <div>당근</div>
        <p>토마토</p>
        <span class="orange">오렌지</span>
    </div>
    ```

### 복합 선택자(Combinators)

#### 일치 선택자(Basic Combinator)
`E`와 `F`를 동시에 만족하는 요소 선택
```
EF
```

```css
span.orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li>
        <li>딸기</li>
        <li class="orange">오렌지</li>
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
</div>
```

#### 자식 선택자(Child Combinator)

`E`의 자식 요소 `F`를 선택
```
E > F
```

```css
ul > .orange{
    color : red;
}
```

```html
<div>
    <ul>
        <li>사과</li>
        <li>딸기</li>
        <li class="orange">오렌지</li>
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
</div>
```

#### 후손(하위) 선택자(Descendant Combinator)

`E`의 후손(하위) 요소 `F`를 선택

```
E F
```

> `띄어쓰기`가 선택자의 기호로 사용된다.

```css
div .orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li>
        <li>딸기</li>
        <li class="orange">오렌지</li>
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
</div>
```

#### 인접 형제 선택자(Adjacent Sibling Combinator)

`E`의 다음 형제 요소 `F` 하나만 선택

```
E + F
```

```css
.orange + li {
    color: red;
}
```

```html
<ul>
    <li>딸기</li>
    <li>수박</li>
    <li class="orange">오렌지</li>
    <li>망고</li>
    <li>사과</li>
</ul>
```

#### 일반 형제 선택자(General Sibling Combinator)

`E`의 다음 형제 요소 `F`모두 선택

```
E - F
```

```css
.orange - li {
    color: red;
}
```

```html
<ul>
    <li>딸기</li>
    <li>수박</li>
    <li class="orange">오렌지</li>
    <li>망고</li>
    <li>사과</li>
</ul>
```

## 상속(Inheritance)

```css
.ecosystem{
    color: red;
}
```

```html
<div class="eciosystem">생태계
    <div class="animal">동물
        <div class="tiger">호랑이</div>
        <div class="lion">사자</div>
        <div class="elephant">코끼리</div>
    </div>
    <div class="plant">식물</div>
</div>
```

> 생테계(`.ecosystem`)에 적용된 색상이, 하위 요소들에게도 적용된다.

### 상속되는 속성들(properties)

- font
    + font-size
    + font-weight
    + line-height
    + font-family
- color
- text-align
- text-indent
- text-decoration
- letter-spacing
- opacity
- etc..

### 강제 상속

```html
<div class="parent">
    <div class="child"></div>
</div>
```

```css
.parent{
    position: absolute;
}
.child {
    position: inherit;
}
```

> 상속되지 않는 속성(값)도 `inherit`이라는 값을 사용하여 '부모'에서 '자식'으로 강제 상속 시킬 수 있다. '자식'을 제외한 '후손'에게는 적용되지 않으며, 모든 속성이 강제 상속을 사용할 수 있는 것은 아니다.

## 우선순위

```html
<body>
    <!-- 인라인 선언방식 -->
    <div id="color_yellow" class="color_green" style="color: orange;">Hellow world!</div>
</body>
```

```css
div {color: red !important;}

#color_yellow {color: yellow;}

.color_green {color: green;}

div {color: blue;}

* {color: darkblue;}

body {color: violet;}
```

### 우선순위 결정

같은 요소가 여러 선언의 대상이 될 경우,
어떤 선언의 CSS 속성(property)을 우선 적용할지 결정하는 방법

1. 명시도 점수가 높은 선언이 우선(명시도)
2. 점수가 같은 경우, 가장 마지막에 해석(늦게 작성한)되는 선언이 우선(우선 순서)
3. 명시도는 '상속' 규칙보다 우선(중요도)
4. `!important`가 적용된 선언 방식이 다른 모든 방식보다 우선(중요도)

> 우선순위에는 '중요도,명시도,선언 순서'의 개념이 있다.

1. 가장 중요(`!important`)
모든 선언을 무시하고 가장 우선
점수 : `inf` pt

```css
div {
    color: red !important; 
}
```

2. 인라인 선언 방식(Style Attribute)

인라인 선언(HTML `style` 속성을 사용)
점수: `1000`pt

```html
<div style="color: orange;">HELLO WORLD</div>
```

3. 아이디(ID Selector)

아이디 선택자
점수: `100`pt

```css
#color_yellow {
    color: yellow;
}
```

4. 클래스(Class Selector)

클래스 선택자
점수: `10`pt

```css
.color_green{
    color: green;
}
```

5. 태그(Type Selector)

태그 선택자
점수: `1`pt

```css
span {
    color: blue;
}
```

6. 전체(Universal Selector)

전체 선택자
점수: `0`pt

```css
* {
    color: darkblue;
}
```

7. 상속(CSS Inheritance)

상속 받은 속성은 항상 우선하지 않음
점수: 계산하지 않음

```css
body {
    color: violet;
}
```

계산해 보자!

```css
/* 21pt */
.list li.item{color: red;}

/* 21pt */
.list li:hover {color: red;}

/* 11pt */
.box::before {content: "Good"; color: red;}

/* 101pt */
#submit span{color : red;}

/* 22pt */
header .menu li:nth-child(2) {color:red;}

/* 1pt */
h1 {color: red;}

/* 10pt */
:not(.box) {color: red;}

/* 1pt */
:not(span) {color: red;}
```

> `hover`처럼 '가상 클래스'는 '클래스' 선택자의 점수(`10pt`)를 가지며, `::before`처럼 '가상 요소'는 '태그' 선택자의 점수(`1pt`)를 가진다. 부정 선택자 `:not()`은 점수를 가지지 않는다.

## 가상 클래스 선택자(Pseudo-Classes Selectors)

### HOVER

`E`에 마우스(포인터)가 올라가 있는 동안에만 `E` 선택
```
E:hover
```

### ACTIVE

`E`를 마우스로 클릭하는 동안에만 `E` 선택

```
E:active
```

### FOCUS

`E`가 포커스 된 동안에만 `E` 선택
```
E:focus
```

> 대화형 콘텐츠에서 사용 가능

## 가상 요소 선택자(Pseudo-Elements Selectors)

### BEFORE

`E`요소 **내부의 앞**에, 내용(content)를 삽입
```
E::before
```

### AFTER

`E` 요소 **내부의 뒤**에, 내용(content)을 삽입

```
E::after
```