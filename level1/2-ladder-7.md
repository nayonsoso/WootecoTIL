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
  - Function 인터페이스에 apply 함수는 구현체 내부를 실행한다는 뜻이다.
  - 람다식이라면, 람다식을 실행한다.
  - ⭐즉, 첫번째 인자인 key를 매핑함수의 인자로 넣어 value를 만들겠다는 뜻이다.⭐
