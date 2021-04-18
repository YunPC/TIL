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