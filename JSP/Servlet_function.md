# 서블릿 기본 기능

## 서블릿 기능 수행 과정
1) 클라이언트로부터 요청 받는다.
2) 데이터베이스 연동고 같은 비즈니스 로직을 처리한다.
3) 처리된 결과를 클라이언트에 돌려준다.

## 서블릿 응답과 요청 수행 API 기능
javax.servlet.http 패키지- 요청이나 응답과 관련된 API가 모두 있음.     
javax.servlet.http.HttpServletRequest 클래스 - 요청과 관련된 API     
javax.servlet.http.HttpServletResponse 클래스 - 응답과 관련된 API     

## HttpServletRequest의 여러 가지 메서드
|반환형|메서드 이름|기능|
|---|---|-----|
|boolean|authenticate(HttpServletResponse response)| 현재 요청한 사용자가 ServletContext 객체에 대한 인증을 하기 위한 컨테이너 로그인 메커니즘을 사용함.|
|String|changeSessionId|현재 요청과 연관된 현재 세션의 id를 변경하여 새 세션 id를 반환|

## HttpServletResponse의 여러 가지 메서드
|반환형|메서드 이름|기능|
|---|---|-----|
|void|addCookie(Cookie cookie)|응답에 쿠키를 추가함.|
|void|addHeader(String name, String value)|name과 value를 헤더에 추가함.|
