# 결과행 제한하기 LIMIT

```sql
SELECT 컬럼명 FROM 테이블명 LIMIT 행수 [OFFSET 시작행]
```

## 1. 행수 제한

- LIMIT 구는 표준 SQL이 아니다.
- MySQL과 PostgreSQL에서 사용할 수 있는 문법이다.
- LIMIT 구는 SELECT 명령의 마지막에 지정하는 것으로 WHERE 구나 ORDER BY 구의 뒤에 지정
- LIMIT 다음에 최대 행수를 수치로 지정

```sql
SELECT 컬럼명 FROM 테이블명 WHERE 조건식 ORDER BY 컬럼명 LIMIT 행수
```

### 예시 - 10개의 행이 있는 테이블에 LIMIT로 7개 제한 결과

```sql
SELECT * FROM sample_table LIMIT 7;
```

| number |
| --- |
| 1 |
| 2 |
| 3 |
| 4 |
| 5 |
| 6 |
| 7 |

### WHERE 과 다른 LIMIT

- WHERE number <= 7 과 같은 조건을 붙인다면, 동일한 위에 예시와 같은 결과를 얻을 수 있음.
- 그래도 LIMIT와 WHERE은 기능과 내부처리 순서가 전혀 다름.
- LIMIT는 반환할 행수를 제한하는 기능
- WHERE 구로 검색한 후, ORDER BY로 정렬된 뒤 최종적으로 처리 되는 것

### LIMIT를 사용할 수 없는 데이터베이스에서의 행 제한

- LIMIT는 표준 SQL이 아니기 때문에, MySQL과 PostgreSQL
- SQL Server에서는 LIMIT와 비슷한 기능을 하는 ‘TOP’를 사용할 수 있다.

```sql
SELECT TOP 7 * FROM sample_table;
```

- Oracle에는 LIMIT도 TOP도 없는 대신, ROWNUM이라는 열을 사용
- 여기서, ROWNUM은 각 행에 할당되는 행 번호
- ROWNUM으로 행 제한할 때는 WHERE 구로 지정하므로 정렬하기 전에 처리되어 LIMIT로 행을 제한한 경우와 결괏값이 다름.

```sql
SELECT * FROM sample_table WHERE ROWNUM <=7;
```

## 2. 오프셋 지정

- 커뮤니티 사이트, 게시판 등에서 하단 부분에 페이지 나누기 사용할 때 자주 사용
- OFFSET은 시작 위치 지정이다.
- 위치 지정은 0부터 시작한다.

### OFFSET 사용 문법

```sql
SELECT 열명 FROM 테이블명 LIMIT 행수 OFFSET 위치
```

### 예시 - 5개씩 제한 두는 상황에서 시작위치 4부터 시작

```sql
SELECT * FROM sample_table LIMIT 5 OFFSET 4;
```

| number |
| --- |
| 5 |
| 6 |
| 7 |
| 8 |
| 9 |
