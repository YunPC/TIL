# 빌트인 객체

1. 자바스크립트 객체의 분류

자바스크립트 객체는 표준 빌트인, 호스트, 사용자 정의로 분류할 수 있다.

- 표준 빌트인 객체

ECMAScript 사양에 정의 된 객체를 말하며 애플리케이션 전역의 공통 기능을 제공한다. 자바스크립트 실행 환경과 상관없이 사용할 수 있다. 표준 빌트인 객체는 전역 객체의 프로퍼티로써 별도의 선언 없이 사용할 수 있다.

- 호스트 객체

호스트 객체란 ESMAScript사양은 아니지만 자바스크립트 실행 환경에서 사용할 수 있는 객체를 말한다. 브라우저에선 클라이언트 사이드 WEB API를 Node.js환경에서는 고유 API를 호스트 객체로 제공한다.

- 사용자 정의 객체

사용자가 직접 정의한 객체를 말한다.

2. 표준 빌트인 객체

자바스크립트는 40여 개의 표준 빌트인 객체가 존재한다. Math.Reflect, JSON을 제외한 표준 빌트인 객체는 모두 생성자 함수다. 이들은 프로토타입과 정적 메소드를 제공하고 나머지 표준 빌트인 객체는 정적 메소드만을 제공한다.

표준 빌트인 객체가 생성자 함수로 인스턴스를 생성할 수 있다. 이 인스턴스의 프로토타입은 표준 빌트인 객체의 prototype 프로퍼티를 가리킨다. 따라서 인스턴스는 생성자 함수의 표준 프로토타입 메소드를 사용할 수 있다.

3. 원시값과 래퍼 객체

문자열, 숫자, 불리언 값에 대해 객체처럼 접근하면 생성되는 임시 객체를 래퍼 객체(wrapper object)라 한다. 예를 들어 문자열에 마침표 표기법으로 접근하면 래퍼 객체가 생성되고 내부슬롯 `[[StringData]]`에 문자열 값이 들어간다.

이 래퍼 객체를 통해 Object나 String의 프로토타입에 접근할 수 있다.

래퍼 객체의 처리가 종료되면 다시 원시 타입으로 되돌리고 래퍼 객체는 가비지 컬렉션의 대상이 된다.

원시 값 중 null과 undefined를 래퍼 객체를 생성하지 않으므로 마침표 표기법으로 접근 시 에러가 발생한다.

4. 전역 객체

전역 객체는 코드가 실행되기 이전에 가장 먼저 생성되는 특수한 객체이다. 브라우저 환경에서는 window, Node.js환경에선 global이다.

> globalThis
    ES11(ECMAScript 11)에서 도입된 globalThis는 모든 전역객체를 통칭한 식별자다. 표준 사양이므로 어디서든 사용할 수 있다.

전역 객체는 표준 빌트인, 호스트 객체와 var로 선언한 전역 변수를 프로퍼티로 갖는다. 

전역 객체는 계층적 구조상 어떤 객체에도 속하지 않은 모든 빌트인 객체의 최상위 객체다. 프로토타입 상속 관계에서 최상위라는 의미가 아니라 전역 객체는 어떠한 객체의 프로퍼티도 아니며 표준 빌트인 객체와 호스트 객체를 프로퍼티로 소유한다는 것을 말한다.

전역 객체는 개발자가 의도적으로 생성할 수 없으며 프로퍼티를 참조할 때 window(또는 global)을 생략할 수 있다. 또한 모든 표준 빌트인 객체를 프로퍼티로 가지고 있다. 전역 객체의 프로퍼티로 표준 빌트인 외에도 실행 환경에 따라 추가 프로퍼티를 가질 수 있다. 브라우저에선 클라이언트 사이드 WEB API, Node.js에선 호스트 객체 API를 가진다. var 키워드로 선언한 변수도 추가된다(let, const제외). 

자바스크립트 코드는 하나의 전역 변수를 공유한다. 이 말은 여러 script태그가 하나의 전역 객체를 공유한다와 동일하다.

- 빌트인 전역 프로퍼티

빌트인 전역 프로퍼티는 전역 객체의 프로퍼티를 말한다. 애플리케이션 전역에서 사용하는 값이다.

+ Infinitiy

숫자 무한대를 말한다.

+ NaN

숫자가 아님을 나타내는 숫자값

+ undefined

undeifned프로퍼티는 원시값 undefined를 갖는다.

- 빌트인 전역 함수

빌트인 전역 함수는 애플리케이션 전반에서 호출할 수 있는 전역 객체의 메서드이다.

+ eval

eval은 주어진 문자열 코드를 런타임에 평가 또는 실행한다. 여러 개의 문으로 이루어져 있다면 모든 문을 실행하고 마지막 결과값을 반환한다.

eval함수는 기존의 스코프를 런타임에 동적으로 수정한다. strict mode에서 eval 함수는 자신의 자체적인 스코프를 생성한다.

eval에 let이나 const가 들어가면 strict mode가 자동 적용된다.

eval은 자바스크립트 엔진의 최적화를 거치지 않으며 보안에 취약하기 때문에 사용을 금한다

+ isFinite

주어진 인자가 유한수인지 불리언 값으로 평가한다. 만약 숫자가 아닌 값이 들어오면 False를 반환한다. 다만 null의 경우 0으로 형변환이 이루어지기 때문에 true를 반환한다.

+ isNaN

전달받은 인수가 NaN인지 아닌지 불리언 값으로 평가한다.

+ parseFloat

전달받은 문자열 인수를 실수로 해석한다.

+ parseInt

전달받은 인수를 정수로 해석한다. 전달 받은 인수가 문자열이 아니면 문자열로 변환한 다음, 정수로 해석한다.

두번째 인자로 기수를 정할 수 있다. 이때 들어온 문자열을 기수로 해석하고 10진수로 변환한 값을 반환한다.

10진수가 아닌 해당 기수의 문자열로 바꾸길 원하는 경우 Number.prototype.toString 메서드를 이용한다.

ES5 이전까지는 사용 금지였디만 "0"으로 시작하는 숫자를 8진수로 해석했다. ES6부터는 "0"으로 시작하는 숫자를 10진수로 해석한다. 지수로 변환이 불가능한 경우 NaN을 반환한다.

첫번째 인자에서 첫 문자가 아니라 중간에서 숫자로 바꿀 수 없는 값이 나온 경우 이 값은 무시하고 나머지 문자열을 해석한다.

문자열의 앞 뒤 공백은 무시되며, 공백으로 구분된 문자열의 경우 첫번째 문자열만 반환된다.

+ encodeURI / decodeURI

encodeURI 함수는 완전한 URI(Uniform Resource Identifier)를 문자열을 전달받아 이스케이프 처리를 위해 인코딩한다. URI는 인터넷에 있는 자원을 나타내는 유일한 주소이다.

인코딩이란 URI의 문자들을 이스케이프 처리하는 것이다. 이스케이프 처리는 아스키 문자 셋으로 변환하는 것이다. 이스케이프 처리는 URL에 올 수 없는 문자(한자, 한글)에 대한 처리를 말한다. 알파벳과 숫자에 대한 처리는 이스케이프 처리에서 제외한다.

URI 문법 형식 표준 RFC3986에 따르면 URL에 특수 문자는 포함될 수 없다. 따라서 특수 문자를 이스케이프 처리함으로써 특수 문자로 인해 야기될 수 있는 문제를 예방한다. 

decode URI는 인코딩된 URI를 받아 인코딩 처리 이전 URI로 바꾼다.

+ encodeURIComponent / decodeURIComponenet

encodeURIComponent함수는 전달된 URI 구성 요소를 인코딩한다. 역시ㅓ encodeURI와 다른 점은 encodeURI의 경우 매개변수로 전달된 문자열을 완전한 URI로 간주하고 encodeURICompoenent의 경우 쿼리 스트링으로도 간주하기 때문에 =, ?, &도 인코딩한다.

+ 암묵적 전역

선언하지 않는 전역 식별자에 깂을 힐당하면 마치 전역 변수처럼 동작한다. 이를 암묵적 변역이라 한다. 전역 객체의 프로퍼티로 추가되기 때문에 delete 연산자로 삭제할 수 있다.

