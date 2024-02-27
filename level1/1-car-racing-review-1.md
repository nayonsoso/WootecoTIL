### 🔶 에러 메세지가 포맷을 제시하게 하라.

---

#### 🔸 리뷰를 받게 된 배경 
- 에러 메세지를 enum으로 관리하는 상태에서 에러 메세지 풍부화를 위해서 details를 string으로 줬더니 받은 피드백이었다.
- 에러 메세지를 enum으로 관리했을 때 얻는 이점은 아래와 같다.
    - 에러 메세지를 한 곳에 관리할 수 있다.
    - 에러 메세지의 Type을 지정할 수 있다.
      - 어떤 예외인지를 enum의 name으로 알 수 있어 가독성이 좋다.
      - 테스트 코드에서 에러 메세지를 검증하기 편리하다.
- 에러 메세지 풍부화를 위해서 detail 정보를 주는 것은 좋은 것 같다.
- 하지만 내가 자동차 경주 미션에서 준 details는 외부에서만 알 수 있는 추가 정보가 아니라, <br> 코드 안에서 사용하는 상수에 대한 것이므로, enum 안에서 포매팅할 수 있는 것이었다.
    - enum 안에서 포매팅할 수 있는 것을 밖으로 빼주는 것은 <br> enum으로 메세지를 관리하는 장점을 무시하는 행위라고 생각되었다.
- 따라서 리뷰해주신대로, 에러 메세지 enum이 포멧을 제시하도록 수정해주었다.

<br>

#### 🔸 반영한 코드

```java
public enum ErrorMessage {
    // MIN_LENGTH와 MAX_LENGTH는 필요한 곳에서 바로 선언하되, static으로 선언되어있는 상태이므로 import할 수 있다.
    INVALID_CAR_NAME_LENGTH("자동차 이름의 길이는 %d글자에서 %d글자 사이여야 합니다.", MIN_NAME_LENGTH, MAX_NAME_LENGTH);

    private final message;

    ErrorMessage(String message) {
        this.message = message;
    }
}
```
