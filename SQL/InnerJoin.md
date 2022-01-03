# InnerJoin

### 1. INNERJOIN   
INNERJOIN은 ON절과 함께 사용되며, ON절의 조건을 만족하는 데이터만을 가져온다.   

### 2. INNERJOIN 문법    
문법 1   
``` SQL
첫 번째 테이블 이름
INNER JOIN 
두 번째 테이블 이름
ON 조건
```
문법 2   
``` SQL
첫 번째 테이블 이름
JOIN 
두 번째 테이블 이름
ON 조건
```

예시
```sql
SELECT * 
FROM A_TABLE AS A 
INNER JOIN B_TABLE AS B 
ON A_TABLE.COL1 = B_TABLE.COL1;
```
