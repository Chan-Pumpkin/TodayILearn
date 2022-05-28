# ORDER BY

## 1. ORDER BY 정렬

- WHERE 구 뒤에 ORDER BY 구를 지정하는 경우

```sql
SELECT 컬럼명 FROM 테이블명 WHERE 조건식 ORDER BY 컬럼명
```

- FROM 구 뒤에 ORDER BY 구를 지정하는 경우

```sql
SELECT 컬럼명 FROM 테이블명 ORDER BY 컬럼명
```

## 2. ORDER BY 내림차순, 오름차순

- 내림차순 : DESC

```sql
SELECT 컬럼명 FROM 테이블명 ORDER BY 컬럼명 DESC
```

- 오름차순 : ASC

```sql
SELECT 컬럼명 FROM 테이블명 ORDER BY 컬럼명 ASC
```

## 3. 대소관계

### 1) 대소관계

- ORDER BY로 정렬할 때 값의 대소관계가 중요함.
- 수치형 데이터는 숫자의 크기 판별이므로 이해하기 쉬움.
- 문자열 데이터는 알파벳이나, 한글 자모음 배열순서를 사용해서 나열 가능

예)

1 가위

2 노랑

3 도둑

### 2) Varchar 컬럼과 Integer 컬럼의 차이

- a_column이 varchar일 경우

보통 숫자로 정렬을 하게 되면, 수치상 크기를 비교를 하지만, 컬럼의 타입이 varchar일 경우 문자로 인식되어 대소관계 계산방법이 달라진다.

```sql
SELECT * FROM sample_table ORDER BY a_column;
```

| a_column |
| --- |
| 1 |
| 13 |
| 18 |
| 3 |

## 4. ORDER BY는 테이블에 영향X

SELECT 명령으로 행 순서를 바꾸어 결과를 반환하는 것뿐, 저장장치에 저장된 데이터의 행 순서를 변경하는 것은 아니다.
