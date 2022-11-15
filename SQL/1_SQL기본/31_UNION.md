수학 집합을 배울 때, 합집합을 배운 적이 있었을 것이다.

SQL에서는 합집합 대신 UNION을 사용한다고 생각하면 좋다.

## 예시

### table_a 테이블

```sql
SELECT * FROM table_a;
```

### table_b 테이블

```sql
SELECT * FROM table_b;
```

### UNION

```sql
SELECT * FROM table_a
UNION
SELECT * FROM table_b
```

## 주의할 점

- UNION으로 묶기 위해서는 각각의 SELECT 명령의 열 구성이 일치해야함.
- 각 SELECT 명령에 ORDER BY를 지정해 정렬은 할 수 없지만, 마지막 SELECT 명령에만 지정할 수 있고, ORDER BY 구에 지정하는 열은 별명을 붙여 이름을 일치 시켜야한다.

```sql
SELECT woman_age AS age FROM table_a AS T
UNION
SELECT man_age AS age FROM table_b 
```

## 참조

sql 첫걸음
