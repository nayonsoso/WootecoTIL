### 🔶 Fixture
----
#### 🔸 도입 배경

- 테스트 코드는 `고정된 환경`에서 `반복 가능한 결과`가 나오도록 작성해야 한다.
- 이를 위해 `테스트를 위한 데이터`을 설정해줘야 한다.
- 이때 테스트 코드 중 여러곳에서 동일한 데이터를 사용하면 코드 중복이 발생한다.
- 이런 코드 중복을 없애주는게 바로 Fixture이다.

➡️ 즉, 반복 가능한 결과를 보장하면서 테스트 코드의 중복을 없애기 위해 사용하는 것

<br>

#### 🔸 개념
Fixture를 구현하기 위해 아래 방법들을 사용할 수 있다.

#### 1. JUnit의 어노테이션 
  - @Before, @BeforeClass, @After, @AfterClass을 사용할 수 있다.
  - 이를 남발해서는 안된다.
  - 테스트 메서드를 이해하기 위해 `다른 부분을 찾아보게 만들어선 안되기 때문`이다.
  - 예를 들어, 테스트 클래스의 필드를 setUp이 초기화하는식으로 fixture를 사용하는 경우, 이를 이해하기 위해 setUp까지 가서 읽어야 한다.
#### 2. 테스트 클래스 안의 private 팩토리 메서드
  - 각각의 테스트 픽스처가 `모두 1회성으로 끝나는 지역변수를 사용`하기 때문에 `테스트간 결합도가 낮아`진다.
  - 어떤 픽스쳐를 만드는지 함수 이름이나 변수명으로 알려줄 수 있기 때문에 `가독성`이 좋아진다.
#### 3. 픽스쳐 클래스 안의 static 팩토리 매서드
  - 픽스쳐가 여러 테스트 코드에 거쳐 사용된다면, static 메서드를 사용할 수도 있다.

<br>

#### 🔸좋은 픽스쳐란
- 중복 코드를 줄여 테스트 코드의 가독성을 높인다.
- 테스트 코드 안에서 픽스쳐를 바로 이해할 수 있다.
- 테스트 실행 시간 단축과 의도치않은 부작용을 피하기 위해 최소한의 테스트 데이터만을 갖는다.

<br>

### 🔶 @ValueSource, @CsvSource, @MethodSource
----
#### 🔸 개념
- JUnit에서 제공하는 어노테이션들이다.
- `@ParameterizedTest`와 함께 사용한다.
- 이를 통해 알 수 있듯, 다양한 파라미터들에 대한 중복 코드를 줄이기 위해 사용한다.

<br>

#### 🔸@ValueSource

- ValueSource에서 지원하는 자료형으로는 short, byte, int, long, float, double, char, String 가 있다.
- 옵션으로 `자료형 소문자 + s` 를 주고, 테스트 메서드의 인자로 받아준다.

```java
@ParameterizedTest
@ValueSource(strings = {"산초", "아톰"})
void validateUserNameLength(String name) {
    assertThat(name.length()).isNotEqualTo(0);
}
```

<br>

#### 🔸@CsvSource

- 옵션으로 `value` 와 `delemeter`가 필요하다.
- delemeter의 디폴트는 쉼표(,) 이다.
- delemeter를 지정할 때는 큰 따옴표(")로 감싸지 말고, 작은 따옴표(')로 감싸야 한다.

```java
@ParameterizedTest
@CsvSource(value = {"산초:true", ":false"} , delimiter = ':') // value와 dele구분자는 디폴트가 ,이다
void validateUserNameLength2(String name, boolean result) {
    boolean isValid = name.length() > 0;
    assertThat(isValid).isEqualTo(result);
}
```

- CsvSource의 value에는 enum도 올 수 있다.
- 사용자 정의 class도 올 수 있지만, csv 테스트만을 위한 함수를 추가해줘야 하므로 패스한다.

```java
enum Status {
    NEW, IN_PROGRESS, COMPLETED
}

@ParameterizedTest
@CsvSource({"NEW", "IN_PROGRESS", "COMPLETED"})
void testWithEnum(Status status) {
    assertNotNull(status);
}
```

<br>

#### 🔸@MethodSource
- 테스트에 필요한 객체를 만들어주는 함수를 호출하고, 그 결과를 인자로 받아 사용한다.
- 기본 타입, 객체, enum, 사용자 정의 클래스 등 거의 모든 타입의 파라미터를 테스트 메소드에 전달할 수 있다.
- MethodSource 어노테이션의 속성값으로 함수의 이름이 들어간다.
- 함수는 아래 조건을 만족해야 한다.
  - static 메소드
  - Stream, Iterable, 또는 Iterator 타입을 반환해야 한다.
  - Stream<T>에서 T안에 들어가는게 static 메소드가 테스트의 파라미터로 반환할 자료형이다.
- 아래의 경우에 유용하다.
  - List를 파라미터로 받고 싶을 때
  - 다양한 자료형의 목록을 파라미터로 받고 싶을 때

```java
static Stream<List<String>> createValidNames() { // Stream<반환하는 자료형>
    return Stream.of(
            List.of("A"),
            List.of("A", "B", "C", "D", "E", "F", "G", "H", "I")
    );
}

@DisplayName("1명 이상 10명 이하면 예외를 발생하지 않는다.")
@ParameterizedTest
@MethodSource("createValidNames") // 함수의 이름
void validateNamesSize(List<String> names) { // 함수가 반환하는 자료형
    assertThatCode(() -> new PlayerNames(names))
            .doesNotThrowAnyException();
}

static Stream<Arguments> createCard() {
    return Stream.of(
            Arguments.of(TWO_HEART, 2),
            Arguments.of(TEN_HEART, 10),
            Arguments.of(ACE_HEART, 11)
    );
}

@DisplayName("숫자로 계산한 값을 반환한다.")
@ParameterizedTest
@MethodSource("createCard")
void getValue(Card card, int value) {
    int actual = card.getLetterValue();
    int expected = value;

    assertThat(actual).isEqualTo(expected);
}
```
