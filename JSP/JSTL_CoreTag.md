# CoreTag (c 태그)

jsp에서는 변수 선언, 조건식, 반복문 기능은 자바 코드를 이용해서 구현하지만, 코어 라이브러리를 사용하면 이런 자바 기능을 태그로 대체할 수 있다.   

## taglib

자바의 import문처럼 Core Tag 라이브러리를 사용하기 위해 반드시 JSP 페이지 상단에 다음과 같이 taglib 디렉티브 태그를 추가해서 톰캣에게 알려주어야 한다. 만약 선언을 하지 않으면 오류가 발생한다.

```jsx
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

## Core 태그 라이브러리 기능별 종류 정리

#1 변수 지원    
- 1-1) <c:set>   
JSP 페이지에서 변수를 지정한다.      

```jsx
<c:set var="변수 이름" value="변수값" [scope="scope 속성 중 하나"]
```
   
   Tip!   
scope : 속성을 공유할 수 있는 유효범위      
scope 종류 : Session, Request, Application, Page      


- 1-2) <c:remove>   
JSP 페이지에서 변수를 선언했으면, <c:remove>태그를 이용해서 변수를 제거할 수도 있다.  

Tip!   
var : 제거할 변수 이름   
scope : 변수 범위 지정   
```jsx
<c:remove var="변수이름" [scope="scope 속성 중 하나"] />
```

#2 흐름 제어      
- 2-1) <c:if>      
JSP 페이지에서 조건문을 대체해 사용하는 태그      
```jsx
<c:if test="${조건식}" var="변수이름" [scope="scope 속성 중 하나"]/>
</c:if>
```

- 2-2) <c:choose>    
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
   
- 2-3) <c:forEach>     
JSP 페이지에서 반복문을 수행하는 태그
```jsx
<c:forEach var="변수이름" item="반복할객체이름" begin="시작값" end="마지막값"
						step="증가값" varStatus="반복상태변수이름">
...
</c:forEach>
```
Tip!   
var : 반복할 변수 이름   
items : 반복할 객체 이름 지정   
begin : 반복 시작 값   
end : 종료 값   
step : 한 번 반복할 때마다 반복 변수를 증가시킬 값   
varStatus : 반복 상태 속성 지정   
    
Tip! : varStatus 속성정리          
|속성|태그|설명|
|---|---|---|
|index|int|items에서 정의한 항목을 가리키는 index 번호로서, 0부터 시작|
|count|int|몇 번째 반복인지 나타냄. 1부터 시작|
|first|boolean|첫 번째 반복인지 나타냄|
|last|boolean|마지막 반복인지 나타냄|


     
- 2-4) <c:forTokens>      
구분자로 분리된 각각의 토큰을 처리할 때 사용한다.     
    
    
#3 URL 처리     
- 3-1) <c:import>     
URL을 이용해 다른 자원을 JSP 페이지에 추가한다.      
```jsx
<c:import url="URL" [var="변수 이름"] [scope="영역"] [charEncoding="인코딩"]>
</c:import>
```   
- 3-2) <c:redirect>     
respones.sendRedirect()을 대체하는 태그로 지정한 다른 페이지로 이동     
```jsx
 <c:redirect url="redirect할 URL" />
```
- 3-3) <c:url>  
<c:url> 태그는 JSP 페이지에서 URL 정보를 저장하는 역할   
```jsx
<c:url var="변수이름" values="URL경로" [scope="scope 속성 중 하나"]
[<c:param name="매개변수이름" value="전달값"/>] >
..
</c:url>
```
var : 생성된 URL이 저장될 변수   
value : 생성할 URL   
scope : scope 속성의 값 지정   
   

#4 기타 태그   
- 4-1) <c:catch>    
예외 처리에 사용한다.    
```jsx
<c:catch var=“변수이름”>
예외 발생할 수 있는 코드 작성
</c:catch>
```
    
- 4-2) <c:out>     
JspWriter에 내용을 처리한 후 출력한다.   
화면에 지정한 값을 출력해 주는 태그로서, 표현 언어와 기능은 거의 동일하지만, 기본값 설정 기능 등을 제공하므로 더 편리하게 사용함.   
```jsx
<c:out value="출력값" default="기본값" [escapeXml="boolean값"] />
```
