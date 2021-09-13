# SVN 서버 설치

1) 아래 홈페이지 주소로 들어갑니다.
<https://www.visualsvn.com/server/download/>

2) 자신의 버전에 맞는 비트로 다운로드를 받습니다.
3) 다운로드 받은 파일로 설치를 진행합니다.
4) 설치한 후, Users(유저)를 생성합니다.
- Users를 오른쪽 마우스를 클릭하여 Create User를 선택 
- User name과 password 지정 후 OK   

5) Repositories(저장소) 추가
- 'Repositories' 오른쪽 마우스 클릭 후, 'Create New Repository...' 선택
- 'Regular FSFS repository' 선택
- Repository name 지정
- 'Empty repository' 선택
- 'All Subversion user have Read / Write Access' 선택 후 Create 선택 
- Finish 버튼

6) 리포지토리 권한 변경 
- 생성한 리포지토리 오른쪽 클릭해서 Properies 선택
- Everyone 삭제 후, 생성한 User 추가

7) 다른 PC에서 리포지토리 사용
- 다른 PC에서 리포지토리 URL을 입력하고, 생성한 USER로 로그인해서 사용하면 됩니다.
