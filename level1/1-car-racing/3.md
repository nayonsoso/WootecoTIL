### 🔶 rebase

---

#### 🔸 내용
- git에서는 커밋이 처음 생성된 브랜치를 `base branch` 라고 한다.
- rebase는 이 base 브랜치를 재정의하는 과정을 의미한다.
  - base를 재정의하므로 `rebase`인 것.
- rebase는 아래 두 상황에서 사용된다.
  - 1)) 기존의 커밋을 수정하는 경우 (순서, 메세지, squash 등)
    - 기존의 base 브랜치를 재정의하는 과정이므로 reabse라고 할 수 있다.
  - 2)) 한 브랜치의 커밋을 다른 브랜치의 최신 커밋으로 옮기는 경우
    - 커밋이 새로운 base 브랜치로 이동하므로 base 브랜치가 재정의되었다. 즉, rebase라고 할 수 있다.

#### 🔸 rebase와 merge의 차이

- merge
  - merge는 두 브랜치의 커밋을 하나의 브랜치로로 합치는 작업이다.
  - 머지를 하면 두 브랜치의 히스토리가 모두 보존되며, "머지 커밋"이라는 특별한 커밋이 생성된다.
  - 이 과정에서 충돌이 나면 한번에 해결할 수 있다.
- rebase
  - 리베이스는 한 브랜치의 변경 사항을 다른 브랜치의 끝에 차례대로 적용하는 과정이다.
  - 충돌이 발생하면, 충돌이 일어난 부분부터 하나씩 해결해야 한다.
  - 리베이스는 기존의 커밋들을 새로운 기반 위에 다시 배치하는 것이므로, 커밋의 해시값이 변경된다.
  - cf. 커밋의 해시값은 커밋의 내용, 부모의 해시값, 커밋 메세지, 커밋 작성자, 커밋 시점에 의해 결정된다.
    <img width="700" src="https://github.com/nayonsoso/WIL/assets/76177848/7b8bf2ef-dd58-4e60-a71f-60b38916d596" style="display: block;">

<br>

### 🔶 커밋 메세지 수정하는 방법

---

- 터미널에 `git rebase -i HEAD~N`를 입력한다.
  - 여기서 N은 최신 순으로 몇번째인지를 의미한다.
  - `-i`는 "interactive"의 약자이다.
  - 즉, 사용자는 커밋에 대한 다양한 작업을 수행할 수 있는 인터페이스를 제공받게 된다.
- 수정하고 싶은 커밋 옆에 있는 `pick`을 `reword` 또는 `r`로 변경하고 저장한 후 에디터를 종료한다.
  <img width="700" src="https://github.com/nayonsoso/WIL/assets/76177848/d502660c-6571-49fe-8154-8ae40c3ee04b" style="display: block;">
- 이후 커밋 메세지를 수정할 수 있는 에디터가 열리면 메세지를 수정한다.
  <img width="700" src="https://github.com/nayonsoso/WIL/assets/76177848/1214a671-7e51-41b6-9f58-2feb99c9ad9a" style="display: block;">
- 주의) 이때 커밋하지 않은 변경사항이 있는 경우 아래와 같은 에러 메세지가 발생한다.
  <img width="700" src="https://github.com/nayonsoso/WIL/assets/76177848/f94e2701-e857-4470-bf14-dba6c6a46e18" style="display: block;">
- 변경사항이 없도록 모두 커밋한 후 `git rebase --continue`를 입력하면, rebase를 진행할 수 있다.
  <img width="700" src="https://github.com/nayonsoso/WIL/assets/76177848/08988a84-ed0d-45e7-a045-b2863e1bcb0b">
