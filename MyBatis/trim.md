# trim
### trim   
동적 Query를 사용하기 위해 사용되는 문법으로 보통 if문의 역할을 대체한다.   
  
### trim 속성   
- prefix : 실행될 쿼리의 <trim> 문 안에 쿼리 가장 앞에 붙여준다.

```xml
<trim prefix="[문자열]"> 
쿼리문
</trim>
```
```xml
UPDATE tb_board 
<trim prefix="SET"> 
username=#{username},password=#{password}
</trim>
```   
   
- prefixOverrides : 실행될 쿼리의 <trim>문 안에 쿼리 가장 앞에 해당하는 문자들이 있으면 자동으로 지워준다.
```xml
<trim prefixOverrides="[문자열]"> 
쿼리문
</trim>
```
```xml
SELECT 
* 
FROM tb_board  
WHERE id = #{id} 
<trim prefixOverrides="OR">
OR TT LIKE '%' || #{searchContent} || '%' 
</if>
```

- suffix : 실행 될 쿼리의 <trim> 문 안에 쿼리 가장 뒤에 붙여준다.

```xml
<trim suffix="[문자열]"> 
쿼리문 
</trim>
```
```xml
<trim suffix=")"></trim>
```

- suffixOverrides : 실행될 쿼리의 <trim> 문 안에 쿼리 가장 뒤에 해당하는 문자들이 있으면 자동으로 지워준다.

```xml
<trim suffixOverrides="[문자열]"> 
쿼리문 
</trim>
```
```xml
<trim suffixOverrides=","></trim>
```
