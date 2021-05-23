# 프로토타입

자바스크립트는 멀티 패러다임 프로그램이 언어다. 함수형, 객체지향, 프로토타입을 모두 사용할 수 있다.

자바스크립트는 클래스 기반의 객체지향 언어보다 강력한 프로토타입 기반의 객체지향 프로그래밍 언어다.

> 클래스(class)
    ES6에서 클래스가 추가되었지만 자바에서 쓰이는 클래스의 개념이 아니라 함수이다. 클래스는 생성자보다 인스턴스 생성에 엄격하며 고유한 기능도 제공한다. 따라서 새로운 인스턴스 생성 방법으로 보는 것이 바람직하다.


자바스크립트에서 원시값을 제외한 모든 것은 객체이다.

1. 객체지향 프로그래밍

객체지향 프로그래밍이란 객체의 집합으로 프로그램을 표현하려는 프로그래밍 패러다임이다.

객체지향 프로그래밍은 사물과 사물이 가지는 속성 하는 행위를 묶어 표현하려고 한다. 이를 통해 여러 개의 값을 하나의 단위로 나타낼 수 있으며, 논리적 단위로 자료구조를 만들 수 있다.

이렇게 만들어진 객체들은 연관성이 존재할 수 있으며, 이를 상속 관계로 나타낼 수 있다.

2. 상속과 프로토타입

어떠한 프로퍼티나 메소드를 다른 객체가 상속받아 자신의 것처럼 사용할 수 있다.

자바스크립트는 프로토타입을 기반으로 상속을 구현하여 불필요한 중복을 제거한다.

3. 프로토타입 객체

프로토타입 객체는 객체 간 상속을 위해 필요한 것이다. 프로토타입은 어떤 객체의 상위 역할을 하는 객체를 일컫는다. 프로토타입을 상속받은 객체는 프로토타입의 프로퍼티나 메서드를 사용할 수 있다.

모든 객체는 `[[Prototype]]`이란 내부 슬롯을 가진다. 이 내부슬롯의 값으로 프로토타입 객체로 가는 참조값(또는 null)을 가진다. 프로토타입은 객체 생성 방식에 따라 결정되며 `[[Prototype]]`에 저장된다.

객체는 `__proto__`를 통해 프로토타입 객체에 간접적으로 접근할 수 있다. 프로토타입은 자신의 constructor 프로퍼티를 통해 생성자 함수에 접근할 수 있다. 

- `__proto__` 접근자 프로퍼티

자바스크립트에서 내부 슬롯은 프로퍼티가 아니다. 따라서 간접적인 수단으로 `__proto__`와 같은 접근자 프로퍼티를 제공한다. `__proto__`는 get/set 접근자 함수를 가지고 있어 이 함수들을 통해 프로토타입의 값을 읽거나 쓸 수 있다.

`__proto__` 접근자 프로퍼티는 상속을 통해 사용된다. 즉, 이 프로퍼티는 객체 고유의 프로퍼티가 아니라 Object.prototype의 프로퍼티이다. 

> 프로토타입 체인

스코프 체인에서 스코프에 식별자가 없을 경우 상위 스코프로 검색을 하는 과정과 유사하다. 프로토타입도 해당 객체의 프로토타입에 프로퍼티가 없는 경우 자신의 부모 역할을 하는 프로토타입에서 찾아나간다. 프로토타입의 종점은 Object.prototype이다. 

`__proto__` 접근자 프로퍼티를 통해 프로토타입에 접근하는 이유

프로토타입에서 순환 구조가 만들어지는 경우 무한루프에 빠진다. 따라서 프로토타입 체인은 단방향으로 이루어져야 한다. 이 구조를 유지하기 위해 `__proto__` 접근자 프로퍼티를 통해 구조를 해치지 않는 선에서 프로토타입에 접근하고 교체하도록 한다. 

`__proto__` 접근자 프로퍼티를 코드 내에서 직접 사용하는 것은 권장하지 않는다.

`__proto__`는 ES6부터 표준으로 채택되었다. 하지만 모든 객체가 `__proto__`접근자 프로퍼티를 사용할 수 있는 건 아니다.

만약 프로토타입의 참조를 취득하고 싶은 경우 `Object.getPrototypeOf`메서드(ES5)를 사용하고, 교체하고 싶은 경우 Object.setPrototype 메서드(ES6)를 사용하는 것이 좋다.

- 함수 객체의 prototype 프로퍼티

함수 객체만이 소유하는 **prototype** 프로퍼티는 생성자 함수가 생성할 인스턴스의 프로토타입을 가리킨다. 

prototype 프로퍼티는 생성자 함수가 생성할 인스턴스의 프로토타입을 가리킨다. 즉 생성자 함수로 사용할 수 없는 축약 표현 메서드나 화살표 함수에는 이 프로퍼티가 존재하지 않는다.

일반 함수에는 prototype 프로퍼티가 존재하나, 인스턴스를 생성하지 않으므로 큰 효용이 없다.

Object.prototype으로부터 상속받은 `__proto__`접근자 프로퍼티와 함수 객체만이 가지고 있는 prototype프로퍼티는 동일하지만 사용 주체가 다르다.

생성자 함수의 경우 생성할 인스턴스의 프로토타입을 할당하기 위해 사용하는 반면, 그 외의 경우 객체가 자신의 프로토타입에 접근 또는 교체하기 위해 사용한다.

- 프로토타입의 constructor 프로퍼티와 생성자 함수

모든 프로토타입은 constructor 프로퍼티를 갖는다. 이 프로퍼티는 생성자 함수를 가리킨다. 따라서 생성자 함수로 생성한 인스턴스는 constructor 프로퍼티를 통해 생성자 함수와 연결된다. 이 프로퍼티는 생성자 함수의 프로토타입에서 상속받는다.

- 리터럴 표기법에 의해 생성된 객체의 생성자 함수와 프로토타입

리터럴 표기법으로 만든 객체의 경우 객체를 만든 주체가 반드시 생성자 함수인 것은 아니다. 

> 추상 연산(abstract operation)
    추상 연산은 ECMAScript에서 내부 동작의 알고리즘을 구현한 것이다. 

객체 리터럴이 평가될 때는 추상 연산 OrdinaryObjectCreate를 호출하고 프로퍼티를 추가하도록 명시되어있다.

따라서 빈 객체를 생성하는 것 까진 Object로 생성자 함수가 동일하나 인자가 주어지거나 new 연산자를 사용하면 생성자 함수가 달라진다.

함수 객체의 경우도 이 차이가 더 명확히 보인다. Function 생성자 함수로 만든 함수는 렉시컬 스코프가 아닌 전역 함수인 것처럼 스코프를 생성하며 클로저도 만들지 않는다. 따라서 함수 선언문과 함수 표현식을 평가하여 함수 객체를 생성한 것은 Function 생성자 함수가 아니다. 하지만 constructor는 Fucntion을 가라키고 있다.

리터럴 표기법에 의해 생성된 객체도 상속을 위해 프로토타입이 필요하다. 따라서 가상의 생성자 함수를 가진다. 생성자 함수는 프로토타입과 같이 생성되고 서로 constructor, prototype으로 연결되어있기 때문에 생성자 함수와 프로토타입은 항상 쌍으로 존재해야 함을 알 수 있다.

- 프로토타입의 생성 시점

모든 객체는 생성자 함수와 연결되어 있다.

> Object.create 메서드와 클래스에 의한 객체 생성
    메서드와 클래스로 생성한 객체도 생성자 함수와 연결되어 있다.

프로토타입은 생성자 함수가 생성되는 시점에 더불어 생성된다. 생성자 함수는 사용자 정의와 빌트인으로 나눌 수 있다.

- 사용자 정의 생성자 함수와 프로토타입 생성 시점

메서드 축약 표현과 화살표를 제외한 함수는 new 연산자를 통해 생성자 함수로 사용할 수 있다.

호이스팅으로 인해 함수 선언문은 다른 코드보다 먼저 평가되어 함수 객체가 된다. 이 때 프로토타입도 같이 생성된다. 생성된 프로토타입의 프로토타입은 언제나 Object.prototype이다.

- 빌트인 생성자 함수와 프로토타입 생성 시점

빌트인 생성자 함수는 전역 객체가 생성되는 시점에 생성된다. 생성된 프로토타입은 빌트인 생성자 함수의 prototype 프로퍼티에 바인딩된다.

> 전역 객체(global object)
    전역 객체는 코드 평가 이전 단게에 자바스크립트 엔진에 의해 성생되는 객체이다. 브라우저에선 window가 생성되고 node.js에선 global을 생성한다.
    전역 객체는 표준 빌트인, 호스트 객체, var 키워드로 표현한 전역 변수와 전역 함수를 프로퍼티로 갖는다. Math, Reflect, JSON을 제외한 표준 빌트인 객체는 모두 생성자 함수이다.

객체 생성되기 이전에 생성자 함수와 프로토타입은 이미 존재한다. 이후 생성자 함수 또는 리터럴로 객체를 생성하면 생성된 객체의 `[[Prototype]]`내부 슬롯이 할당되고 프로토타입을 상속받는다.

6. 객체 생성 방식과 프로토타입의 결정

객체는 리터럴, Object 생성자, 생성자 함수, Object.create 메서드, 클래스(ES6)로 생성할 수 있다.

이 모든 방식은 추상 연산에 의해 생성된다. OrdinaryObjectCreate는 자신이 생성할 객체의 프로토타입을 인수로 전달받는다. 이 인수에 따라 객체에 추가할 프로퍼티 목록을 객체에 추가한다. 그리고 인수로 전달받은 프로토타입을 자신이 생성할 객체의 `[[Prototype]]` 내부 슬롯에 할당한다. 그리고 객체를 반환한다.

- 객체 리터럴에 의해 생성된 객체의 프로토타입

객체 리터럴에 의해 생성된 객체의 프로토타입은 Object.prototype이다. 

- Object 생성자 함수에 의해 생성된 객체의 프로토타입

Object 생성자 함수에 의해 생성된 객체의 프로토타입은 Object.prototype이다. 위에서 본 객체 리터럴과의 차이점은 객체 리터럴은 객체 리터럴 내부에 프로퍼티를 추가하지만 Object 생성자 함수 방식은 일단 빈 객체를 생성한 이후 프로퍼티를 추가해야 한다.

- 생성자 함수에 의해 생성된 객체의 프로토타입

new 연산자와 함께 함수를 호출하여 인스턴스를 생성하면 추상 연산에 생성자 함수의 prototype 프로퍼티에 바인딩되어 있는 객체를 넘겨준다. 따라서 생성자 함수에 의해 생성된 객체의 프로토타입은 생성자 함수의 prototype프로퍼티에 바인딩 된 객체이다.

7. 프로토타입 체인

자바스크립트는 해당 객체에 접근하려는 프로퍼티가 없다면 `[[Prototype]]`내부 슬롯의 참조를 따라 프로퍼티(또는 메서드)를 검색한다. 이를 프로토타입 체인이라하며 객체지향 프로그래밍을 구현하는 방식이다.

프로토타입 체인의 종점은 Object.prototype이며 Object.prototype의 `[[Prototpye]]` 내부 슬롯 값은 이다.

프로토타입 체인에서도 찾고자 하는 메서드나 프로퍼티를 못 찾을 경우 undefined를 반환한다. 이 때 에러는 발생하지 않는다.

스코프 체인은 식별자를 찾기 위한 매커니즘이고 프로토타입 체인은 프로퍼티와 메서드를 찾기 위한 매커니즘이다. 이 두 매커니즘은 서로 상호작용한다.

8. 오버라이딩과 프로퍼티 섀도잉

프로토타입이 소유한 프로퍼티를 프로토타입 프로퍼티, 인스턴스가 소유한 프로퍼티를 인스턴스 프로퍼티라고 부른다.

프로토타입 프로퍼티와 똑같은 이름을 가진 프로퍼티나 메서드를 인스턴스 프로퍼티에 추가하면 상속 관계에 의해 프로토타입 프로퍼티가 가려지는데 이를 섀도잉이라 한다.

> 오버라이딩(overriding)
    상위클래스의 메서드를 하위 클래스에서 재정의 하는 것을 말한다.

> 오버로딩(overloading)
    함수의 이름은 동일하나 매개변수의 타입이나 개수가 다른 메서드를 말한다. 자바스크립트는 오버로딩을 지원하지 않지만, arguments객체를 통해 구현할 수 있다.

상속 관계에 의해 프로퍼티 삭제도 해당 프로토타입부터 진행한다. 다만, 하위 객체에서 프로토타입에 접근하여 프로퍼티를 변경하는 것을 허용하지 않는다. 따라서 프로토타입 체인을 통해서가 아니라 프로토타입에 직접 접근해야 한다.

9. 프로토타입의 교체

프로토타입은 동적으로 변경할 수 있다. 생성자 함수 또는 인스턴스를 통해 교체할 수 있다.

- 생성자 함수에 의한 프로토타입의 교체

프로토타입을 교체하는 경우 생성자함수와 prototype을 연결하는 constructor를 명시하지 않으면 연결이 끊어지므로 consturctor 프로퍼티를 교체하려는 프로퍼티 객체에 넣어야 한다. 

- 인스턴스에 의한 프로토타입의 교체

프로토타입은 prototype 프로퍼티뿐만 아니라 `__proto__`접근자 프로퍼티를 통해 접근할 수 있으다. 따라서 이 접근자 프로퍼티를 통해 프로토타입을 교체할 수 있다.

prototype 프로퍼티에 직접 접근하여 교체하는 것과 다른점은 prototype 프로퍼티의 경우 앞으로 생성될 인스턴스에까지 영향을 미치지만, `__proto__`는 해당 객체의 프로토타입만 교체한다.

따라서 이 경우 Person 생성자 함수의 prototype 프로퍼티가 교체된 프로토타입을 가리키지 않는다.

10. instanceof 연산자

이 연산자는 우변의 생성자 함수의 prototype에 바인딩된 객체가 좌변의 객체의 프로토타입 체인 상에 존재하면 true 아니면 false로 평가한다.

11. 직접 상속

- Object.create에 의한 직접 상속

Object.create는 명시적으로 프로토타입을 지정하여 새로운 객체를 생성한다.

Object.create는 두 개의 매개변수를 가진다. 첫번째는 프로토타입으로 지정할 객체이고, 두번째는 생성할 객체의 프로퍼티 키와 프로퍼티 디스크립터 객체로 이루어진 객체를 전달한다(생략 가능). 

객체를 생성하면서 직접적으로 프로토타입에 속한 객체를 만들 수 있다. 이를 이용하면 new연산자 없이도 객체 생성이 가능하고, 프로토타입 생성과 객체 생성을 한 번에 할 수 있다. 그리고 객체 리터럴에 의해 생성된 객체도 상속받을 수 있다.

하지만 이 방법은 ESLint 프로토타입 체인의 종점을 위치하는 객체를 생성할 수 있기 때문에 권장하지 않는다. 종점에 위치하게 되면 Object.prototype의 빌트인 메서드를 사용할 수 없다.

이러한 에러의 위험성을 줄이기 위해선 간접 호출을 하는 것이 좋다. 

- 객체 리터럴 내부에서 `__proto__`에 의한 직접 상속

ES6에선 `__proto__` 접근자 프로퍼티를 사용하여 직접 상속을 구현할 수 있다. 객체 리터럴로 생성하여 `__proto__`에 직접 프로퍼티 값을 할당하면 된다.

12. 정적 프로퍼티/메서드

정적 프로퍼티/메서드는 생성자 함수로 인스턴스를 생성하지 않아도 참조/호출 할 수 있는 프로퍼티/메서드를 말한다. 정적 프로퍼티/메소드를 참조/호출을 할 땐 인스턴스로 할 수 없다. 

this를 참조하지 않는 프로토타입 메소드는 정적 메서드로 변경해도 동일한 효과를 얻는다.

프로퍼티/메서드를 표기할 때 prototypedmf #으로 표기 하는 경우도 있다. 

13. 프로퍼티 존재 확인

- in 연산자

객체 내에 특정 프로퍼티가 존재하는지 여부를 확인한다. in 연산자는 대상 객체가 상속받은 모든 프로토타입의 프로퍼티를 확인한다.

in 대신 ES6에 도입된 Reflect.has메서드를 쓸 수 있다.

- Object.prototype.hasOwnProperty 메서드

in과 달리 해당 객체의 프로토타입에 존재하는 프로퍼티인지 확인한다. 

14. 프로퍼티 열거

- for...in 문

객체의 모든 프로퍼티를 순회하며 열거할 때 사용한다. `for(변수선언문 in 객체){...}`

상속받은 모든 프로토타입의 프로퍼티를 열거하지만 Object.prototype의 프로퍼티는 열거되지 않는다. 열거되지 않는 이유는 for...in은 프로퍼티 어트리뷰트 중 `[[Enumerable]]`값이 true인 것만 열겨하기 때문이다.

for...in문은 프로퍼티를 열거할 때 순서를 보장하지 않는다. 하지만 대부분의 모던 브라우저는 순서를 보장한다.

배열에는 for...in문을 사용하기 보단 for...of문 또는 Array.prototype.forEach 메서드 사용을 권장한다. 배열도 객체이므로 프로퍼티와 상속받은 프로퍼티가 포함될 수 있다.

- Object.keys/values/entries 메서드

객체 자신의 고유 프로퍼티만을 열거하기 위해 Object,keys/values/entries를 사용할 수 있다. 

Object.keys는 열거 가능한 프로퍼티 키를 배열로 반환한다.

ES8에서 도입된 Objects.values 메서드는 객체 자신의 열거 가능한 프로퍼티 값을 배열로 반환한다. 

ES8에서 도입된 Object.entries 메서드는 객체 자신의 열거 가능한 프로퍼티 키와 값의 쌍의 배열을 담아 반환한다. 




