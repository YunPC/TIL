# 단축 평가

- 논리 연산자를 사용한 단축 평가

논리합(||)이나 논리곱(&&)은 두 피연산자 중 하나로 평가된다.

논리곱은 두 피연산자가 모두 true로 평가될 때 true를 반환한다. 평가 방향은 좌에서 우로 진행하기 때문에 첫번째 인자가 true라면 두번째 인자로 인해 논리곱의 값이 정해진다.

논리합의 경우 두 개의 피연산자 중 하나만 true여도 true를 반환한다. 따라서 첫번째 인자값이 true라면 첫번째 값을 형 변환없이 반환한다.

논리합과 논리곱은 값으로 형 변환을 거치지 않은 값을 반환하는데, 이를 단축 평가(short-circuit evaluation)이라 한다. 이에 더해 단축 평가는 논리 값이 연산 중간에 확정되었을 경우, 남은 연산을 하지 않는 것을 말한다.

단축 평가를 적절히 활용하면 if문을 대체할 수 있다. 논리곱의 경우 어떤 조건이 참일 때 무언가를 할 때 유용하다. 반대로 논리합의 경우 어떤 조건이 거짓일 때 활용할 수 있다.

단축 평가는 다음과 같은 상황에서 유용하다

+ 객체를 가리키기를 기대하는 변수가 null 또는 undefined이 안닌지 확인하고 프로퍼티를 참조할 때

객체는 키와 값으로 구성된 프로퍼티들의 집합이다. 객체가 아닌 변수의 프로퍼티를 참조하면 타입에러가 발생한다. 이때 단축평가를 사용하면 에러를 발생시키지 않을 수 있다.

+ 함수 매개변수에 기본값을 설정할 때

함수를 호출할 때 인자가 없는 경우 undefined를 갖게 된다. 이 경우 논리합을 통해 기본값을 설정해 줄 수 있다.

- 옵셔널 체이닝 연산자

ES11(ECMAScript2020)에서 도입된 옵셔널 체이닝(optional chaining) 연산자 ?.는 좌항의 피연산자 null 또는 undefined의 경우 undefined를 반환하고 아닌 경우 우항의 프로퍼티 참조를 이어간다.

> 프로퍼티 참조란 객체의 프로퍼티에 접근해 프로퍼티 값을 참조하는 것을 말한다. 

논리곱과 유사한 동작을 하지만 논리곱의 경우 Falsy값(false, undefined, null, 0, -0, NaN, (빈 문자열))이 false로 평가되기 때문에 0이나 빈 문자열이 객체가 될 경우 프로퍼티 참조가 불가능하다. 

- null 병합 연산자

ES11(ECMAScript2020)에서 도입된 null 병합(nullish coalescing) 연산자 ??는 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환하고, 그렇지 않으면 좌항의 피연산자를 반환한다.

논리합과 유사한 동작을 하지만 다른점이 있다. 만약 0이나 빈 문자열을 기본값으로 유지하고 싶을 경우 논리합에서 이들의 값이 Falsy이기 때문에 ?? 연산자를 써야한다.





