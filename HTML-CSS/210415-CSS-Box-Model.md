## width

요소의 가로 너비를 지정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 너비를 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|

## height

요소의 세로 너비를 지정

|값|의미|기본값|
|---|---|---|
|`auto`|브라우저가 너비를 계산|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|

## max-width

요소의 최대 가로 너비를 지정

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`none`|
|`auto`|브라우저가 너비를 계산|

## min-width
요소의 최소 가로 너비를 지정

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`0`|
|`auto`|브라우저가 너비를 계산|

## max-height

요소의 최대 세로 너비

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`none`|
|`auto`|브라우저가 너비를 계산|

## min-height

요소의 최소 세로 너비

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`0`|
|`auto`|브라우저가 너비를 계산|

## margin

요소의 '외부 바깥 여백'을 지정

> '음수 값'을 사용할 수 있다.

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`0`|
|`auto`|브라우저가 너비를 계산|
|`%`|부모 요소의 너비에 대한 비율로 지정

### 사용법

```
margin: 위 우 아래 좌;
margin: 위 [좌, 우] 아래;
margin: [위, 아래] [좌, 우];
margin: [위, 아래, 좌, 우];
```

```css
.box {
    margin: 10px 20px 30px 40px;
    margin: 10px 20px 40px;
    margin: 10px 40px;
    margin: 10px;
}
```

### margin-top

요소의 '외부(바깥) **위쪽** 여백'을 지정

### margin-bottom

요소의 '외부(바깥) **아래쪽** 여백'을 지정

### margin-left

요소의 '외부(바깥) **왼쪽** 여백'을 지정

### margin-right

요소의 '외부(바깥) **오른쪽** 여백'을 지정

```css
.box1 {
    /* 단축 속성 */
    margin: 10px 20px 30px 40px;
}

.box2{
    /* 개별 속성 */
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 30px;
    margin-left: 40px
}
```

### 마진 중복(병합, Collapse)

마진의 특정 값들이 '중복'되어 합쳐지는 현상

1. 형제 요소들의 `margin-top`과 `margin-bottom`이 만났을 때

2. 부모 요소의 `margin-top`과 자식 요소의 `margin-top`이 만났을 때

3. 부모 요소의 `margin-bottom`과 자식 요소의 `margin-bottom`이 만났을 때

> `마진 중복`은 버그(오류)가 아니다. 현상을 우회하거나 응용할 수 있다.

### 마진 중복 계산법

마진 중복 현상이 발생 시, 중복 값을 계산하는 방법

|조건|요소A 마진|요소B 마진|계산법|중복 값|
|---|---|---|---|---|
|둘 다 양수|`30px`|`10px`|더 큰 값으로 중복|`30px`|
|둘 다 음수|`-30px`|`-10px`|더 작은 값으로 중복|`-30px`|
|각각 양수와 음수|`-30px`|`10px`|`30`+`10`=`-20`|`-20`|

## padding

요소의 여부 '내부(안) 여백'을 지정

|값|의미|기본값|
|---|---|---|
|단위|`px`, `em`, `%` 등 단위로 지정|`0`|
|`%`|부모 요소의 너비에 대한 비율로 지정

```css
.box1 {
    /* 단축 속성 */
    padding: 10px 20px 30px 40px;
}

.box2{
    /* 개별 속성 */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px
}
```

### paddig-top

요소의 '내부(안) **위쪽** 여백'을 지정

### paddig-bottom

요소의 '내부(안) **아래쪽** 여백'을 지정

### paddig-left

요소의 '내부(안) **왼쪽** 여백'을 지정

### paddig-right

요소의 '내부(안) **오른쪽** 여백'을 지정

### 크기 증가

추가된 `padding`값만큼 요소의 크기가 커지는 현상

### 크기가 커지지 않도록 집적! 계산

```css
/* 100 x 100(px) 크기의 요소 만들기 */
.box {
    width: 60px;
    height: 80px;
    background: red;
    padding: 10px 20px;
}
```

> `padding`이 추가된 값만큼 `width`와 `height`를 다시 계산한다.

### 크기가 커지지 않도록 자동 계산

```css
/* 100 x 100(px) 크기의 요소 만들기 */
.box {
    width: 100px;
    height: 100px;
    background: red;
    padding: 10px 20px;
    box-sizing: border-box;
}
```

> 직접 계산하지 않고 `box-sizing: border-box;`를 추가한다.

## border

요소의 '테두리 선'을 지정

|값|의미|기본값|
|---|---|---|
|`border-width`|선의 두께(너비)|`medium`|
|`border-style`|선의 종류|`none`|
|`border-color`|선의 색상|`black`|


### 사용법

```
border: 두께, 종류, 색상
```

```css
.box {
    border: 1px solid red;
}
```

### border-width

선의 두께(너비)를 지정 (단축, 개별)

|값|의미|기본값|
|---|---|---|
|`medium`|중간 두께|`medium`|
|`thin`|얇은 두께||
|`thick`|두꺼운 두께||
|단위|`px`, `em`, `cm`등 단위로 지정||

### 사용법

```
border-width: 위 우 아래 좌;
border-width: 위 [좌, 우] 아래;
border-width: [위, 아래] [좌, 우];
border-width: [위, 아래, 좌, 우];
```

```css
.box {
    border-width: 10px 20px 30px 40px;
    border-width: 10px 20px 40px;
    border-width: 10px 40px;
    border-width: 10px;
}
```

### border-style

선의 종류를 지정(단축, 개별)

|값|의미|기본값|
|---|---|---|
|`none`|선 없음|`none`|
|`hidden`|선 없음과 동일(`table`요소에서 사용)||
|`solid`|실선(일반선)||
|`dotted`|점선||
|`dashed`|파선||
|`double`|두 줄선||
|`groove`|홈이 파여있는 모양(선)||
|`ridge`|솟은 모양(선, `groove`의 반대)||
|`inset`|요소 전체가 들어간 모양(선)||
|`outset`|요소 전체가 나온 모양(선)||

### 사용법

```
border-style: 위 우 아래 좌;
border-style: 위 [좌, 우] 아래;
border-style: [위, 아래] [좌, 우];
border-style: [위, 아래, 좌, 우];
```

```css
.box {
    border-style: solid dotted double inset;
    border-style: solid dotted inset;
    border-style: solid inset;
    border-style: solid;
}
```

### border-color

선의 색상을 지정 (단축, 개별)

|값|의미|기본값|
|---|---|---|
|색상|선의 색상을 지정|`black`|
|`transparent`|투명한 선(요소의 배경색이 보임)||

### 기타 속성1

|속성|의미|사용 값|
|---|---|---|
|`border-top`|위쪽 선|`두께 종류 색상`|
|`border-top-width`|위쪽 선의 두께|`두께`|
|`border-top-style`|위쪽 선의 종류|`종류`|
|`border-top-color`|위쪽 선의 색상|`색상`|
|`border-bottom`|아래쪽 선|`두께 종류 색상`|
|`border-bottom-width`|아래쪽 선|`두께`|
|`border-bottom-style`|아래쪽 선의 종류|`종류`|
|`border-bottom-color`|아래쪽 선의 색상|`색상`|

### 기타 속성2

|속성|의미|사용 값|
|---|---|---|
|`border-left`|위쪽 선|`두께 종류 색상`|
|`border-left-width`|위쪽 선의 두께|`두께`|
|`border-left-style`|위쪽 선의 종류|`종류`|
|`border-left-color`|위쪽 선의 색상|`색상`|
|`border-right`|아래쪽 선|`두께 종류 색상`|
|`border-right-width`|아래쪽 선|`두께`|
|`border-right-style`|아래쪽 선의 종류|`종류`|
|`border-right-color`|아래쪽 선의 색상|`색상`|

## box-sizing

요소의 크기 계산 기준을 지정

|값|의미|기본값|
|---|---|---|
|`content-box`|너비(`width`, `height`)만으로 요소의 크기를 계산|`content-box`|
|`border-box`|너비(`width`, `height`)에 안쪽 여백(`padding`)과 테두리 선(`border`)를 포함하여 요소의 크기를 계산

## display

요소의 박스 타입(유형)을 설정

|값|의미|기본값|
|---|---|---|
|`block`|블록 요소(`<div>`등)||
|`inline`|인라인 요소(`<span>` 등)|
|`inline-block`|인라인-블록 요소(`<input>` 등)|
|기타|`table`, `table-cell`, `flex`등|
|`none`|요소의 박스 타입이 없음(요소가 사라짐)|

## overflow

요소의 크기 이상으로 내용(자식요소)이 넘쳤을 때, 내용의 보여짐을 제어(단축)

|값|의미|기본값|
|---|---|---|
|`visible`|넘친 부분을 자르지 않고 그대로 보여줌|`visible`|
|`hidden`|넘친 부분을 잘라내고, 보이지 않도록 함|
|`scroll`|넘친 부분을 잘라내고 스크롤바를 이용하여 볼 수 있도록 함|
|`auto`|넘친 부분이 있는 경우만 잘라내고 스크롤바를 이용하여 볼 수 있도록 함|