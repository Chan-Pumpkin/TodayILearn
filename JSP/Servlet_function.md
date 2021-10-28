# 서블릿 기본 기능

## 서블릿 기능 수행 과정
1) 클라이언트로부터 요청 받는다.
2) 데이터베이스 연동고 같은 비즈니스 로직을 처리한다.
3) 처리된 결과를 클라이언트에 돌려준다.

## 서블릿 응답과 요청 수행 API 기능
javax.servlet.http 패키지- 요청이나 응답과 관련된 API가 모두 있음.     
javax.servlet.http.HttpServletRequest 클래스 - 요청과 관련된 API     
javax.servlet.http.HttpServletResponse 클래스 - 응답과 관련된 API     
