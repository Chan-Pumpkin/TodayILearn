# form 태그 활용해서 서블릿 요청

## form 태그 속성
name :      
- form태그의 이름을 지정
- 여러 개의 form이 존재할 경우 구분하는 역할
- 자바스크립트에서 form 태그에 접근할 때 자주 사용

method :      
- form 태그 안에서 데이터를 전송할 때 전송 방법을 지정
- GET또는 POST로 지정 (Default : GET)

action :        
- form 태그에서 데이터를 전송할 서블릿이나 JSP를 지정
- 서블릿으로 전송할 때는 매핑 이름을 사용

encType :        
- form 태그에서 전송할 데이터의 encoding 타입을 지정
- 파일 업로드할 때는 multipart/form-data로 지정
