### 🔶 I/O 비용을 최소화하라.
---

#### 🔸 리뷰를 받게 된 배경 
- 자동차 경주 미션에서는 각 라운드의 결과를 출력해야 했다.
- 하지만 이를 `각 라운드 종료 후` 할지, 아니면 `모든 라운드 종료 후` 한번에 출력할지를 나누어 생각해볼 수 있다.
- 나는 I/O 비용을 고려해야 한다는 것을 모르고 전자를 선택했지만, **I/O 비용을 최소화하라는 리뷰**를 받았다.
- 따라서 리뷰해주신대로, 경기의 결과를 한 객체에 저장해두었다가 한번에 I/O 출력하도록 바꿔주었다.

<br>

#### 🔸 반영한 코드


```java
private void race(final int raceCount, final RaceParticipants raceParticipants) {
    outputView.printRaceResultHeaderMessage();
    RaceHistory raceHistory = new RaceHistory();
    for (int i = 0; i < raceCount; i++) {
        raceHistory.add(raceParticipants.move());
    } // raceHistory에 모아두었다가 한번에 출력

    RaceResultResponse raceResultResponse = new RaceResultResponse(raceHistory.getRaceHistory());
    RaceWinnerResponse raceWinnerResponse = new RaceWinnerResponse(raceHistory.getFinalWinners());

    outputView.printRaceHistory(raceResultResponse.toResult());
    outputView.printRaceWinners(raceWinnerResponse.toWinner());
}
```
