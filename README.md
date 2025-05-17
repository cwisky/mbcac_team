# mbcac_team
## Windows에서 자격증명 확인 / github관련 자격증명 삭제

## github.com 회원가입

## github 사이트에서 Repository 생성
* Repository 주소 복사
* 
## git 다운로드/설치
* user.name / user.email 등록
  + git config --global user.name="개인아이디"
  + git config --global user.email="개인이메일주소"
* git config --list : 등록된 항목 확인
* 
## github 토큰 신청/발급
* github.com 화면 우측 상단 아이콘 클릭 > Settings > 왼쪽 메뉴 하단 Developer settings > Personal access tokens >
* Tokens(classic) > Generate new token > Generate new token(classic) >
* Note:간단 설명 입력 > Generate token

## 로컬 Repository에 원격 리파지토리 복사
* 원격 저장소에 등록된 프로젝트를 최초로 로컬 저장소에 복제한다
* git init
* git clone [원격 저장소 주소]
* git config --list  <-- origin 이라는 이름으로 원격 저장소의 주소가 등록된 것을 확인

## 로컬 저장소의 내용변경 및 원격 저장소에 병합(push)하기
* 로컬 저장소에 있는 파일을 변경하고 저장한다
* git add . : 현재 디렉토리(프로젝트 루트)에서 staging 작업 실행(업로드할 파일을 모은다)
* git status : 현재 상태 확인
* git commit -m "변경 내역에 기록할 메시지"
* git status
* git push -u origin main : origin은 원격 저장소의 주소에 대한 별칭으로 로컬에 설정된 상태임, main:원격 저장소 브랜치 이름
* 위의 명령은 -u(--set-upstream) 설정, 인증을 위한 웹브라우저가 실행됨
* 웹브라우저 하단의 초록버튼을 누르고 화면이 전환되면 브라우저를 닫는다
* git 명령을 실행하던 콘솔창을 닫고 다시 실행한다
* git status 명령으로 git의 현재 작업 상태 확인
* 파일의 변경 상태가 표시되지 않으면 대상 파일을 열고 다시 변경하고 저장한다
* git add . : 변경된 로컬 저장소의 내용을 staging
* git status : 변경된 파일이 git에 의해 표시되는지 확인
* git commit -m "변경내역에 기록할 메시지"
* git status : 위에서 commit 한 정보가 확인되는지
* git push origin main : 최종적으로 로컬 프로젝트를 원격 저장소(origin)의 main 브랜치에 병합한다
* github.com에 접속하여 해당 파일의 내용이 변경되어 있는지 확인한다

## Github Actions 테스트
* Github Actions는 Github의 리파지토리에 올려진 프로젝트가 변경시 자동으로 해당 리파지토리의 .github/workflow/*.yml 파일에 정의된 작업이 자동으로 실행된다
* 리파지토리의 .github/workflow/*.yml은 표준으로 따라야 하며 *.yml 안에 정의된 빌드, 테트, 배포 작업이 수행되는 것이다
* 현재 리파지토리 루트에 .github 디렉토리 생성 > .github안에 workflow 디렉토리 생성 > workflow 안에 sample.yml 생성
* sample.yml 에 아래의 내용 입력(빈 라인은 무의미, 들여쓰기 문법, "키:값" 형식이 아니어도 됨, "-" 는 리스트 아이템, 아이템 한개는 다수개 속성도 가능)
  + 키:값은 한줄로 가능하며 줄바꿈할 때는 들여쓰기함. 단일 값은 한줄로 쓰는 것이 가장 안전함
```yml
name: Test GitHub Actions

on:
  push:           # 어떤 브랜치든 push 되면 실행
    branches:
      - "**"

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: 코드 체크아웃
        uses: actions/checkout@v3

      - name: 확인 메시지 출력
        run: echo "🎉 GitHub Actions가 잘 작동하고 있습니다!"
```
* 이 파일을 수정하면 이 리파지토리에 설정된 workflow가 시작되고 로그에 기록되는지 확인
* Actions > 표시된 workflow 중 최근 실행된 workflow 클릭 > 해당 yml 아래의 Job 클릭 > "확인 메시지 출력" > yml에서 echo 명령으로 출력한 메시지 확인

## Github Actions에서 사용되는 yml 작성법

