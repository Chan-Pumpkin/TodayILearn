# WEB Server와 WAS(Web Application Server)Server 차이

## WEB Server

### WEB Server?
클라이언트가 웹 브라우저에서 어떠한 페이지 요청하면 웹 서버에서 그 요청을 받아 정적 컨텐츠를 제공하는 역할을 함.

### 정적 컨텐츠?
HTML, CSS, javascript, 이미지

### 기능
- 정적인 컨텐츠 제공
- WAS를 거치지 않고 바로 자원을 제공한다.
- 동적인 컨텐츠 제공을 위한 요청을 전달을 해서, 클라이언트의 요청을 WAS에 보내고, WAS가 처리한 결과를 클라이언트에게 전달함.


## WAS Server

### WAS Server?
- DB 조회나 다양한 로직 처리를 요구하는 동적인 컨텐츠를 제공한다.
- HTTP를 통해 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어이다.
- WAS는 JSP, Server 구동환경을 제공해주기 때문에 웹 컨테이너 혹은 서블릿 컨테이너라고 불림

### 기능
- 프로그램 실행 환경과 DB 접속 기능 제공
- 여러 개의 트랜잭션(논리적인 작업 단위) 관리 기능
- 업무를 처리하는 비즈니스 로직 수행

## WAS만 안쓰고, WEB서버와 WAS를 굳이 왜 따로 쓸까?
- 기능을 분리하여 서버 부하 방지
- 물리적으로 분리하여 보안 강화
- 여러개의 서버 운영이 가능함.

## 참고
https://gmlwjd9405.github.io/2018/10/27/webserver-vs-was.html      
https://codechasseur.tistory.com/25     
https://gaebaldiary.tistory.com/27     
