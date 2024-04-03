### 🔶 테스트 코드는 명세를 드러낸다는 마음으로 친절하게 작성해야 한다.

---

#### 🔸 리뷰를 받게 된 배경 
- 테스트코드를 작성할 때 when 단계에서 Ladder(3,2) 라고 작성했다.
- 그랬더니, 테스트 코드는 동료 개발자들이 함께 보는 것이기 때문에
- 값이 어떤 의미를 갖는지를 명확히 나타내달라는 리뷰를 받게 되았다.

<br>

#### 🔸 리뷰를 통해 알게된 점
- 테스트는 명세의 기능을 한다는 것을 머리로는 알고 있었지만,
- `명세의 역할을 잘 하기 위해 무엇을 할 수 있는지`는 고민해보지 않았던 것 같다.
- 이번 리뷰를 통해 테스트 코드에서 변수명으로 의미 전달이 가능하다는걸 배울 수 있었다.
- 그리고 `테스트 코드를 친절하게 작성하라`는 말의 의미를 더 깊이 이해하게 되었다.

<br>

#### 🔸 반영한 코드
```java
@DisplayName("사다리는 높이 만큼의 라인을 갖는다.")
@Test
void ladderHasLines() {
    // ❗ 값이 갖는 의미를 변수 이름을 통해 보여주었다.
    Height height = new Height(3);
    int playerSize = 9;

    Ladder ladder = Ladder.of(height, playerSize, mockSticksGenerator());
    int actualHeight = ladder.getHeight();

    assertThat(actualHeight).isEqualTo(height.getHeight());
}
```


