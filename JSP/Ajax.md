# Ajax

## Ajax
Asynchronous Javascript(비동기 자바스크립트) + XML의 줄임말.     
자바스크립트를 사용해서 XML, JSON 데이터를 클라이언트와 서버간에 주고받는 비동기 통신 기술     
         
Ajax는 페이지 이동 없이 데이터 처리가 가능하다는 큰 특징이 있다.    
서버의 처리를 기다리지 않고 비동기 요청이 가능하다는 것인데     

페이지에서 데이터 처리로 다음 페이지로 넘어가는 것이 아닌, 페이지에서 다음 페이지 이동 없이 데이터 처리가 가능하다.     
     
## Ajax 사용법

```jsx
$.ajax({
type : "post 또는 get",
async : "true 또는 false",
url : "요청할 URL",
data : {서버로 전송할 데이터},
dataType : "서버에서 전송받을 데이터형식",
success : {
					//정상 요청, 응답 시 처리
},
error : function(xhr,status,error){
				//오류 발생 시 처리
},
complete : function(data, textStatus){
					//작업 완료 후 처리
}
});
```

## Ajax 속성
- type : 통신 타입 설정 (post or get)
- url : 요청할 url을 설정
- async : 비동기식으로 처리할지 여부 설정 (false=동기/true=비동기)
- data : 서버에 요청할 때 보낼 매개변수 설정
- dataType : dataType 응답 받을 데이터 타입 설정(XML, TEXT, HTML, JSON)
- success : 요청 및 응답에 성공했을 때 처리 구문 설정
- error : 요청 및 응답에 실패했을 때 처리 구문 설정
- complete : 모든 작업 마친 후 처리 구문 설정
