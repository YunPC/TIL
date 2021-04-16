# CSS Flex(Flexible Box)

대부분 사이트는 전체 레이아웃이 수직 구서이며, '위-아래'로 스크롤 하여 사용한다.

레이아웃을 구성할 때 가장 많이 상요하는 요소(Elements)들이 기본적으로 블록(Block) 개념으로 표시(Display)되며 이는 뷰(View)에 수직(위에서 아래로)으로 쌓이기 때문에 수직 구성은 상대적으로 쉽게 만들 수 있다.
하지만 수평(왼쪽에서 오른쪽으로) 구성의 경우는 조금 다르다.

## CSS3 Flexible Box

Flex는 요소의 크기가 불분명하거나 동적인 경우에도, 각 요소를 정렬할 수 있는 효율적인 방법을 제공한다.

우선 Felx는 2개의 개념으로 나뉜다.
첫 번째는 Container 두 번째는 Items이다.
Container는 Items를 감싸는 부모 요소이며, 각 Item을 정렬하기 위해선 Container가 필수이다.

Container와 Items에 적용하는 속성은 구분됨을 주의하자.
Container에는 `display`, `flex-flow`, `justify-content`등의 속성을 사용할 수 있으며, Items에는 `order`, `flex`, `align-self`등의 속성을 사용할 수 있다.

## Flex Container

Flex Container를 위한 속성들은 다음과 같다.

|속성|의미|
|---|---|
|display|Flex Container를 정의|
|flex-flow|`flex-direction`와 `flex-wrap`의 단축 속성|
|flex-direction|Flex items의 주 축(main-axis)을 설정|
|flex-wrap|Flex items의 여러 줄 묶음(줄 바꿈)설정|
|justify-content|주 축(main-axis)의 정렬 방법을 설정|
|align-content|교차 축(cross-axis)의 정렬 방법을 설정(2줄 이상)|
|align-items|교차 축(cross-axis)에서 items의 정렬 방법을 설정(1줄)|

## flex-flow

이 속성은 단축 속성으로 Flex Items의 주 축(main-axis)을 설정하고 Items의 여러 줄 묶음(줄 바꿈)도 설정한다.

```
flex-flow: 주축 여러줄묶음;
```

```css
.flex-container {
    flow-flow: row-reverse wrap;
}
```

|값|의미|기본값|
|---|---|---|
|flex-direction|Items의 주 축(main-axis)을 설정|`row`|
|flex-wrap|Items의 여러 줄 묶음(줄 바꿈) 설정|`nowrap`|

## flex-direction

Items의 주 축(main-axis)을 설정한다.

|값|의미|기본값|
|---|---|---|
|row|Items를 수평축(왼쪽에서 오른쪽으로)으로 표시|`row`|
|row-reverse|Items를 `row`의 반대축으로 표시|
|column|Items를 수직축(위에서 아래로)으로 표시|
|column-reverse|Items를 `column`의 반대 축으로 표시|

```
flex-direction: 주축;
```

### 주 축(main-axis)과 교차 축(cross-axis)

주 축(main-axis)과 교차 축(cross-axis)의 개념은 다음과 같다.
값 `row`는 Items를 수평축으로 표시하므로 이 때는 주 축이 수평이며 교차 축은 수직이 된다.
반대로 값 `column`은 Items를 수직축으로 표시하므로 주 축은 수직잉며 교차 축은 수평이 된다.
즉, 방향(수평, 수직)에 따라 주 축과 교차 축이 달라진다.

### 시작점(flex-start)과 끝점(flex-end)

주 축이나 교차 축의 시작하는 점과 끝나는 지점을 지칭한다.
방향에 따라 시작점과 끝점이 달라진다.

### flex-wrap

Items의 여러 줄 묶음(줄 바꿈)을 설정한다.

|값|의미|기본값|
|---|---|---|
|nowrap|모든 Items를 여러 줄로 묶지 않음(한 줄에 표시)|`nowrap`|
|`wrap`|Items를 여러 줄로 묶음|
|`wrap-reverse`|`Items`를 `wrap`의 역 방향으로 여러 줄로 묶음|

```
flex-wrap: 여러줄묶음;
```

기본적으로 Items는 한 줄에서만 표시되고 줄 바꿈 되지 않습니다.
이는 지정된 크기(주 축에 다라 `width`나 `height`)를 무시하고 한 줄안에서만 가변한다.
Items를 줄 바꿈 하려면 값으로 `wrap`을 사용해야 한다.

### justify-content

주 축(main-axis)의 정렬 방법을 설정한다.

|값|의미|기본값|
|---|---|---|
|flex-start|Items를 시작점(flex-start)으로 정렬|`flex-start`|
|flex-end|Items를 끝점(flex-end)으로 정렬|
|center|Items를 가운데 정렬|
|space-between|시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨|
|space-around|Items를 균등한 여백으로 포함하여 정렬|

```
justify-content: 정렬방법;
```

### align-content

교차 축(cross-axis)의 정렬 방법을 설정한다.
주의할 점은 `flex-wrap` 속성을 통해 Items가 여러 줄(2줄 이상)이고 여백이 있을 경우만 사용할 수 있다.

> Items가 한 줄일 경우 `align-items` 속성을 사용하자.

|값|의미|기본값|
|---|---|---|
|stretch|Container의 교차 축을 채우기 위해 Items를 늘림|`stretch`|
|flex-start|Items를 시작점(flex-start)으로 정렬|
|flex-end|Items를 끝점(flex-end)으로 정렬|
|center|Items를 가운데 정렬|
|space-between|시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨
|space-around|Items를 균등한 여백을 포함하여 정렬

```
align-content: 정렬방법;
```

값 `stretch`는 교차 축에 해당하는 너비(속성 `width` 혹은 `height`)가 값이 `auto`(기본값)일 경우 교차 축을 채우기 위해 자동으로 늘어난다.

## align-items

교차 축(cross-axis)에서 Items의 정렬 방법을 설정한다.
Items가 한 줄일 경우 많이 사용한다.

주의할 점은 Items가 `flex-wrap`을 통해 여러 줄(2줄 이상)일 경우에는 `align-content`속성이 우선인 점이다. 따라서 `align-items`를 사용하려면 `align-content`속성을 기본값(`stretch`)으로 설정해야 한다.

|값|의미|기본값|
|---|---|---|
|stretch|Container의 교차 축을 채우기 위해 Items를 늘림|`stretch`|
|flex-start|Items를 각 줄의 시작점(flex-start)으로 정렬|
|flex-end|Items를 각 줄의 끝점(flex-end)으로 정렬|
|center|Items를 가운데 정렬
|baseline|Items를 문자 기준선에 정렬

```
align-items: 정렬방법;
```

## Flex Items

Flex Items를 위한 속성들은 다음과 같습니다.

|속성|의미|
|---|---|
|order|Flex Item의 순서를 결정|
|flex|`flex-grow`, `flex-shrink`, `flex-basis`의 단축 속성|
|flex-grow|Flex Item의 증가 너비 비율을 설정|
|flex-shrink|Flex Item의 감소 너비 비율을 설정|
|flex-basis|Flex Item의 (공간 배분 전) 기본 너비 설정|
|align-self|교차 축(cross-axis)에서 Item의 정렬 방법을 설정|

### order

Item의 순서를 설정한다.
Item에 숫자를 지정하고 숫자가 클 수록 순서가 밀린다.
음수가 허용된다.

> HTML 구조와 상관없이 순서를 변경할 수 있기 때문에 유용하다.

|값|의미|기본값|
|---|---|---|
|숫자|Item의 순서를 설정|`0`|

```
order: 순서;
```

### flew-grow

Item의 증가 너비 비율을 설정한다.
숫자가 크면 더 많은 너비를 가진다.
Item이 가변 너비가 아니거나, 값이 `0`일 경우 효과가 없다.

|값|의미|기본값|
|---|---|---|
|숫자|Item의 증가 너비 비율을 설정|`0`|

```
flow-grow: 증가너비;
```

모든 Items의 총 증가 너비(`flex-grow`)에서 각 Item의 증가 너비의 비율 만큼 너비를 가질 수 있다.
예를 들어 Item이 3개이고 증가 너비가 각각 `1`, `2`, `1`이라면,
첫 번째 Item은 총 너비의 25%(1/4)를,
두 번쨰 Item은 총 너비의 50%(2/4)를,
세 번째 Item은 총 너비의 25%(1/4)를 가진다.

## flex-shrink

Item이 감소하는 너비의 비율을 설정한다.
숫자가 크면 더 많은 너비가 감소한다.
Item이 가변 너비가 아니거나, 값이 `0`일 경우 효과가 없다.

|값|의미|기본값|
|---|---|---|
|숫자|Item의 감소 너비 비율을 설정|`1`|

```
flex-shrink: 감소너비;
```

감소 너비(`flex-shrink`)는 요소의 너비에 영향을 받기 때문에 계산하기 까다롭다.
영향을 받는다는 요소의 너비는 `width`, `height`, `flex-basis`등으로 너비가 지정된 경우를 의미한다.
Container의 너비가 줄어 Items의 너비에 영향을 미칠 경우, 영향을 미치기 시작한 지점부터 줄얻느 거리 만큼 감소 너비 비율에 맞게 Item의 너비가 줄어든다.

예를 들어 Container의 너비가 줄어 Item의 너비에 영향을 미치기 시작한 지점부터 실제 줄어든 거리가 `90px`일 때, 요소 너비가 같은 Item이 2개이고 지정된 감소 너비가 각각 `2`와 `1`이라면,

## flex-basis

Item의 (공간 배분 전) 기본 너비를 설정한다.
값이 `auto`일 경우 `width`, `height`등의 속성으로 Item의 너비를 설정할 수 있다.
하지만 단위 값이 주어질 경우 설정할 수 없다.

|값|의미|기본값|
|---|---|---|
|auto|가변 Item과 같은 너비|`auto`|
|단위|`px`,`em`,`cm`등 단위로 지정|

```
flex-basis: 기본너비;
```

`flex` 속성에서 설명한 것 같이 단축 속성 내에서 `flex-basis`를 생략하면 값이 `0`이 되는 것을 주의하자.

## flex

Item의 너비(증가, 감소, 기본)를 설정하는 단축 속성이다.

|값|의미|기본값|
|---|---|---|
|flex-grow|Item의 증가 너비 비율을 설정|`0`|
|flex-shrink|Item의 감소 너비 비율을 설정|`1`|
|flex-basis|Item의 (공간 배분 전) 기본 너비 설정|`auto`|

```
flex: 증가너비 감소너비 기본너비;
```

```css
.item {
    /* 증가너비 감소너비 기본너비 */
    flex: 1 1 20px;
    /* 증가너비 감소너비 */
    flex: 1 1;
    /* 증가너비 기본너비 (단위를 사용하면 flex-basis가 적용된다) */
    flex: 1 20px;
}
```

## align-self

교차 축(cross-axis)에서 개별 Item의 정렬 방법을 설정한다.

`align-items`는 Container 내 모든 Items의 정렬 방법을 설정한다.
필요에 의해 일부 Item만 정렬 방법을 변경하려고 할 경우 `align-self`를 사용할 수 있다.
이 속성은 `align-items`속성보다 우선한다.

|값|의미|기본값|
|---|---|---|
|auto|Container의 `align-itmes`속성을 상속받음|`auto`|
|stretch|Container의 교차 축을 채우기 위해 Item을 늘림|
|flex-start|Item을 각 줄의 시작점(flex-start)으로 정렬|
|flex-end|Item을 각 줄의 끝점(flex-start)으로 정렬|
|center|Item을 가운데 정렬|
|baseline|Item을 문자 기준선에 정렬|