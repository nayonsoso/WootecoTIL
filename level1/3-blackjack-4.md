### 🔶 Stream API의 탐색 메서드 - findXXX
---

#### 🔸 findAny()
```java
Optional<T> findAny()
```
- 스트림에 요소가 하나라도 있으면, 그 값을 Optional로 감싸 반환한다.
- 값이 하나라도 있으면 즉시 연산을 중단하고 반환한다.
- 이런 특성 때문에 병렬 스트림에서 빠른 성능위해 사용할 수 있다.

```java
public static Direction find(final int dx, final int dy) {
    return Arrays.stream(values())
            .filter(direction -> direction.isSameGradiant(dx, dy) && direction.isSameSign(dx, dy))
            .findFirst()
            .orElseThrow(() -> new IllegalArgumentException("존재하지 않는 이동 방향입니다."));
}
```

- 주로 filter 뒤에 사용하여 조건에 맞는 원소를 탐색하기 위해 사용한다.

<br>

#### 🔸 findFirst
```java
Optional<T> findFirst()
```
- 스트림의 첫번째 값을 Optional로 감싸 반환한다.
- 첫번째 값을 찾을 경우 즉시 연산을 중단하고 반환한다.
- 단일 스트림의 경우 효율적이지만, 병렬 스트림의 경우 전체 중에서 첫번째 요소를 결정하는 작업이 필요하기 때문에 성능이 좋지 않다.

```java
Optional<Product> firstAvailableProduct = products.stream()
                                                  .filter(p -> p.getStock() > 0)
                                                  .findFirst();
```

- 주로 filter 뒤에 사용하여 조건에 맞는 원소를 탐색하기 위해 사용한다.
- 순서가 중요할 때 사용한다.

<br>

### 🔶 Stream API의 조건 검사 메서드 - XXXMatch
---

#### 🔸anyMatch
```java
boolean anyMatch(Predicate<? super T> predicate)
```
- 스트림에 predicate의 조건을 만족하는 요소가 하나라도 있는지를 반환한다.
- 주로 컬렉션의 요소가 하나라도 조건을 만족하는지 확인하기 위해 사용한다.

```
boolean hasMinor = people.stream()
                         .anyMatch(p -> p.getAge() < 18);
```

<br>

#### 🔸allMatch
```java
boolean allMatch(Predicate<? super T> predicate)
```

- 스트림의 모든 요소가 predicate의 조건을 만족하는지 반환한다.
- 주로 컬렉션의 모든 요소가 조건을 만족하는지 확인하기 위해 사용한다.
  
```
boolean allAgesAboveMinPrice = ages.stream()
                                       .allMatch(age -> age.getAmount() >= 100);
```

<br>

#### 🔸noneMatch
```java
boolean noneMatch(Predicate<? super T> predicate)
```

- 스트림의 모든 요소가 predicate의 조건을 만족하지 못하는지 반환한다.
- 사실상 allMatch의 결과에 `!`를 붙인 것과 같지만, 가독성과 직관성을 위해 따로 만든 것이라 생각하면 된다.

```
boolean allAgesAboveMinPrice = ages.stream()
                                       .nonMatch(age -> age.getAmount() < 100);
```
