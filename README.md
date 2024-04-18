# 🪐 Level 1에서 배운 것들

---
추가 공부 필요한것들 TODO
- [ ] 학습 테스트 다 하기 - 함수형 인터페이스 연습하기
- [ ] 내가 나와 한 카톡에 보낸 테스트에 대한 내용 (시그니처를 변경하는 등..) 읽고 정리하기 | | |


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
- 테스트 데이터는 최대한 간결하게 작성하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-2.md)
- 객체의 상호작용을 돕는 객체를 만들어라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-4.md)
- I/O 비용을 최소화하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-3.md)
- 에러 메세지가 포맷을 제시하게 하라. [링크](https://github.com/nayonsoso/WIL/blob/main/level1/1-car-racing-review-1.md)

<br>

## 🚀 2) 사다리 타기

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.02.20 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-1.md) | TDD란 | ✅ |  |
|  | 인텔리제이의 유용한 여러 단축키 | ✅ | |
| 📆[24.02.21 WED](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-2.md) | record | ✅ | ⭐ |
|  |  불변의 객체라면 class보다 record를 쓰는게 이득일까? | ✅ | |
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
| 📆[24.02.28 WED](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-7.md) | computeIfAbsent() 메서드 | ✅ |  |
|  | ConcurrentHashMap 이란 | ✅ | |
| 📆[24.02.29 THU](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-8.md) | 패키지의 존재 이유는 무엇인가 | ✅ |  |
|  | 객체의 이름을 er로 끝내면 안된다는 견해 | ✅ | |
| 📆[24.03.04 MON](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-9.md) | 생성자 대신 정적 팩토리 메서드를 사용했을 때의 장단점 | ✅ | ⭐ |

### 단계별 PR
- 1단계 사다리 생성 PR [링크](https://github.com/woowacourse/java-ladder/pull/328)
- 2단계 사다리 게임 구현 PR [링크](https://github.com/woowacourse/java-ladder/pull/386)

### 피드백 정리
- 패키지 이름으로 계층을, 클래스 이름으로 행위를 표현하게 하라 [링크](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-review-1.md)
- 컨트롤러의 역할은 무엇인가? [링크](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-review-2.md)
- 테스트 코드는 명세화한다는 마음으로 친절하게 작성해야 한다 [링크](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-review-3.md)
- 원시값 포장은 언제 해야할까? [링크](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-review-4.md)
- 생성자에는 필드 초기화 외의 다른 로직이 있어서는 안 된다 [링크](https://github.com/nayonsoso/WIL/blob/main/level1/2-ladder-review-5.md) 

<br>

## 🚀 3) 블랙잭

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.03.05 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-1.md) | Stack보다는 Deque를 써야하는 이유 | ✅ |  |
| 📆[24.03.06 WED](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-2.md) | VO란 | ✅ | ⭐ |
|  | VO vs Dto vs 원시값 포장 객체 | ✅ | |
| 📆[24.03.07 THU](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-3.md) | 가변인자(varargs)의 개념과 특징 | ✅ |  |
| 📆[24.03.08 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-4.md) | Stream의 탐색 함수과 조건 확인 함수 | ✅ |  |
| 📆[24.03.11 MON](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-5.md) | 제네릭과 와일드 카드의 차이 | |  |
|  | 제네릭 클래스나 함수에서 적는 `<T> T`의 의미 | | |
| 📆[24.03.12 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-6.md) | 상태 패턴 | |  |
|  | 전략 패턴 | | |
| 📆[24.03.13 WED](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-7.md) | git의 체리콕 | |  |
| 📆[24.03.14 THU](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-8.md) | 팩토리 패턴 | |  |
|  | 팩토리 클래스 | | |
| 📆[24.03.15 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-9.md) | 가변 객체와 불변 객체 | | |
|  | 쓰레드 안정성과 불변 객체의 연관성 | | |
| 📆[24.03.18 MON](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack-10.md) | EOF 컨벤션을 지켜야 하는 이유 | |  |
|  | The default unnamed package should not be used | | |

### 단계별 PR
- 1단계 블랙잭 게임 실행 PR [링크](https://github.com/woowacourse/java-blackjack/pull/659)
- 2단계 블랙잭 배팅 PR [링크](https://github.com/woowacourse/java-blackjack/pull/759) [링크](https://github.com/woowacourse/java-blackjack/pull/748)

### 피드백 정리
- 

<br>


## 🚀 4) 체스

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.03.19 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-1.md) | JDBC란 | |  |
|  | JDBC를 사용하면 어떻게 벤더사와 관계 없이 자바 코드를 작성할 수 있는가? | | |
| 📆[24.03.20 WED](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-2.md) | autocloseable과 try-with-resource | |  |  
| 📆[24.03.21 THU](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-3.md) | List와 Set의 contains 성능 비교 | |  |
| 📆[24.03.22 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-4.md) | 표준 예외의 종류 | |  |
| 📆[24.03.25 MON](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-5.md) | CheckedException과 UncheckedException의 차이 | |  |
| 📆[24.03.26 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-6.md) | Stream의 flatmap 사용법 | |  |
| 📆[24.03.27 WED](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-7.md) | 무분별한 static 사용을 지양해야 하는 이유 | |  |
| 📆[24.03.28 THU](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-8.md) | JUnit과 AssertJ의 차이 | |  |  
| 📆[24.03.29 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-9.md) | 테스트 코드에서 검증하려는 함수 외의 함수를 호출한다면, 이는 의존적인 테스트인가? | |  |
| 📆[24.04.01 MON](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess-10.md) | 테스트 더블의 종류 | |  |

### 단계별 PR
- 

### 피드백 정리
- 

<br>

