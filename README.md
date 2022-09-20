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
