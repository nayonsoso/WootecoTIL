# 🪐

---
추가 공부 필요한것들 TODO
- [x] 레이어를 나눠야 하는 이유
- [ ] static 사용을 지양해야 하는 이유
- [ ] 객체를 불변하게 관리하는 방법 
- [ ] 디자인 패턴
- [ ] csv 테스트(?)
- [ ] 레코드
- [ ] supplier.get() 의 의미
- [ ] 제네릭 클래스나 함수에서 `<T> T` 를 쓰는 이유


---

## 🚀 1) 자동차 경주

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.02.14 WED](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-1.md) | 함수형 인터페이스 | ✅ | ⭐ |
|  | 함수형 인터페이스 API | ✅ | |
|  | 정적 팩토링 메소드의 네이밍 규칙 | ✅ | |
| 📆[24.02.15 THU](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-2.md) | God Class를 만들면 안되는 이유 | ✅ | ⭐ |
|  | Dto의 역할 | ✅ | |
| 📆[24.02.16 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-3.md) | rebase란 |✅| |
| | 커밋 메세지 수정하는 방법 |✅| |
| 📆[24.02.19 MON](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-4.md) | IntelliJ에서 테스트 커버리지 보는 방법 | ✅ | |
|  | IntelliJ에서 프로젝트의 모든 파일 한번에 정렬하는 방법 | ✅ | |

### 단계별 PR
- 1단계 자동차 경주 구현 PR [링크](https://github.com/woowacourse/java-racingcar/pull/682)
- 2단계 리팩토링 PR [링크](https://github.com/woowacourse/java-racingcar/pull/814)

### 피드백 정리
- 에러 메세지가 포맷을 제시하게 하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-1.md)
- 테스트 데이터는 최대한 간결하게 작성하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-2.md)
- I/O 비용을 최소화하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-3.md)
- 객체의 상호작용을 돕는 객체를 만들어라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-4.md)

<br>

## 🚀 2) 사다리 타기

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.02.20 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-1.md) | TDD란 | ✅ |  |
|  | 인텔리제이의 유용한 여러 단축키 | ✅ | |
| 📆[24.02.21 WED](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-2.md) | record | ✅ | ⭐ |
|  |  불변의 객체라면 class보다 record를 쓰는게 무조건 이득일까? | ✅ | |
| 📆[24.02.22 THU](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-3.md) | Fixture란 | ✅ |  |
|  | @ValueSource, @CsvSource, @MethodSource | ✅ | |
| 📆[24.02.23 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-4.md) | 단위 테스트의 정의 | ✅ | ⭐ |
|  | 좋은 단위테스트란 (FIRST 원칙) | ✅ | |
|  | 단위 테스트에 대한 견해와 나의 결론 | ✅ | ⭐ |
| 📆[24.02.26 MON](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-5.md) | 얕은 복사와 깊은 복사 | ✅ |  |
|  | 방어적 복사 | ✅ | |
|  | 방어적 복사의 적용 | ✅ | ⭐ |
| 📆[24.02.27 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-6.md) | 테스트 코드에서 for문을 지양해야 하는 이유 | ✅ |  |
|  | assertAll의 장점과 사용법 | ✅ | |
| 📆[24.02.28 WED](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-7.md) | computeIfAbsent의 사용법 | |  |
|  | ConcurrentHashMap 이란 | ✅ | |
| 📆[24.02.29 THU](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-8.md) | 피드백 내용으로 채우기 | |  |
| 📆[24.03.04 MON](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-9.md) | | |  |
|  | stub, mock, spy는 무엇인가 | | |
|  | 생성자 대신 정적 팩토리 메서드를 사용했을 때의 장단점 | | |

### 단계별 PR
- 1단계 사다리 생성 PR [링크](https://github.com/woowacourse/java-ladder/pull/328)
- 2단계 사다리 게임 구현 PR [링크](https://github.com/woowacourse/java-ladder/pull/386)

### 피드백 정리
- 
- 

## 🚀 3) 블랙잭

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆24.03.05 TUE | | |  |
| 📆24.03.06 WED | | |  |
| 📆24.03.07 THU | | |  |
| 📆24.03.08 FRI | | |  |
| 📆24.03.11 MON | | |  |
| 📆24.03.12 TUE | Stack보다는 Deque를 | |  |
|  | VO와 Dto - 누가 정리해준 글 읽기 | | |
|  | 가변인자 | | |
|  | stream.anyMatcher | | |
|  | 객체 안에서 캐싱을 하는 방법 | | |
|  | State 전략 패턴 | | |
|  | 함수형 인터페이스 연습하기 | | |
|  | reduce와 mapToInt.sum() 간의 차이와 무엇을 써야 하는지 정리 | | |
|  | 전략 패턴에 대해서 공부하기 | | |
|  | EOF 컨벤션을 지켜야 하는 이유 | | |
|  | 내가 나와 한 카톡에 보낸 테스트에 대한 내용 (시그니처를 변경하는 등..) 읽고 정리하기 | | |
| 📆24.03.13 WED | | |  |
|  | 가변 객체와 불변 객체 | | |
|  | 쓰레드 안정성과 불변 객체의 연관성 | | |
| 📆24.03.14 THU | | |  |
|  | 팩토리 클래스 | | |
|  | 캐싱하는 방법 (e.g. 카드 캐싱) | | |
|  | The default unnamed package should not be used | | |
| 📆24.03.15 FRI | | | |
| 📆24.03.18 MON | | |  |
| 📆24.03.19 TUE | | |  |
| 📆24.03.20 WED | | |  |
| 📆24.03.21 THU | | |  |
| 📆24.03.22 FRI | | |  |
| 📆24.03.25 MON | | |  |
| 📆24.03.26 TUE | | |  |
| 📆24.03.27 WED | | |  |
| 📆24.03.28 THU | | |  |
| 📆24.03.29 FRI | | |  |
