### 🔶 Stack보다는 Deque를 써야하는 이유	
---

#### 🔸 자바 공식 문서
> A more complete and consistent set of LIFO stack operations is provided by the Deque interface and its implementations, which should be used in preference to this class.

- 번역 : Deque 인터페이스와 그 구현체는 보다 완벽한 LIFO 스택을 제공한다. 이는 Stack 클래스보다 우선적으로 사용되어야 한다.
- [공식 문서](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Stack.html)에도 나와있을 만큼, Stack 보다는 Deque를 사용해야 하는 것은 중요하다.

<br>

#### 🔸 이유 1 : Deque는 더 LIFO에 충실하다.
- Stack은 Vector를 상속하기 때문에, 인덱스를 통한 접근이 가능하다.
- 이는 LIFO 자료구조에서 기대하지 못한 기능이므로, 개발자가 실수를 할 여지가 있다.
- 반면 Deque는 위 또는 아래에만 접근 가능하기 때문에 LIFO에 더 충실하다고 할 수 있다. 

<br>

#### 🔸 이유 2 : Deque는 더 성능이 좋다.
- Vector는 동기화된 메서드들로 이루어져있기 때문에 단일 쓰레드 환경에서는 오버헤드가 발생한다.
- 반면 Deque는 동기화되어있지 않으므로 단일 쓰레드 환경에서는 더 성능이 좋다.
- 심지어, 멀티 쓰레드 환경에서도 Stack 보다 Deque의 구현체를 사용하는게 더 성능이 좋다.

<br>

#### 🔸 Deque의 구현 클래스와 적절한 사용처
- `ArrayDeque` : 단일 쓰레드 환경에서 사용
- `LinkedList` : Deque에 index를 사용하고 싶을 때 사용
- `ConcurrentLinkedDeque` : 멀티 쓰레드 환경에서 사용
