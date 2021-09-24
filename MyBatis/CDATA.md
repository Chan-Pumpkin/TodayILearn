# CDATA

Mybatis 사용시 쿼리문에 문자열 비교연산자 혹은 부등호를 처리할 때가 있다.
하지만 '<','>','&' 과 같은 기호는 태그로 인식하는 경우가 종종 있는 문제가 발생을 한다.   
아래와 같은 상황에는 그럼 어떻게 해야할까..    

```xml
<select id="getUserList" resultMap="UserVO">
select *
from employees
where salary > 100
</select> 

```

이럴 때, 사용하는 것이 아래와 같은 CDATA이다.    
CDATA는 <,>,&,|| 등을 =문자열로 처리하라는 뜻으로 XML parser를 하지 않도록 하는 것이다.   
CDATA안에 들어가는 문장을 문자열로 인식하여 특수문자가 들어가도 문자열로 인식을 한다.

```xml
<![CDATA[
쿼리 내용
]]>
```

아래와 같은 예시로 사용하면 된다.   

```xml
<select id="getUserList" resultMap="UserVO">

<![CDATA[
select *
from employees
where salary > 100
]]>

</select> 

```
