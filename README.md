# Today I Learned

> 매일매일 배운 것을 기록합니다.

## 2022-09-13

### RPA 1기 - 웹프로그래밍 기획과 기본

#### 리눅스 커맨드라인 기초

`pwd`, `cd`, `ls`

- `pwd` : Print Working Directory의 약자로 현재 작업 경로를 출력해주는 명령어
- `cd` : Change Directory의 약자로 작업 경로를 변경할 때 쓰는 명령어
  - 절대경로는 `/`로 시작.
  - 상위경로는 `..`으로 나타냄
  - `tab`을 사용하는 자동완성 기능이 존재.
- `ls` : list의 약자로 현재 작업 경로에 있는 파일이나 디렉토리를 출력해주는 명령어
  - `ls -a`, `ls -l`, `ls -al`과 같은 옵션을 붙일 수 있음.
- `history` : 과거에 쳤던 명령어들을 보여줌. 복습할 때 용이하다. 명령어 복구도 가능.
  - 123번째 명령어를 복구하고 싶으면 !123

#### vim 사용법

- vim으로 파일 만들기/파일 편집하기
  - `vim 파일명.확장자명`
- 명령 모드와 입력 모드
  - vim 에디터를 열 때는 명령 모드로 진입함
  - 명령 모드에서는 입력이 불가능.
  - 입력을 하기 위해서는 입력 모드로 전환 필요.
    - 키보드에서 `i` 키 입력시 전환
  - 입력이 끝나고 저장하려면 명령 모드로 전환 필요.
    - 키보드에서 `esc`키 입력시 전환
  - 입력 가능한 명령어
    - `:w` : 저장하기
    - `:q` : 나오기
    - `:wq` : 저장하고 나오기
  - 참고자료 [링크](https://zeddios.tistory.com/122)
  - 비정상적으로 종료시 해결 방법
    - vim이 비정상 종료 되었을 때 swp 파일이 생성됨.
      -ATTENTION 문구가 뜨는 경우
      1.  두 프로세스, 두 사람이 동시에 한 파일을 수정하는 경우
      2.  crash가 나서 vim이 비정상적으로 닫힌 경우
    - 기존에 입력했던 내용을 복구하고 싶을 때는 `vim -r 파일명`을 입력하거나 Recovery모드로 진입
    - 정상 종료후, swp 파일 삭제
    - `rm .파일명.파일형식.swp`

#### 마크다운 문법

- 외부 링크 추가

```
사용문법: [Title](link)
적용예: [Google](https://google.com, "google link")
```

Link: [Google](https://google.com, "google link")

#### 버전 관리 시스템과 git

##### 버전 관리 시스템을 사용하는 이유

1. 실행 취소, 재 실행이 가능.
2. 버전간 소스코드 비교가 가능.
3. 협업이 쉬워짐.

##### 다양한 버전 관리 방법

이름 변경하기 등의 방법이 있는데, 개발할 때는 git을 주로 사용함

##### 커밋

- 커밋은 논리적 변경이 있을 때 만듬
- 가능하면 커밋 크기가 작을 수록 좋음

##### 커밋 이력 보기

```
git log
```

##### 리포지토리

- 정의 : 여러 파일을 하나로 모은 컬렉션
- 일반 디렉터리와 리포지토리의 차이 : `.git` 디렉터리 유무

#### 저장소 상태 파악하기

```
git status
```

### 220920 git bash code

- `code .` : 현재 위치를 작업폴더로 VS코드(또는 그 컴퓨터에 깔린 코딩 프로그램) 실행.
- `git init` : 현재 디렉터리를 리포지토리(저장소)로 변경. `.git` 파일 생성.
- `git status` : 현재 상태 표시. 변경사항이 있으면 붉은색으로 내용에 표시됨.
- `git log` : 최근 커밋 표시.
- `git add 파일명` : 해당 파일을 스테이징 영역으로 올림.
- `git commit` : commit.
  - `git commit -m "커밋코멘트"`: 코멘트와 함께 commit.
- `git checkout 커밋ID` : 해당 시점으로 이동.
- `git branch` : 현재 생성된 branch 확인.
  - `git branch branch명` : branch 생성.
  - `git checkout branch명` : 해당 branch로 이동.
- `git merge branch명` : 현재 branch에 branch명을 가진 brach를 병합함.
- `git push 저장소명 브랜치명` : 로컬 브랜치(브랜치명)를 원격저장소(저장소명)로 푸시한다.
- `git pull 저장소명 브랜치명` : 로컬저장소에 원격저장소의 브랜치를 가져온다.

## 2022-09-20

#### 브랜치

- 정의 : A branch in Git is simply a lightweight movable pointer to one of these commits.
- 브랜치는 특정한 목표를 가지고 하나의 코드를 수정할 때 주로 만듬
  - 이슈 하나당 브랜치 하나를 주로 만듬

##### 명령어

1. 브랜치 목록 보기
   ```
   git branch
   ```
2. 브랜치 생성하기
   ```
   git branch 생성하고자하는 브랜치 이름
   ```
3. 특정 브랜치로 전환하기
   ```
   git checkout 특정 브랜치 이름
   ```
   or
   ```
   git switch 특정 브랜치 이름
   ```
4. 브랜치 생성과 동시에 전환하기
   ```
   git checkout -b 브랜치이름
   ```

## 2022-09-27

#### branch를 merge하는 도중 충돌 해결

- 각 branch를 merge하다 보면 충돌이 생길 수 있다.
- 이 경우는 수동으로 merge하는 파일을 수정해야 한다.
- vim을 이용한 merge 충돌 실험
  1.  `git init`으로 저장소를 지정(main)
  2.  `vim test.txt`로 테스트 파일 생성
  3.  `git add text.txt` , `git commit -m "커밋 메시지"`로 커밋 생성
  4.  `git branch`로 잘 생성되었는지 확인
  5.  `git branch feature-A`로 새 branch 생성
  6.  `git checkout feature-A`로 branch 전환
  7.  `vim test.txt`로 테스트 파일 내용 변경
  8.  3,4번 항목 반복
  9.  `git checkout main`으로 main branch로 돌아옴
  10. `git branch feature-B`로 새 branch 생성
  11. `git checkout feature-B`로 branch 전환
  12. `vim test.txt`로 테스트 파일 내용을 변경하되 feature-A와 동일한 부분을 다르게 변경.
  13. 3,4번 항목 반복
  14. 현재 feature-B 에 checkout 되어 있는 상태에서 `git merge feature-A`로 merge
  15. 충돌이 일어났다는 메시지가 뜬 걸 확인하고 `vim test.txt`로 충돌 부분을 확인
  16. 충돌부분을 수정한 후 3번 항목을 반복

### GitHub를 이용한 브랜치 병합

1. 클론 만들기, 혹은 이미 클론이 있다면 원격 저장소 받아오기

```
git clone 깃허브페이지
git pull origin main
```

2. 이슈 발생
3. 이슈에 관한 브랜치 생성

```
git branch BranchName
```

4. 해당 브랜치로 체크아웃 후 이슈 해결

```
git checkout BranchName
```

5. 해당 브랜치를 GitHub에 업로드

```
git push origin BranchName
```

6. git hub에서 pull request로 브랜치 병합, _이때 병합되는 화살표를 잘 확인해야함_
7. 메인 브랜치로 체크아웃

```
git checkout main
```

8. 메인 브랜치에 원격저장소 받아오기

```
git pull origin main
```

## 2022-10-04

### 브랜칭 전략

- git branch를 효과적으로 나누고 관리하기 위한 전략

1. `git-flow` : 브랜치를 크게 4가지로 나누어 개발하는 전략

- 메인 브랜치(Main branch)
  - Main과 develop, 두 종류의 브랜치를 보통 메인 브랜치로 사용한다.
  - Main : 배포 가능한 상태만을 관리하는 브랜치
  - develop : 다음에 배포할 것을 개발하는 브랜치. develop 브랜치는 통합 브랜치의 역할을 하며 평소에는 이 브랜치를 기반으로 개발을 진행한다.
- 보조 브랜치(Supporting branch)
  - 피처 브랜치(frature branch) 또는 토픽 브랜치(topic branch)로 불린다.
  - 기능을 개발하는 브랜치로 develop 브랜치로부터 분기되고 기능을 다 완성할 때까지 유지하다가 완성되면 develop 브랜치로 병합한다.
  - 보통 개발자 저장소에만 있는 브랜치이며 origin에는 push하지 않는다.
- 릴리스 브랜치(Release branch)
  - develop 브랜치에 이번 버전에 포함되는 기능이 병합되었다면 QA를 위해 develop 브랜치에서부터 release 브랜치를 생성하고 배포를 위한 최종적인 버그 수정 등의 개발을 수행한다.
  - 배포 가능한 상태가 되면 main 브랜치로 병합시키고 출시된 main 브랜치에 버전 태그를 추가한다.
  - release 브랜치에서의 버그 수정 사항은 develop 브랜치에서도 적용해주어야 한다.
- 핫 픽스 브랜치(Hotfix branch)
  - 배포한 버전에서 긴급하게 수정을 해야 할 필요가 있을 경우 main 브랜치에서 분기하는 브랜치
  - hotfix 브랜치에서의 변경사항은 develop 브랜치에도 병합하여 문제가 되는 부분을 처리해주어야 한다.

2.
