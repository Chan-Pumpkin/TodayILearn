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

Tip!   
scope : 속성을 공유할 수 있는 유효범위      
scope 종류 : Session, Request, Application, Page      

```jsx
<c:set var="변수 이름" value="변수값" [scope="scope 속성 중 하나"]
```

- <c:remove>   
JSP 페이지에서 변수를 선언했으면, <c:remove>태그를 이용해서 변수를 제거할 수도 있다.  

Tip!   
var : 제거할 변수 이름   
scope : 변수 범위 지정   
```jsx
<c:remove var="변수이름" [scope="scope 속성 중 하나"] />
```

#2 흐름 제어
- <c:if>   
JSP 페이지에서 조건문을 대체해 사용하는 태그      
```jsx
<c:if test="${조건식}" var="변수이름" [scope="scope 속성 중 하나"]/>
</c:if>
```

- <c:choose>    
JSP 페이지에서 switch문의 기능을 수행한다.
```jsx
<c:choose>
	<c:when test="조건식1"> 내용1 </c:when>
	<c:when test="조건식2"> 내용2 </c:when>
	..
	<c:otherwise> 내용N </c:otherwise>
</c:choose>
```

첫 번째 <c:when> 태그의 조건식1을 체크해서 참이면 '내용1'을 수행한다.   
조건식 1이 거짓이면, 다음 조건식2를 체크해서 참이면 '내용2'를 수행한다.   
모든 조건식이 거짓이면 '내용N'을 수행한다   
   
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
