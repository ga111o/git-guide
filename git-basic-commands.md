### basic command

`git init`

`git add <filename>`

- commit

  - ctrl + s 처럼 막 하는 것 보다는, 기능 하나 완성될 때마다 하는 걸 추

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

  - 커밋 자체에 문제가 있을 때, 해당 커밋사항을 기반으로 작성한 모든 파일들에 문제가 생길 수 있음.
  - 해당 commit id로 회귀
  - `git reset --soft HEAD~1`<br>가장 최근 commit 취소
  - `git reset --soft HEAD~3`<br>최근부터 3개 commit 취소
    > --soft: 변경 내역은 staging에 남김.

- restore

  - `git restore 파일명`: 최근 commit된 상태로 현재 파일의 수정 내역을 -
  - `git restore --source 커밋id 파일명`: 해당 commit id로 파일을 되돌림
  - `git restore --staged <file name>`

- revert

  -
  - `git revert <commit id>`

- log

  - github에서 history 보는 것과 비슷함

  - `git log --all --oneline`
  - `git log --all --oneline --graph`

- diff

  - `git diff`
  - `git diff {commit id}`
  - `git diff {commit id}, {commit id}`

  - `git difftool`: vim에서 gui처럼 보여줌, 그 외 옵션은 diff와 동일

- merge

  - 3-way merge: 가장 일반적임, 새로운 커밋을 만들어서, 거기에 두 브랜치를 합침.
  - fast-forward merge: 새 브랜치에만 commit이 있고, 기준 브랜치에 신규 commit이 없을 경우, 기존 branch에 자동으로 통합 <br>`git merge --no-ff 브랜치명` 하면 강제로 3-way merge 시켜줌

  - rebase: 3-way merge 말고 강제로 fast-forward를 하고 싶을 때, 즉, 커밋 내역을 브랜치 하나로만 남기고 싶을 때.

    1. `git switch 브랜치명`
    2. `git rebase main`
    3. `git switch main`
    4. `git merge 브랜치명`

  - squash and merge: rebase의 업그레이드 버전?이라고 이해하면 좋을듯, rebase 할 브랜치의 모든 commit을 하나의 commit으로 만들고 rebase<br>`git merge --squash 브랜치명`

- conflict 해결

  - cli면 원하는 코드만 남기고, `<<<<`, `>>>>`, `====` 지움. -> git add -> git commit
  - vscode면 상단 accept 어쩌구 버튼 누르고 git add -> git commit

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
