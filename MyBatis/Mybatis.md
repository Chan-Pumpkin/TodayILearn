# Mybatis 개념

### 1 Mybatis란?

자바 오브젝트와 SQL사이의 자동 매핑 기능을 지원하는 ORM(Object relational Mapping)프레임워크이다. 
- SQL을 별도의 파일로 분리해서 관리하게 해준다.
- Hibernate나 JAP(Java Persistence Api)처럼 새로운 DB프로그래밍 패러다임을 익혀야하는 부담 없이 SQL을 그대로 이용하면서 JDBC코드 작성의 불편함도 제거해주고 도메인 객체나 VO객체를 중심으로 개발이 가능하다는 장점이 있다.

### 2 Mybatis의 특징

1)쉬운 접근성과 코드의 간결함
- JDBC의 모든 기능을 Mybatis가 대부분 제공한다.
- 복잡한 JDBC코드를 걷어내며 깔끔한 소스코드를 유지할 수 있다.
- 수동적인 파라미터 설정과 쿼리 결과에 대한 맵핑 구문을 제거할 수 있다.

2)SQL문과 프로그래밍 코드의 분리
SQL에 변경이 있을 때마다 자바 코드를 수정하거나 컴파일하지 않아도 된다.

3)다양한 프로그래밍 언어로 구현 가능
JAVA, C#, .NET 등등

### 3 Mybatis와 Mybatis-Spring을 사용한 DB 액세스 아키텍처
<img src="https://user-images.githubusercontent.com/62877858/134814767-20b7ba32-39c9-410a-8d82-8f69b6ad443d.GIF"/>


### 4 Mybatis 를 사용하는 데이터 액세스 계층 흐름도
<img src="https://user-images.githubusercontent.com/62877858/134814885-5ba9a323-0c4a-4764-aa78-7fc6ed5f33eb.GIF"/>

참고 :
https://shlee0882.tistory.com/205
https://velog.io/@changyeonyoo/Mybatis%EB%9E%80-%EC%9E%A5%EC%A0%90-%ED%8A%B9%EC%A7%95-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8
