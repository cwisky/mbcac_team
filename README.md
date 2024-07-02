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
