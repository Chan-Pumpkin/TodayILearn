# CoreTag (c 태그)

jsp에서는 변수 선언, 조건식, 반복문 기능은 자바 코드를 이용해서 구현하지만, 코어 라이브러리를 사용하면 이런 자바 기능을 태그로 대체할 수 있다.   

### taglib
자바의 import문처럼 Core Tag 라이브러리를 사용하기 위해 반드시 JSP 페이지 상단에 다음과 같이 taglib 디렉티브 태그를 추가해서 톰캣에게 알려주어야 한다. 만약 선언을 하지 않으면 오류가 발생한다.

```jsx
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

### Core 태그 라이브러리 기능별 종류 정리

#1 변수 지원 
- <c:set>   
JSP 페이지에서 변수를 지정한다.

```jsx
<c:set var="변수 이름" value="변수값" [scope="scope 속성 중 하나"]
```

Tip!   
scope : 속성을 공유할 수 있는 유효범위   
scope 종류 : Session, Request, Application, Page   

- <c:remove>   
지정된 변수를 제거한다.

#2 흐름 제어
- <c:if>   
조건문을 사용한다.   

- <c:choose>    
switch문을 사용한다.

- <c:forEach>     
반복문을 사용한다    
     
- <c:forTokens>      
구분자로 분리된 각각의 토큰을 처리할 때 사용한다.     
    
    
#3 URL 처리     
- <c:import>     
URL을 이용해 다른 자원을 JSP 페이지에 추가한다.      

- <c:redirect>     
respones.sendRedirect() 기능을 수행한다.     

- <c:url>    
요청 매개변수로부터 URL을 생성한다.    

#4 기타 태그
- <c:catch>    
예외 처리에 사용한다.    

- <c:out>     
JspWriter에 내용을 처리한 후 출력한다.     
