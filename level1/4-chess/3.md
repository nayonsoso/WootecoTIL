### 🔶 cherry-pick
---

#### 🔸 개념
- 다른 브랜치의 커밋을 현재 브랜치로 가져올 때 사용할 수 있다.
- 하나의 커밋이나 여러 커밋을 선택할 수 있다. 범위 지정도 가능하다.
- 선택한 커밋이 반영되는 곳은 현재 브랜치의 HEAD 부분이다.

<br>

#### 🔸 사용법
```bash
# 커밋 하나
git cherry-pick <commit-hash>

# 여러 커밋 : 공백으로 구분
git cherry-pick <commit-hash1> <commit-hash2>

# 시작 포함 범위 지정 : ^..
git cherry-pick <start-commit-hash>^..<end-commit-hash>

# 시작부터 끝까지 범위 지정 : ^..HEAD
git cherry-pick <start-commit-hash>^..HEAD
```

<br>

#### 🔸 rebase와의 비교
- 이름에서부터 알 수 있다시피, 두 명령어는 목적이 다르다.
- cherry-pick은 '커밋'에, rebase는 '두 브랜치'에 집중한다.
- cherry-pick은 특정 커밋을 현재 브랜치에 적용하기 위해 사용한다.
- rebase는 다른 브랜치의 변경 사항을 현 브랜치에 순차적으로 적용하기 위해 사용한다.
- 하지만 두 명령어의 옵션을 아래와 같이 지정한다면, 동일하게 동작할 수 있다.
  - cherry-pick으로 선택적으로 커밋을 가져오는 것은 `rebase -i`와 동일하게 동작한다.
  - cherry-pick으로 범위를 지정해서 커밋을 가져오는 것은 `rebase --onto`와 동일하게 동작한다.
