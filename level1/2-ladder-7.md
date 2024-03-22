### 🔶 Map의 computeIfAbsent() 메서드와 그 자매품
---

#### 🔸 공부 배경
- 네오의 학습 테스트를 하는 도중 캐싱에 대해 배우게 되었다.
- 그리고 아래 코드를 마주했다.
```java
record Car(String name, Position position) {
    private static final Map<String, Car> CACHE = new ConcurrentHashMap<>();

    public static Car of(final String name, final Position position) {
        return CACHE.computeIfAbsent(toKey(name, position), key -> new Car(key, position));
    }

    private static String toKey(final String name, final Position position) {
        return name + position.value();
    }
}
```

<br>

#### 🔸 computeIfAbsent
- 개념
  - key에 해당하는 value가 없으면 그 key와 value쌍을 put한다.
  - 그리고 value를 반환해준다.
- 내부 구현
```java
default V computeIfAbsent(K key, Function<? super K, ? extends V> mappingFunction) {
    Objects.requireNonNull(mappingFunction);
    V v;
    if ((v = get(key)) == null) {
        V newValue;
        if ((newValue = mappingFunction.apply(key)) != null) {
            put(key, newValue);
            return newValue;
        }
    }

    return v;
}
```

- `Objects.requireNonNull(mappingFunction);`
  - Function 인터페이스의 구현이 필수적이라는 뜻이다.
  - Function 인터페이스 구현 예시 : score -> score * 2
- `if ((v = get(key)) == null)` 블럭
  - map에 키에 해당하는 값이 null 즉, 없으면 만들어서 넣어주고
  - null 이 아니면 그 값을 그대로 반환한다.
- `mappingFunction.apply(key)`
  - Function 인터페이스에 대한 apply 함수는 구현체 내부를 실행한다는 뜻이다.
  - 람다식이라면, 람다식을 실행한다.
  - ⭐즉, 첫번째 인자인 key를 매핑함수의 인자로 넣어 value를 만들겠다는 뜻이다.⭐
- 사용 예시
    ```java
    public static Car of(final String name, final Position position) {
        // ❗첫번째 인자인 toKey()가 두번째 인자의 key로 들어가고 있다❗
        return CACHE.computeIfAbsent(toKey(name, position), key -> new Car(key, position));
    }
    ```

<br>

#### 🔸 computeIfAbsent의 자매품

- computeIfAbsent(Key, Function)
  - 키에 해당하는 값이 없으면, 함수를 실행하여 새 값을 저장한다.
  - `map.computeIfAbsent(key, k -> new Value(k));`
- computeIfPresent(Key, BiFunction)
  - 키에 해당하는 값이 있으면, 함수를 실행하여 값을 업데이트한다.
  - 키에 해당하는 값이 없으면 실행하지 않는다.
  - 함수 실행 결과가 null이면 키를 제거한다.
  - `map.computeIfPresent(key, (k, v) -> newValue);`
- compute(Key, BiFunction)
  - 키에 대해 함수를 실행하여 값을 업데이트한다.
  - 값이 있으면 업데이트, 값이 없으면 추가를 한다.
  - 함수 실행 결과가 null이면 키를 제거한다.
  - `map.compute(key, (k, v) -> newValue);`

<br>

#### 🔸 compute와 put의 비교

- 공통점 : 둘 다 키에 대응하는 값이 있으면 업데이트, 값이 없으면 추가한다.
- 차이점 : put은 단순한 입력인 반면, compute는 key를 인자로 받아 동적으로 계산한다.

```java
public class MapExamples {
    public static void main(String[] args) {
        Map<String, Integer> map = new HashMap<>();

        map.put("apple", 10);
        // apple의 값을 기존 값+10으로 업데이트한다.
        map.computeIfPresent("apple", (key, value) -> value + 10);
        // banana의 값을 찾고, 있으면 +5를 업데이트, 없으면 5로 초기화한다.
        map.compute("banana", (key, value) -> (value == null) ? 5 : value + 5);
        // orange의 값이 없을 경우에만 3으로 초기화한다.
        map.computeIfAbsent("orange", key -> 3);

        System.out.println(map); // 출력 결과: {apple=20, banana=5, orange=3}
    }
}
```
