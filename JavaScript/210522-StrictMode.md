# strict mode

1. strict mode란?

자바스크립트 언어의 문법을 더 엄격히 적용하여 오류를 발생시킬 가능성이 높거나 최적화 작업에 문제를 일으킬 수 있는 코드에 대해 명시적인 에러를 발생시키는 것이다.

유사한 효과를 얻기 위해 정적 분석 도구인 ESLint를 사용할 수 있다. ESLint는 코딩 컨벤션도 강제할 수 있기 때문에 strict mode보다는 ESLint의 사용을 추천한다.

ES6에서 도입된 클래스와 모듈은 기본적으로 strict mode가 적용된다.

2. strict mode의 적용

strict mode를 사용하기 위해선 함수 몸체 선두나 전역의 선두에 `use strict;`를 추가한다. 

3. 전역에 strict mode를 적용하는 것은 피하자.

만약 외부 라이브러리가 non-strict mode 스크립트라면 에러를 발생시킬 수 있다. 또한 전역에 적용한 strict mode는 스크립트 단위로 동작하는데 이 모드들을 혼용해서 쓰는 것도 좋지 않다. 따라서 이러한 경우 즉시 실행 함수로 스코프를 나누고 즉시 실행 함수의 선두에 strict mode를 적용한다.

4. 함수 단위로 strict mode 적용을 피하자

함수는 서로 참조가 가능하기 때문에 함수 단위로 strict mode를 주면 혼란을 줄 수 있고 오류를 발생시킬 수 있다. 그리고 함수 단위로 strict mode를 적용하는 것도 번거로운 일이다.

5. strict mode가 발생시키는 에러

- 암묵적 전역

선언하지 않은 변수를 참조하면 ReferenceError가 발생한다.

- 변수, 함수, 매개변수의 삭제

delete 연산자로 변수, 함수, 매개변수를 삭제하면 SyntaxError가 발생한다.

- 매개변수 이름의 중복

중복된 매개변수 이름을 사용하면 SyntaxError가 발생한다.

- with 문의 사용

with문을 사용하면 SyntaxError가 발생한다. with문은 전달된 객체를 스코프체인에 추가한다. with문을 사용하면 코드의 가독성이 나빠지기 때문에 사용을 권하지 않는다.

6. strict mode 적용에 의한 변화

- 일반 함수의 this

strict mode에서 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩 된다. 이때 에러는 발생하지 않는다.

- arguments 객체

strict mode에서는 매개변수에 전달된 인수를 재할당해도 arguments객체에 반영되지 않는다.


