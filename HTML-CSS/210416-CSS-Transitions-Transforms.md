# CSS / 속성 - 전환 & 변환

## Transitions

CSS 속성의 전환 효과를 지정

### transition

CSS 속성의 시작과 끝을 지정(전환 효과)하여 중간 값을 애니메이션 (단축)

|값|의미|기본값|
|---|---|---|
|`transition-property`|전환 효과를 사용할 속성 이름|`all`|
|`transition-duration`|전환 효과의 지속시간 설정|`0s`|
|`transition-timing-function`|타이밍 함수 지정|`ease`|
|`transition-delay`|전환 효과의 대기시간 설정|`0s`|

#### transition-property

전환 효과를 사용할 속성 이름을 설정 (개별)

|값|의미|기본값|
|---|---|---|
|`all`|모든 속성에 적용|`all`|
|속성이름|전환 효과를 사용할 속성 이름|

#### transition-duration

전환 효과의 지속시간을 설정(개별)

|값|의미|기본값|
|---|---|---|
|시간|전환 효과가 지속되는 시간|`0s`|

#### transition-timing-function

타이밍 함수(애니메이션 전환 효과를 계산하는 방법) 지정 (개별)

|값|의미|기본값|Cubic Beizer 값|
|---|---|---|---|
|`ease`|빠르게 - 느리게|`cubic-bezier(.25, .1, .25, 1)`|
|`linear`|일정하게|`cubic-bezier(0, 0, 1, 1)`|
|`ease-in`|느리게 - 빠르게|`cubic-bezier(0, 0, 1, 1)`|
|`ease-out`|빠르게 - 느리게|`cubic-bezier(0, 0, .58, 1)`|
|`ease-in-out`|느리게 - 빠르게 - 느리게|`cubic-bezier(.42, 0, .58, 1)`|
|`cubic-bezier(n,n,n,n)`|자신만의 값을 정의(`0`~`1`)|
|`steps(n)`|`n`번 분할된 애니메이션|

#### transition-delay

전환 효과가 몇 초 뒤에 시작할지 대기시간을 설정 (개별)

|값|의미|기본값|
|---|----|---|
|시간|전환 효과의 대기시간을 설정|`0s`|

## transform

요소의 변환 효과(변형)를 지정

```
transform: 변환함수1, 변환함수2, 변환함수3...;
transform: 원근법 이동 크기 회전 기울임;
```

```css
.box {
    transform: rotate(20deg) translate(10px, 0);
}
```

### transform 2D 변환 함수

|값(변환함수)|의미|단위|
|---|---|---|
|`translate(x,y)`|이동(X축, Y축)|단위|
|`translateX(x)`|이동(X축)|단위|
|`translateY(y)`|이동(Y축)|단위|
|`scale(x, y)`|크기(X축, Y축)|없음(배수)|
|`scaleX(x)`|크기(X축)|없음(배수)|
|`scaleY(y)`|크기(Y축)|없음(배수)|
|`rotate(degree)`|회전(각도)|`deg`|
|`skew(x-deg, y-deg)`|기울임(X축, Y축)|`deg`|
|`skewX(x-deg)`|기울임(X축)|`deg`|
|`skewY(y-deg)`|기울임(Y축)|`deg`|
|`matrix(n,n,n,n,n,n)`|2차원 변환 효과|없음|

