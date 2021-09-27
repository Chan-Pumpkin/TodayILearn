# JSTL개념

### JSTL이란?
JSP 개발을 단순화하기위한 태그 library로서,  Java EE 기반의 웹 애플리케이션 개발 플랫폼을 위한 컴포넌트 모음이다.   
JSTL의 정식 명칭은 자바서버 페이지 표준 태그 라이브러리(JavaServer Pages Standard Tag Library)이고 줄여서 JSTL이라 부른다.   
   
JSTL은 JSP 페이지 내에서 자바 코드를 바로 사용하지 않고 로직을 내장하는 효율적인 방법을 제공한다.    
표준화된 태그 셋을 사용하여 자바 코드가 들락거리는 것보다 더 코드의 유지보수와 응용 소프트웨어 코드와 사용자 인터페이스 간의 관심사의 분리로 이어지게 한다.   

### JSTL의 장점
1) JSP를 단순화하여 사용할 수 있어서 빠른 개발에 도움을 준다.
3) 코드의 재사용성이 좋다.


### JSTL 종류
1) Core  (prefix : c)   
- 실행 흐름의 제어 기능을 제공   

2) Formatting (prefix : fmt)
- 숫자, 날짜, 시간을 포매팅하는 기능을 제공
- 국제화, 다국어 지원 기능 제공   

3) DataBase (prefix : sql)
- DB의 데이터를 입력 / 수정 / 삭제 / 조회 하는 기능을 제공

4) XML (prefix : x)
- XML문서를 처리할 때 필요한 기능 제공

5) Function (prefix : fn)
- 문자열을 제공하는 함수 제공
