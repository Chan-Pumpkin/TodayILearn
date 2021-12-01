# FormattingTag(포매팅 태그)
포매팅 라이브러리를 사용하면 쉽게 원하는 형태로 숫자, 날짜, 문자열을 표시할 수 있다.

## taglib
```jsx
<%@ taglib prefix="fmt" uri=" http://java.sun.com/jsp/jstl/fmt ">
```   
    
## Formatting Tag library   
1. ```<fmt:timeZone>```   
지정한 국가의 시간을 지정하는 태그     
태그를 열고 닫는 영역 안에서만 적용된다.   

2. ```<fmt:setTimeZone>```    
지정한 국가의 시간을 지정하는 태그  
    
3. ```<fmt:formatNumber>```    
표시할 숫자의 형식을 지정

4. ```<fmt:formatDate>```    
지정한 형식의 날짜를 표시
    
## FormatNumber 태그 속성     
value : 출력될 숫자를 지정    
    
type : 출력된 타입 지정 (percent인 경우 %, number인 경우 숫자, currency인 경우 통화 형식으로 출력      
    
dateStyle : 날짜의 출력 형식 지정      
     
groupingUsed : 콤마등 기호로 구분 여부 지정     
     
currencyCode : 통화 코드를 지정 (한국 원화는 KRW)     
     
currentSimbol : 통화를 표시할 때 사용할 기호를 표시      
     
var : <formatNumber> 태그 결과를 저장할 변수의 이름을 저장      
          
scope : 변수의 접근 범위 지정       
      
pattern : 숫자가 출력될 양식 지정. 자바의 DecimalFormat 클래스에 정의된 형식을 따름.     
     
## FormatDate 태그 속성     
value : 포맷될 날짜를 지정    
    
type : 포매팅할 타입을 지정          
    
dateStyle : 날짜의 출력 형식 지정      
     
timeStyle : 시간 출력 형식을 지정     
     
pattern : 직접 출력 형식을 지정     
- 예시    
registerDate 파라미터에 년-월-일-시-분 의 값이 들어있는 경우, pattern 속성으로 년-월-일 형태로 지정할 수 있다.
```
<fmt:formatDate value="#{registerDate}" pattern="YYYY-MM-DD"/>
```
```
실행 결과 : 2021-12-02
```
      
timeZone : 특정 나라 시간대로 시간을 지정      
       
