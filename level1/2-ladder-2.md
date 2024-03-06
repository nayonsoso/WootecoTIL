### 🔶 record

---

#### 🔸 도입 배경
- 자바 16에서 정식적으로 추가되었다.
- `불변 데이터`를 전달할 때가 있다. (Immutable)
- 이전에는 bolierplate 필드와 베서드가 포함된 클래스를 작성해야 했다.
  - bolierplate 란, 반복적으로 사용되는 코드를 말한다.
  -  e.g. getter, setter, equals, hashCode
- 이는 사소한 실수와 혼동을 야기했다.
  - 예를 들어, 클래스에 필드를 추가하면 equals와 hashCode의 코드를 변경해야 했다.
- 이런 보일러 플레이트 코드 때문에 단순히 '값을 가지는 불변 객체'라는 의미가 퇴색되었다.

<br>

#### 🔸 개념
- 불변 데이터 객체를 만들기 위해 사용한다.
- record 클래스의 선언부에 `필드의 타입과 이름`를 작성하면 된다.
  - 이 모습이 마치 생성자 같다.😳
- 아래 목록은 컴파일러에 의해 자동 생성된다.
  - 필드
    - `private final` 필드
  - 생성자
    - `public allArgumentConstructor`
  - 메서드
    - `equals`
    - `hashcode`
    - `toString`
    - 각 필드에 대한 `getter`

<br>

#### 🔸 record의 생성자
- 레코드의 생성자가 필드 초기화 이외의 기능을 하게 하고 싶다면, `사용자 정의 생성자`를 만들 수 있다.
- 주로 검증의 기능을 추가하기 위해 사용한다.

<br>

1)) 매개변수 목록이 없는 `컴팩트 생성자`를 만들 수 있다.
```java
public record Name(String name) {
    public Name {
        validateLength(name);
    }
}
```

<br>

2)) 매개변수를 갖는 생성자도 만들 수 있다.
```java
public record Name(String name) {
    public Name(String name) {
        validateLength(name);
    }
}
```

- 단, 컴팩트 생성자로 만든 all args constructor과 일반 생성자로 만든 all args constructor는 공존할 수 없다.

<br>

#### 🔸 그 외 특징
- 필드
  - `private final` 필드를 추가할 수 있다.
  - `static` 필드를 추가할 수 있다.
  - 이외의 필드는 선언할 수 없다.
  - e.g. public static final => O, private => X
- 메서드
  - `static` 메서드를 추가할 수 있다.
  - 다른 일반적인 메서드들도 추가할 수 있다.
  - e.g. public => O, static => O
- 상속
  - 다른 클래스를 상속받을 수도, 다른 클래스가 record를 상속할 수도 없다.
    - record는 final 클래스이기 때문!
  - 인테페이스는 구현할 수 있다.

#### 🔸 특이점
- 컴팩트 생성자에서 필드는 언제 초기화되는가?
  - 컴팩트 사용자에서 호출하는 함수들을 다 호출한 이후 초기화된다.
- 따라서, 검증 함수를 호출하기 위해서
  - `this`로 참조하면 에러가 발생한다.
  - `매개변수`로 검증하려는 값을 받아야 에러가 발생하지 않는다.


**에러가 발생하는 코드**
```java
public record PlayerNames(List<String> names) {

    public PlayerNames {
        validateDuplicate();
    }

    private void validateDuplicate() {
        // ❗this로 받으면 에러가 발생❗
        boolean isDuplicated = this.names.stream().distinct().count() != this.names.size();

        if (isDuplicated) {
            throw new IllegalArgumentException(NAME_DUPLICATE_MESSAGE);
        }
    }
}
```


**정상 작동 코드**
```java
public record PlayerNames(List<String> names) {

    public PlayerNames {
        validateDuplicate(names);
    }

    // ❗함수의 매개변수로 받아야 에러가 발생하지 않는다.❗
    private void validateDuplicate(names) {
        boolean isDuplicated = names.stream().distinct().count() != names.size();

        if (isDuplicated) {
            throw new IllegalArgumentException(NAME_DUPLICATE_MESSAGE);
        }
    }
}
```


