### 🔶 원시값 포장은 언제 해야할까?

---

#### 🔸 리뷰를 받게 된 배경 
- Ladder 클래스에서 높이를 int 형태로 관리하고 있었다.
- 또한 '높이는 2이상이어야 한다'는 검증도 Ladder가 하고 있었다.
- 여기에 대해, 높이를 int로 관리하지 말고 Height 클래스로 만들어 `원시값 포장하라`는 리뷰를 받게 되었다.

<br>

#### 🔸 원시값 포장이란
- 원시 유형의 값을 의미 있는 객체로 포장하는 것이다.
- 객체지향 생활 원칙 중 하나인 `Wrap all primitives and strings`에서 나온 개념이다.

<br>

#### 🔸 원시값 포장의 장점
1. 이름을 통해서 의미를 더 잘 전달할 수 있다.
2. 포장 클래스를 통해 생성과 동시에 검증을 할 수 있기 때문에 무결성이 보장된다.
3. 원시 타입이나 검증 내용을 캡슐화하여 결합도를 낮출 수 있다.
4. 객체의 책임을 분산시킬 수 있다.

<br>

#### 🔸 반영한 코드
```java
public class Height {

    protected static final int MIN_LADDER_HEIGHT = 1;
    protected static final String MIN_HEIGHT_MESSAGE = String.format("사다리의 높이는 최소 %d 이어야 합니다.", MIN_LADDER_HEIGHT);
    private final int height;

    public Height(int height) {
        validateLadderHeight(height);

        this.height = height;
    }

    public int getHeight() {
        return this.height;
    }

    private void validateLadderHeight(int height) {
        if (height < MIN_LADDER_HEIGHT) {
            throw new IllegalArgumentException(MIN_HEIGHT_MESSAGE);
        }
    }
}
```

<br>

#### 🔸 원시값 포장에 대한 생각
- 원시값 포장을 해보니 확실히 코드가 깔끔해졌고, 책임이 적절히 분리된다는 느낌을 받았다.
- 이름으로 의도를 전달할 수 있었기 때문에 가독성이 향상되었다.
- 값의 책임이 늘어나거나 변경된다면, 포장 객체가 있는게 코드 변경을 줄일 것이라는 생각도 들었다.
- 결론적으로 유지보수, 가독성, 확장성을 모두 고려해봤을 때 `값이 하나 이상의 책임을 갖는다면 원시값 포장을 해야겠다`는 결론을 내렸다.
