### 🔶 VO란
---

#### 🔸 개념
- VO란 Value Object로 말 그대로 값을 나타내는 객체이다.
- 값을 객체로 만들면, 검증과 같은 로직을 포함할 수 있다는 장점이 있다. (캡슐화)
- 또한, 'Value Object'라는 정체성에 충실하기 위해, 다음과 같은 조건을 만족시켜야 한다.

<br>

#### 1️⃣ Equals와 HashCode를 재정의
- VO는 값을 나타내야 하기 때문에, 값이 같다면 같다고 판단되어야 한다.
- 이를 위해서 동등성을 보장해줘야 한다.
- 그리고 이를 위해서 Equals와 HashCode를 재정의해야 한다.
- cf. 동일성을 주소값의 일치를 / 동일성은 내부 요소의 일치를 의미한다. [참고](https://github.com/2024-woowacourse-study/level-interview/discussions/20)
- cf. Equals와 HashCode를 함께 재정의해야 하는 이유는, 컬렉션에서 내부 요소를 비교할 때 Equals과 HashCode의 비교가 모두 true가 되어야 정말로 동등하다고 보기 때문이다. [참고](https://github.com/2024-woowacourse-study/level-interview/discussions/33)

#### 2️⃣ 불변 객체
- 식별자가 있는 entity는 내부 값을 바꾸더라도 식별자를 통해서 추적이 가능하다.
- 하지만 VO는 값 자체가 곧 객체를 나타내기 때문에, 값을 바꾸면 이전과 같은 객체인지 파악하기 어려워진다.
- 이를 위해서 VO는 불변 객체여야 한다.
