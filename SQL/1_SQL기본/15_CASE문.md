## 1. CASE문

### CASE문 문법

```sql
-- [] 괄호는 생략 가능
CASE 
WHEN 조건식1 THEN 식1
[WHEN 조건식2 THEN 식2]
[ELSE 식3]
END
```

- `WHEN` 절에는 참과 거짓을 반환하는 조건식을 기술
- `THEN`절은 해당 조건을 만족하여 참이 되는 경우 `THEN` 절에 기술한 식 처리됨.
- `WHEN` 절의 조건식을 차례로 평가하다가 `THEN` 절 식의 처리결과를 `CASE` 문의 결과값으로 반환
- 그 어떤 조건식도 만족하지 못한 경우에는 `ELSE` 절에 기술한 식이 채택
- `ELSE` 는 생략 가능하며 생략했을 경우 ‘ELSE NULL’로 간주 됨.

### CASE문 예시

- SQL

```sql
select 
case 
when contents = '<p>aa</p>' then '내용 있음 aa' 
when contents is null then '없음'
else '미지정' end '내용' from tb_board;
```

- 결과

| 내용 |
| --- |
| 내용 있음 aa |
| 미지정 |
| 내용 있음 aa |
| 없음 |

### COALESCE

```sql
SELECT b, COALESCE(b,0) FROM sampleTable
```

- NULL 값을 변환하는 경우라면 COALESCE 함수를 사용하는 편이 더 쉽다.
- `COALESCE`는 여러 개의 인수를 지정할 수 있음.
- b가 null이 아니면 그대로 출력, 그렇지 않으면 0이 출력됨.

## 2. 다른 CASE문

### 수치 데이터를 이용한 CASE문

```sql
WHEN a=1 THEN '숫자1'
WHEN a=2 THEN '숫자2'
```

- 문자열로 변환하기 위해 사용할 수 있음.
- 디코드 : 수치 데이터 → 문자화
- 인코드 : 문자화 → 수치 데이터

## 3. CASE를 사용할 경우 주의사항

### CASE문은 어디에나 사용 가능

- WHERE 구에서 조건식의 일부로도 사용 가능
- ORDER BY 구에서도 사용 가능
- SELECT 구에서도 사용 가능
- 어디에나 사용 가능

### ELSE 생략하면 ELSE NULL이 된다

- 대응하는 WHEN이 하나도 없으면 ELSE 절이 사용되는데, 생략하게 되면 NULL이 반환 됨.
- 따라서 웬만하면 ELSE를 생략하지 않고, 지정하는 편을 추천함.

### WHEN에 NULL 지정

- 비교 연산자 `=` 로 NULL 값이 같은지 아닌지 비교할 수 없다.
- NULL 값인지 아닌지를 판정하기 위해서는 `IS NULL`을 사용한다.

### DECODE NVL

Oracle에는 이 같은 디코드를 수행하는 DECODE 함수가 내장 되어있고, CASE문과 같은 용도로 사용할 수 있지만, CASE문은 표준 SQL로 규정된 덕분에 많은 데이터베이스에서 지원을 한다.
