### 🔶 flatMap 사용법
---

#### 🔸 자바 공식 문서
```java
<R> Stream<R> flatMap(Function<? super T, ? extends Stream<? extends R>> mapper);
```

> Returns **a stream consisting of the results of** replacing each element of this stream with the contents of a mapped stream produced by applying the **provided mapping function** to each element. 

<br>

#### 🔸 개념

- 여러개의 스트림을 하나의 스트림으로 만들어줘야 하는 경우가 있다.
- 중첩된 스트림을 사용하거나, 이중 for 문에서 스트림을 사용하는 경우 등..
- flatMap의 메서드 시그니터에서 알 수 있다시피, flatMap은 인자로 Funtion<A, B>를 받는다.
- flatMap은 A에 해당하는 것에 대해 함수를 실행하여 B로 만들어주되, 이 결과를 하나의 스트림으로 만들어준다.
    - ① 어떤 값에 대해 스트림을 만드는 매핑 함수가 주어지면 
    - ② 모든 요소에 대해 매핑 함수를 실행하고 
    - ③ 그 결과를(여러 스트림)을 하나의 스트림으로 변환해주는 역할을 한다.
- Stream의 map함수와 비슷하면서, 더 나아가 그 결과를 하나의 Stream으로 만들어준다.

<br>

#### 🔸 사용 예시

```java
private static final Map<String, Position> CACHE;

static {
        CACHE = Arrays.stream(File.values())
                .flatMap(Position::createPositionWithEachRank)
                .collect(Collectors.toMap(
                        position -> toKey(position.file, position.rank),
                        position -> position));
    }

    private static Stream<Position> createPositionWithEachRank(File file) {
        return Arrays.stream(Rank.values())
                .map(rank -> new Position(file, rank));
    }
```

- createPositionWithEachRank은 file을 받아 Stream<Position>을 반환하는 매핑 함수이다.
- 첫번째 static 블록에서는 이를 사용해 모든 file에 대해 Stream<Position>을 각각 만들고, 이를 하나로 합친다.
- 이후 Position을 사용해 Map 형태로 만들어준다.
