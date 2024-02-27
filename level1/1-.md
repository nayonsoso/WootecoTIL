### 🔶 테스트 데이터는 최대한 간결하게 작성하라.

---

#### 🔸 리뷰를 받게 된 배경 

- 자동차의 이름을 1~5 글자까지 허용하는 경우, 모든 경우에 대해서 테스트 데이터를 넣어주었다.
- 자동차 움직임 검증을 할 때도, `“true, true”`와 `“true, false”`를 통해 각각 두칸, 한칸 갔는지를 검증했다.
- 하지만 아래와 같이, `테스트 데이터는 최대한 간결하게 작성하라` 는 피드백을 받게 되었다.
    - 이름을 1 글자와 5 글자만 검사
    - {“true, true”, “true, false”}를 {“true”, “false”}로 수정
- 테스트 데이트를 간결하게 작성해야 하는 이유는 아래와 같다.
    - 무엇이 경계값인지를 명확히 알 수 있다.
    - 무의미한 테스트 비융을 줄인다.
- 따라서 리뷰해주신대로, **경계값만 포함하도록 & 필요한 부분만 검증하도록** 코드를 수정해 주었다.

<br>

#### 🔸 반영한 코드

```java
@ParameterizedTest
@ValueSource(strings = {"일", "오오오오오"}) // 경계값만 테스트 데이터로 넣어주었다.
void 자동차_이름이_생성_성공(final String name) {
    final CarName carName = new CarName(name);

    assertThat(carName.getName()).isEqualTo(name);
}
```

```java
@Test
void 자동차_위치를_비교한다() {
    // 테스트에 반드시 필요한 부분만 검증할 수 있게 했다.
    final Car car1 = new Car("car1", new MockMovingStrategy(List.of(true)));
    final Car car2 = new Car("car2", new MockMovingStrategy(List.of(false)));

    car1.move();
    car2.move();

    assertSoftly(softly -> {
        softly.assertThat(car1.compareTo(car1)).isEqualTo(0);
        softly.assertThat(car1.compareTo(car2)).isEqualTo(1);
        softly.assertThat(car2.compareTo(car1)).isEqualTo(-1);
    });
}
```
