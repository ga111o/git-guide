### basic command

`git init`

`git add <filename>`

- commit

  - `git commit -m "<text>"`
  - `git commit -a -m "모든 변경 사항을 커밋"`
  - `git commit -p` <br>선택적으로 변경 사항을 스테이징. 특정 변경 사항만 선택해서 커밋
  - `git commit --amend -m "수정된 커밋 메시지"`<br>마지막 커밋을 수정. 이전 커밋 메시지 변경 or 추가 변경 사항 포함 가능
  - `git commit -v` <br>스테이징된 변경 사항을 보여줌.

- unstaging

  - `git restore --staged <file>`

- branch

  - `git branch`<br>브랜치 목록
  - `git branch <branch name>`<br>브랜치 생성
  - `git branch -d <branch name>`<br> 브랜치 삭제
  - `git branch -m <branch name>`<br> 현재 브랜치 이름 변경
  - `git checkout <branch name>`<br> 브랜치 전환
  - `git switch <branch name>`<br> 단순화된 버전의 git checkout

- reset

  - `git reset --soft HEAD~1`<br>가장 최근 commit 취소
  - `git reset --soft HEAD~3`<br>최근부터 3개 commit 취소
    > --soft: 변경 내역은 staging에 남김.

- `git revert <commit hash>`<br>해당 변경 내역 revert

- pull request

  - `git remote add upstream <original repo url>`

    - 일반적으로 origin은 내 원격 저장소 주소, upstream을 원본 원격 저장소 주소로 설정.

  - `git fetch upstream`<br> 원본 repo에서 변경 사항을 가져옴

  - `git checkout <로컬 브랜치명>`<br>`git merge upstream/<원하는 브랜치명>`<br>upstream에서 가져온 변경 사항을 로컬 브랜치에 병합

  - `git push origin <로컬 브랜치명>`<br>`git push upstream <로컬 브랜치명>`

---


- `origin/main`: 로컬에 저장된 깃헙 main브랜치
- `main`: 로컬에 저장된 main 브랜치

	`git pull origin/main main`

	`git push origin/main main`

---

"origin의 test브랜치에, 로컬 develop 브랜치 push"

	1. `git switch develop`

	2. 커밋

	3. `git push origin develop:test`
