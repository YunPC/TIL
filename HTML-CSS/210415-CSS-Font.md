# Font

## font-size

글자의 크기를 지정(개별)

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `cm`등 단위로 지정|`16px`|
|`%`|부모(상위) 요소의 비율로 지정
|`xx-small`|가장 작은 크기|
|`x-small`|더 작은 크기|
|`small`|더 작은 크기|
|`medium`|중간 크기|`medium`|
|`large`|큰 크기|
|`x-large`|더 큰 크기|
|`xx-large`|가장 큰 크기|
|`smaller`|부모(상위)요소보다 작은 크기|
|`larger`|부모(상위)요소보다 큰 크기|

## line-height

줄 높이(줄 간격)지정

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `cm`등 단위로 지정|
|`normal`|브라우저의 기본 정의를 사용(`1`~`1.4`)|`normal`
|숫자|요소 자체 글꼴 크기의 배수로 지정
|`%`|요소 자체 글꼴 크기의 비율로 지정

## font-family

글꼴(서체)지정


|값|의미|기본값|
|---|---|---|
|글꼴이름|글꼴(서체) 후보 목록을 지정|
|`serif`<br>`sans-serif`<br>`monospace`<br>`cursive`<br>`fantasy`|글꼴 계열 이름을 지정|

### 사용법

```
font-family: [글꼴후보1, 글꼴후보2...], 글꼴계열;
```

```css
.box {
    font-family: Arial, "Open Sans", "돋움", dotum, sans-serif;
}
```

> 글꼴 계열을 필수로 입력해야 한다.

### 글꼴 계열(Generic family)

|계열|의미|
|---|---|
|`serif`|바탕체 계열|
|`sans-serif`|고딕체 계열|
|`monospace`|고정너비(가로폭이 동등한)글꼴 계열|
|`cursive`|필기체 계열|
|`fantasy`|장식(재미있는 문자 표현을 포함하는)글꼴 계열|

## color

문자의 색상을 지정

|값|의미|기본값|
|---|---|---|
|색상|문자의 색상을 지정|`rgb(0,0,0)`|


### 색상 표현

|표현|의미|예시|
|---|---|---|
|색상이름|브라우저에서 제공하는 색상의 이름|`red`, `blue`|
|Hex 색상코드|16 진수 색상(Hexadecimal Colors)|`#000000`|
|RGB|빛의 삼원색|`rgb(255, 255, 255)`|
|RGBA|빛의 삼원색, 투명도|`rgb(255, 0, 0, .5)`|
|HSL|색상, 채도, 명도|`hsl(120, 100%, 50%)`|
|HSLA|색상, 채도, 명도, 투명도|`hsla(120, 100%, 50%, .3)`|

> 위 표는 색상을 이용하는 모든 속성(property)의 값으로 사용할 수 있다.<br>RGBA:Red, Green, Blue, Alpha chnnel<br>HSLA: Hue, Saturation, Lightness, Alpha channel

