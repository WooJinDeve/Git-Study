## Git 이란?
- 파일버전을 기록해주는 프로그램.

## Git 설치
- **Download URL**
  - [https://git-scm.com/downloads](https://git-scm.com/downloads)

## Git init, add, commit
![image](https://user-images.githubusercontent.com/106054507/187034246-26ca6ae2-934e-4d55-85a6-1e6b6ee6c238.png)
- **$ git init**
    - `$ git init`는 새로운 `Git 저장소(repository)`를 생성할 때 사용하는 Git 명령어.
- **$ git add {filename}**
    - `Working Drectory` → `Statig Area` 로 이동
- **$ git commit -m “{message}“**
    - `Staging Area` → `저장소(Repository`로 저장
- **$ git status**
    - `Staging Area` 를 확인
- **$ git log —oneline**
    - `commit`된 내용을 확인
    - `$ git log --onelie --all --graph` : `branch` 의 `commit` 확인.
- **$ git diff**
    - 최근 `commit` 과 현재 파일의 변경점을 알 수 있음.
    - `$ git difftool`
        - 변경점을 에디터로 확인
        - `$ git difftol {logID}` : `commit` 한 내용을 비교.
    

## Branch

- **$ git branch {Branch Name}**
    - `commit` 복사본 생성
    - `$ git branch -d {branch name}` : 브랜치 삭제
    - `$ git branch -M {branch name}` : 메인 브렌치 설정
- **$ git switch {Branch Name}**
    - `branch`로 이동
- **$ git merge {Branch Name}**
    - `branch` 합치기
    - `$ git merge — squash {branch name}`

## 복구(Restore)

- **$ git restore {filename}**
    - `$ git restore {filename}` : 최근 `commit` 시점으로 복구
    - `$ git restore —source {commit id}` : 특정 `commit` 시점으로 복구
    - `$ git restore --staged {filename}` : 특정 파일 `staging` 취소
- **$ git revert {commit id}**
    - 특정 `commit` 취소
    - `$ git revert HEAD` : 최근 `commit`취소
- **$ git reset -hard {commit id}**
    - `commit`이 생성된 시점으로 되돌림.
    - `$ git reset --soft {commit id}` : 변동사항을 지우지 말고 `Staging` 처리.
    - `$ git reset --mixed {commit id}` : 변동사항을 지우지 말고 `unstaging` 처리.

## GitHub

- `깃허브(Github)`는 `Git`을 지원하는 웹 호스팅 서비스 시스템

- **$ git push -u {repository url} {branch name}**
    - `원격 저장소(GitHub Repository)`에 `branch` 에 `commit` 내역이 저장
    - `$git remote add {변수명} {repository url}` : `repository url` → `변수`
    - `-u` : 원격 저장소 주소 기억 명령어.
- **$ git clone {repository url}**
    - 원격 저장소에 저장된 소스코드 다운
- **$ git pull {repository url}**
    - 원격저장소 → 로컬 저장소
- **pull request**
    - **`pull request` → `base : branch← compare : branch` → `Create pull request` → `merge`**
    

## GitFlow

![image](https://user-images.githubusercontent.com/106054507/187034231-acb037a1-04e9-416e-bbd5-d81356954f41.png)
- **main**
    - `master` 브랜치는 최종적으로 배포되는 가장 중심의 브랜치이다
- **develop**
    - 개발을 진행하는 브랜치로 중심적인 브랜치
- **feature**
    - **`feature`** 브랜치는 기능의 구현을 담당
    - `feature/{구현기능명}`과 같은 명칭을 준수하는 것이 일반적
- **release**
    - `release` 브랜치는 개발된 내용을 배포하기 위해 준비하는 브랜치
- **hotfix**
    - `hotfix` 브랜치는 배포된 소스에서 버그가 발생하면 생성되는 브랜치
