## SELECT 문

```sql
SELECT 열1, 열2 FROM 테이블명
```

## WHERE 문

```sql
	SELECT 열1, 열2.... FROM 테이블명 WHERE 조건식
```

## WHERE문 조건식

1) no 열의 값이 2인 행 검색

```sql
SELECT * FROM sampleTable WHERE no = 2;
```

2) name 열의 값이 홍길동인 행 검색

```sql
SELECT * FROM sampleTable WHERE name = '홍길동';
```

수치형 상수의 경우 비교할 숫자를 그대로 조건식에 표기하지만, 2)에 ‘홍길동’처럼 문자열형을 비교할 경우 (‘ ’) 싱글쿼드로 둘러싸 표기해야한다.

3) no 열의 값이 2가 아닌 행 검색

```sql
SELECT * FROM sampleTable WHERE no <> 2;
```

4) null값 검색

```sql
SELECT * FROM sampleTable WHERE address IS NULL;
```

## 연산자

| 연산자 | 설명 |
| --- | --- |
| = | 좌변과 우변의 값이 같을 경우 참 |
| <> | 좌변과 우변의 값이 같지 않을 경우 참 |
| > | 좌변의 값이 우변의 값보다 클 경우 참 |
| ≥, > = | 좌변의 값이 우변의 값보다 크거나 같을 경우 참 |
| < | 우변의 값이 좌변의 값보다 클 경우 참 |
| ≤, < = | 우변의 값이 좌변의 값보다 크거나 같을 경우 참 |

## AND
AND절에 포함한 모든 조건이 충족이 되어야 참.

## OR
OR절 포함한 모든 조건 중 하나라도 충족이 되면 참
