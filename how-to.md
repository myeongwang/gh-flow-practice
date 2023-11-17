# git 사용법을 알아봅시다.

## repo clone하기

- github에서 repo를 생성한다.
- repo url을 복사한다.
- `$ git clone repo-url` 하여 로컬에 복제한다.

## add, commit, push

- 새 파일을 생성한다 or 이미 존재하는 파일에 작업을 실시한다.
- `$ git status` 로 현재 상황을 파악한다.
- `$ git add filename`으로 대상 파일을 staging한다.
- `$ git commit` 으로 메타데이터를 작성한다.(`$ git commit -m "message"`도 사용가능)
- `$ git push origin main`으로 원격저장소(github)에 push 한다.

## branch

- `$ git branch branchname`으로 새 브랜치를 생성한다.
- `$ git switch branchname`으로 새 브랜치로 이동한다.
- 작업하여 add, commit을 실시한다.
- 작업이 끝나면, `$ git switch main` 으로 기본 브랜치로 돌아온다.
- `$ git merge branchname`으로 새 브랜치의 작업사항을 기본 브랜치로 합친다.
- 만약, merge conflict가 발생한다면, 해당 상황을 해결한 뒤 add, commit(-m 사용 금지) 하여 merge를 완료한다.

## github flow

- `$ git branch branchname`으로 새 브랜치를 생성 후 `$ git switch branchname` 으로 이동한다.
- github 에서 issue를 작성한 뒤, 작성한 작업의 순서에 따라 작업을 실시한다.
- 최종적으로 모든 작업을 commit 한 뒤, 해당 브랜치 위에서 `$ git push -u origin branchname` 하여 github에 전달한다.
- github 에서 pull request를 open 하여 code review 등 필요한 일을 수행하고, 이상없을 경우 merge 한다.
- github 에서 merge 된 branchname 브랜치를 삭제한다.
- local에서 `$ git fetch origin main`, `$ git merge FETCH_HEAD`를 하여, github의 업데이트된 내용을 pull 한다.
- 다음 작업 시작 의 반복
