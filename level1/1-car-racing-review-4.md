### 🔶 객체의 상호작용을 돕는 객체를 만들어라.

---

#### 🔸 리뷰를 받게 된 배경 
- 이전까지는 객체를 만들고, 이들을 열심히 조합해서 결과물을 내는 것이 controller라고 생각했다.
- 하지만 controller는 domain과 view의 상호작용을 돕는 역할을 할 뿐이고,
- 객체간의 상호작용을 돕기위해서는 다른 객체가 필요하다는 피드백을 듣게 되었다.
  - controller는 view와 domain의 상호작용을 돕는다.
  - 그렇다면 domain과 domain의 상호작용을 돕는건? → domain
- 그리고 view에 원시값을 전달해야 한다는 나의 선입견과는 다르게,
- 객체의 상호작용을 돕는 객체에는 `생성자나 함수의 인자로 다른 객체를 줄 수 있다`는 것도 배울 수 있었다.
- 위 피드백을 반영해서 아래와 같이 코드를 작성해봤다.

<br>

#### 🔸 반영한 코드

```java
// move가 리턴하는 것은 Map<CarName, Position> 이다.
public Map<CarName, Position> move() {
    cars.forEach(Car::move);

    Map<CarName, Position> result = new LinkedHashMap<>();
    for (Car car : cars) {
        result.put(car.getName(), car.getPosition());
    }
    return result;
}
```

```java
private void race(final int raceCount, final RaceParticipants raceParticipants) {
    RaceHistory raceHistory = new RaceHistory();
    for (int i = 0; i < raceCount; i++) {
        raceHistory.add(raceParticipants.move()); // move의 결과를 인자로 전달한다.
    }
}
```

```java
public class RaceHistory {
    private final List<Map<CarName, Position>> history = new LinkedList<>();

    // Map<String, Integer> 가 아니라 Map<CarName, Position>으로 인자를 받는다.
    public void add(Map<CarName, Position> roundResult) {
        history.add(roundResult);
    }
}
```
