# CSS/ 속성 - 띄움(정렬), 위치

## float

요소를 좌우 방향으로 띄움(수평 정렬)

|값|의미|기본값|
|---|---|---|
|`none`|요소 띄움 없음|`none`|
|`left`|왼쪽으로 띄움|
|`right`|오른쪽으로 띄움|

### 사용법

```
float: 방향;
```

```css
img{
    float:left;
}
```

### 단순 띄움

> 요소에 `float` 속성을 적용하면, 적용된 요소 주변으로 문자(text)가 흐르게 된다.

### 단순 해제

clear:left;, clear:right;

### 수평 정렬

> 각 요소에 `float`속성이 적용되면 차례로 **'정렬'** 된다.

### 정렬 해제

clear:left; clear: right;

### float 해제

`float` 속성이 적용된 요소의 주위로 다른 요소들이 흐르게 되는데 이를 방지하기 위해 속성을 '해제'해야 함

1. 형제요소에 `clear:(left, right, both)` 추가하여 해제
2. 부모요소에 `overflow: (hidden, auto)` 추가하여 해제
3. 부모요소에 `clearfix`클래스 추가형 해제(**추천!**)

#### 형제 요소에서 해제

`float` 속성이 추가된 요소의 다음 형제요소에 `clear`속성 추가

```html
<div class="float-left"></div>
<div class="float-left"></div>
<div class="next"></div>
```

```css
.float-left {
    width: 100px;
    height: 100px;
    background: red;
    float: left;
}
.next {
    clear: both;
}
```

#### 부모 요소에서 해제 1

`float`속성이 추가된 요소의 부모요소에 `overflow`속성 추가

```html
<div class="parent">
    <div class="child"></div>
    <div class="child"></div>
</div>
```

```css
.parent {
    overflow: hidden;
}
.child {
    float: left;
}
```

#### 부모 요소에서 해제2 (추천!)

`float`속성이 추가된 요소의 부모요소에 미리 지정된 `clearfix` 클래스 추가
```html
<div class="parent clearfix">
    <div class="child"></div>
    <div class="child"></div>
</div>
```

```css
.clearfix::after {
    content: "";
    clear:both;
    display: block;
}
.child {
    float:left;
}
```

## display 수정

`float`속성이 추가된 요소는 `display`속성의 값이 대부분 `block`으로 수정됨

|지정값|변화값|
|---|---|
|`inline`|`block`|
|`inline-block`|`block`|
|`inline-table`|`block`|
|`table-row`|`block`|
|`table-row-group`|`block`|
|`table-column`|`block`|
|`table-column-group`|`block`|
|`table-cell`|`block`|
|`table-caption`|`block`|
|`table-header-group`|`block`|
|`table-footer-group`|`block`|
|`flex`|`flex`/`float`속성 효과없음|
|`inline-flex`|`inline-flex` / `float`속성 효과없음|
|그외|변화없음|

## clear

`float`속성이 적용되지 않도록 지정(해제)

|값|의미|기본값|
|---|---|---|
|`none`|요소 띄움 허용|`none`|
|`left`|왼쪽 띄움 해제|
|`right`|오른쪽 띄움 해제|
|`both`|양쪽(왼쪽, 오른쪽) 모두 띄움 해제|

## position

요소의 위치 지정 방법의 유형(기준)을 설정

|값|의미|기본값|
|---|---|---|
|`static`|유형(기준)없음 / 배치 불가능|`static`|
|`relative`|요소 자신을 기준으로 배치|
|`absolute`|위치 상 부모 요소를 기준으로 배치|
|`fixed`|브라우저(뷰포트)를 기준으로 배치|
|`sticky`|스크롤 영역 기준으로 배치|

## top

요소의 `position`기준에 맞는 '위쪽'에서의 거리(위치)를 설정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|`0`|
|`%`|부모(위치 상의 부모(조상)) 요소의 세로 너비의 비율로 지정, 음수 값 허용|

## bottom

요소의 `position`기준에 맞는 '아래쪽'에서의 거리(위치)를 설정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|`0`|
|`%`|부모(위치 상의 부모(조상)) 요소의 세로 너비의 비율로 지정, 음수 값 허용|

## left

요소의 `position`기준에 맞는 '왼쪽'에서의 거리(위치)를 설정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|`0`|
|`%`|부모(위치 상의 부모(조상)) 요소의 가로 너비의 비율로 지정, 음수 값 허용|

## right

요소의 `position`기준에 맞는 '오른쪽'에서의 거리(위치)를 설정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|`0`|
|`%`|부모(위치 상의 부모(조상)) 요소의 가로 너비의 비율로 지정, 음수 값 허용|
