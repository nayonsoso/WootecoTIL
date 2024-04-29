# What I learned in Wooteco 🪐 

---

### Level 1 : Java and OOP

| Title | Keyword | Date |
|-------|---------|------|
| Car racing | Unit test | [24.02.14 ~ 24.02.19]() |
| Ladder game | TDD |  [24.02.20 ~ 24.03.04]() |
| Blackjack | Clean code | [24.03.05 ~ 24.03.18]() |
| Chess | OOP, DB | [24.03.19 ~ 24.04.01]() |



추가 공부 필요한것들 TODO
- [ ] 학습 테스트 다 하기 - 함수형 인터페이스 연습하기
- [ ] 내가 나와 한 카톡에 보낸 테스트에 대한 내용 (시그니처를 변경하는 등..) 읽고 정리하기
- [ ] 제네릭과 와일드카드 차이점 : [링크](https://inpa.tistory.com/entry/JAVA-%E2%98%95-%EC%A0%9C%EB%84%A4%EB%A6%AD-%EC%99%80%EC%9D%BC%EB%93%9C-%EC%B9%B4%EB%93%9C-extends-super-T-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)


---



## 🚀 3) 블랙잭

| 날짜 | 내용 | 완료 | 중요 |
|--------|--------|--------|--------|
| 📆[24.03.05 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/1.md) | Stack보다는 Deque를 써야하는 이유 | ✅ |  |
| 📆[24.03.06 WED](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/2.md) | VO란 | ✅ | ⭐ |
|  | VO vs Dto vs 원시값 포장 객체 | ✅ | |
| 📆[24.03.07 THU](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/3.md) | 가변인자(varargs)의 개념과 특징 | ✅ |  |
| 📆[24.03.08 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/4.md) | Stream의 탐색 함수과 조건 확인 함수 | ✅ |  |
| 📆[24.03.11 MON](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/5.md) | 제네릭 | ✅ | ⭐ |
|  | 와일드 카드 | ✅ | |
| 📆[24.03.12 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/6.md) | 상태 패턴 | ✅ | ⭐ |
| 📆[24.03.13 WED](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/7.md) | 전략 패턴 | |  |
| 📆[24.03.14 THU](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/8.md) | 팩토리 패턴 | |  |
|  | 팩토리 클래스 | | |
| 📆[24.03.15 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/9.md) | 가변 객체와 불변 객체 | | |
|  | 쓰레드 안정성과 불변 객체의 연관성 | | |
| 📆[24.03.18 MON](https://github.com/nayonsoso/WIL/blob/main/level1/3-blackjack/10.md) | EOF 컨벤션을 지켜야 하는 이유 | |  |
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
| 📆[24.03.19 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/1.md) | JDBC란 | |  |
|  | JDBC를 사용하면 어떻게 벤더사와 관계 없이 자바 코드를 작성할 수 있는가? | | |
| 📆[24.03.20 WED](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/2.md) | autocloseable과 try-with-resource | |  |  
| 📆[24.03.21 THU](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/3.md) | git의 체리콕 | ✅ |  |
| 📆[24.03.22 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/4.md) | 표준 예외의 종류 | |  |
| 📆[24.03.25 MON](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/5.md) | CheckedException과 UncheckedException의 차이 | |  |
| 📆[24.03.26 TUE](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/6.md) | Stream의 flatmap 사용법 | ✅ |  |
| 📆[24.03.27 WED](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/7.md) | 무분별한 static 사용을 지양해야 하는 이유 | |  |
| 📆[24.03.28 THU](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/8.md) | JUnit과 AssertJ의 차이 | |  |  
| 📆[24.03.29 FRI](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/9.md) | 테스트 코드에서 검증하려는 함수 외의 함수를 호출한다면, 이는 의존적인 테스트인가? | |  |
| 📆[24.04.01 MON](https://github.com/nayonsoso/WIL/blob/main/level1/4-chess/10.md) | 테스트 더블의 종류 | |  |

### 단계별 PR
- 

### 피드백 정리
- 

<br>

