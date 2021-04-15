# CSS/속성 - 배경

## background

요소의 배경을 설정(단축)

|값|의미|기본값|
|---|---|---|
|`background-color`|배경 색상|`transparent`|
|`background-image`|하나 이상의 배경 이미지|`none`|
|`background-repeat`|배경 이미지의 반복|`repeat`|
|`background-position`|배경 이미지의 위치|`0 0`|
|`background-attachment`|배경 이미지의 스크롤 여부(특성)|`scroll`|

### 사용법

```
background: 색상 이미지경로 반복 위치 스크롤 특성;
```

```css
.box1 {
    background: red url("../image.jpg") no-repeat left top scroll;
    /* 색상 이미지경로 반복 위치 스크롤 특성 */
}

.box2 {
    background: url("../image.jpg") no-repeat right 100px;
    /* 이미지경로 반복 위치 */
}

.box3 {
    background: red;
    /* 색상 */
}
```

### background-color

요소의 배경 색상을 지정(개별)

|값|의미|기본값|
|---|---|---|
|색상|요소의 배경 색상|
|`transparent`|투명|`transparent`|

### background-image

요소의 배경에 하나 이상의 이미지를 삽입(개별)


|값|의미|기본값|
|---|---|---|
|`none`|이미지 없음|`none`
|`url('경로')`|이미지 경로(URL)|

#### 사용법

```
background-image: url("경로");
```

```css
.box {
    background-image: url("../img/image.jpg");
    width: 120px;
    height: 80px
}
```
> 배경 이미지 삽입 시, 요소의 크기가 설정되어 있어야 배경 이미지가 보일 수 있다.

```css
.box1 {
    /* 개별속성 */
    background-image: url("../img/i1.jpg"),
    url("../img/i2.jpg"),
    url("../img/i3.jpg");
}

.box2 {
    /* 단축속성 */
    backgroud: url("../img/i1.jpg") no-repeat, url("../img/i2.jpg") no-repeat 100px 50px, url("../img/i3.jpg") repeat-x;
}
```

> 하나 이상의 배경 이미지를 삽입할 경우, `,`로 구분한다. 먼저 작성된 이미지가 더 위에 쌓인다. 이런 '다중 배경 이미지'는 IE8이하 버전에 사용할 수 없다.

## background-repeat

배경 이미지의 반복을 설정(개별)

|값|의미|기본값|
|---|---|---|
|`repeat`|배경 이미지를 수직, 수평으로 반복|`repeat`|
|`repeat-x`|배경 이미지를 수평으로 반복|
|`repeat-y`|배경 이미지를 수직으로 반복|
|`no-repeat`|반복 없음

## background-position

배경 이미지의 위치를 설정(개별)

|값|의미|기본값|
|---|---|---|
|`%`|왼쪽 상단 모서리는 `0% 0%`, 오른쪽 상단 모서리는 `100%, 100%`|`0% 0%`|
|방향|방향을 입력하여 위치 설정 `top`, `bottom`, `left`, `right`, `center`|
|단위|`px`,`em`,`cm`등 단위로 지정|

### 사용법

값이 방향일 경우

```
background-position: 방향1 방향2;
```

값이 단위(`%`,`px`등)일 경우
```
background-position: x축 y축;
```

## background-attachment

요소가 스크롤될 때 배경 이미지의 스크롤 여부(특성) 설정(개별)

|값|의미|기본값|
|---|---|---|
|`scroll`|배경 이미지가 요소를 따라서 같이 스크롤 됨|`scroll`|
|`fixed`|배경 이미지가 뷰포트(Viewport)에 고정되어, 요소와 같이 스크롤되지 않음|
|`local`|요소 내 스크롤 시 배경 이미가 같이 스크롤 됨|
