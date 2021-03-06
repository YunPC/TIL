# 객체 리터럴

1. 객체란?

자바스크립트는 객체 기반의 프로그래밍 언어이며, 원시 타입을 제외한 모든 것을 객체라고 한다.

원시 타입은 단 하나의 원시 타입을 나타내지만 객체의 경우 여러 원시 타입을 모아둔 자료 구조이다. 원시 타입은 값을 변경할 수 없지만, 객체의 경우 값을 변경할 수 있다.

객체는 0기 이상의 프로퍼티들의 집합이며, 키와 값으로 구성되어 있다.

자바스크립트에서 사용할 수 있는 모든 값을 프로퍼티이다. 자바스크립트 함수는 일급객체이므로 함수도 프로퍼티로 사용할 수 있다. 프로퍼티 값이 함수일 경우 함수와 구분하기 위해 메서드라 부른다.

따라서 프로퍼티는 객체의 상태를 나타내는 값이고, 이 프로퍼티를 조작할 수 있는 객체를 메서드라 부른다.

객체 안에는 상태와 상태를 조작할 수 있는 동작이 모두 있기 때문에 유용하다.

2. 객체 리터럴에 의한 객체 생성

객체 지향 프로그래밍 언어에서는 객체에 대한 정의를 하고 new연산자와 함께 생성자를 호출하여 인스턴스를 생성한다.

>인스턴스(instance)
    인스턴스는 객체가 실제 메모리 공간을 차지한 것을 말한다.

자바스크립트에서는 프로토타입 기반 객체지향 언어로서 다양한 객체 생성 방법을 지원한다.

+ 객체 리터럴
+ Object 생성자 함수
+ 생성자 함수
+ Object.create 메서드
+ 클래스(ES6)

이 중 첫번째인 객체 리터럴은 중괄호를 통해 객체를 정의하는 것을 말한다. 중괄호 내에 0개 이상의 프로퍼티를 정의할 수 있으며, 할당이 이루어지는 시점에 객체를 생성한다.

만약 중괄호 내에 프로퍼티를 정의하지 않으면 빈 객체가 생성된다.

객체 리터럴에서 사용하는 중괄호는 값으로 평가되는 표현식이기 때문에 끝에 세미콜론은 붙인다. 이 면에서 코드 블록과 차이가 있다.

다른 언어와 다르게 자바스크립트는 클래스를 정의하지 않고도 객체를 생성할 수 있다. 그리고 객체를 생성한 뒤에 동적으로 프로퍼티를 추가할 수 있다.

객체 리터럴 이외의 선언 방법은 모두 함수를 이요한다.

3. 프로퍼티

객체는 프로퍼티들의 집합이고 프로퍼티는 키와 값의 쌍이다. 프로퍼티간의 구분은 컴마를 통해 구분한다.

프로퍼티 키에는 심볼과 문자열이 올 수 있고 프로퍼티 값에는 모든 값이 올 수 있다.

프로퍼티 키는 식별자 역할을 하는데, 반드시 네이밍 규칙을 따를 필요는 없다. 다만 네이밍 규칙을 따르지 않는 경우에는 반드시 따옴표를 사용해야 한다. 왜냐하면 사이에 있는 하이픈과 같은 값을 연산자로 인식할 수 있기 때문이다.

프로퍼티 키를 동적으로 생성하려면 `객체[프로피터 키] = 프로퍼티 값`을 이용하여 생성할 수 있다.

빈 문자열을 프로퍼티 키로 사용할 수 있지만, 의미를 담기 어려워 권장하지 않는다. 만약 키 값으로 심볼이나 문자열이 아닌 값이 들어오면 암묵적 형 변환을 통해 형 변환이 이루어진다.

예약어를 프로퍼티 키로 사용할 수 있으며, 만약 동적으로 만든 키값이 이미 있을 경우 업데이트가 일어난다.

4. 메서드

자바스크립트 함수는 일급 객체이기 때문에 값으로 취급할 수 있다. 따라서 프로퍼티 값으로 사용할 수 있다. 

프로퍼티 값이 함수일 경우 이를 특별히 메서드라 부른다. 

5. 프로퍼티 접근

프로퍼티에 접근하는 방법은 마침표를 이용해 접근하는 마침표 표기법과 대괄호를 통해 접근하는 대괄효 표기법이 있다.

식별자 네이밍 규칙을 준수하는 경우 위 두가지 표기법을 모두 사용할 수 있다.

대괄호 프로퍼티 접근 연산자 내부에 지정하는 프로퍼티 키는 반드시 따옴표로 감싼 문자열이어야 한다. 따옴표로 감싸지 않은 이름은 식별자로 해석한다. 단 프로퍼티키가 숫자로 이루어진 문자열인 경우 생략할 수 있다.

> `person.last-name`의 경우 person.last가 먼저 평가된다. 프로퍼티 값이 없기 떄문에 undefined가 되고 `undefined - name`이 되기 때문에 name 식별자를 찾는다. name이 없으므로 참조 에러를 발생시킨다.

6. 프로퍼티 값 갱신

이미 존재하는 프로퍼티에 값을 할당하면 프로퍼티 값이 갱신된다.

7. 프로퍼티 동적 생성

존재하지 않는 프로퍼티에 값을 할당하면 동적으로 생성되어 추기되고 프로퍼티 값이 할당된다. 

8. 프로퍼티 삭제

delete연산자는 프로퍼티를 삭제한다. 만약 없는 프로퍼티를 삭제하면 에러가 발생하지 않고 무시된다.

9. ES6에서 추기된 객체 리터럴의 확장 기능

- 프로퍼티 축약 표현

변수 이름과 프로퍼티 키가 동일한 이름일 경우 프로퍼티 키를 생략할 수 있다. 이때 프로퍼티 키는 변수 이름으로 생성된다.

- 계산된 프로퍼티 이름

문자열 또는 문자열로 타입 변환할 수 있는 값으로 평가되는 표현식을 통해 프로퍼티 키를 동적으로 생성할 수 있다. 이때 표현식은 대괄호로 묶어주어야 한다. 이를 계산된 프로퍼티 이름이라한다.

ES6에서는 객체 리터럴 내부에서도 계산된 프로퍼티 이름으로 프로퍼티 키를 동적 생성할 수 있다.

- 메서드 축약 표현

ES5에서 메서드는 프로퍼티 값으로 함수를 할당해야 한다. 다음 버전인 ES6에서는 function 키워드를 생략할 수 있다.




