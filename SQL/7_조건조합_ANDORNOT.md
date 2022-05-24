# 조건 조합 AND,OR,NOT

## 1. AND 조합

- 논리 연산자의 하나로서, 좌우 항목이 필요한 이항 연산자
- 모든 조건을 만족하는 경우 조건식은 참이 된다
- 좌우의 식 모두 참일 경우 AND 연산자는 참이 된다.

```sql
조건식1 AND 조건식2
```

### AND 조합 예시

a 컬럼에 0이 아닌 값과 b 컬럼에서 0이 아닌 값의 sample_table 행을 찾는다.

```sql
SELECT * FROM sample_table WHERE a <> 0 AND b <> 0 ;
```

## 2. OR 조합

- 논리 연산자의 하나로서, 좌우 항목 모두 필요한 이항 연산자
- 어느 쪽이든 하나만 참이 되면 조건식은 참이 된다.
- AND와 달리 어느 쪽이든 조건을 만족하면 결과는 참

```sql
조건식1 OR 조건식2
```

## 3. AND와 OR를 사용할 때 주의할 점.

### 1. AND와 OR의 좌우 주의할 점

- 아래의 코드는 올바른 결과를 얻을 수가 없다. 아래와 같이 사용하면, 논리 연산으로 ‘2’ 가 참이 되기 때문이다.

```sql
SELECT * FROM sample_table WHERE a = 1 OR 2;
```

- 아래의 코드와 같이 사용해야 올바른 결과를 얻을 수 있다.

```sql
SELECT * FROM sample_table WHERE a = 1 OR a = 2;
```

### 2. 연산자의 우선순위

- OR보다 AND가 우선순위 높다.

### 예시

```sql
WHERE aa = 1 OR aa = 2 AND bb = 1 OR bb = 2
```

위에 조건은 아래와 같이 나누어짐.

- aa = 1
- aa = 2 AND bb = 1
- bb = 2

## 4. NOT 조합

- 오른쪽에만 항목을 지정하는 단항 연산자
- 오른쪽에 지정한 조건식의 반대 값을 반환
- 조건식이 참을 반환하면 NOT은 이에 반하는 거짓을 반환

```sql
NOT 조건식
```

### 예시

- aa 컬럼이 0이 아니거나, bb 컬럼이 0이 아닌 행을 제외한 나머지 행을 검색

```sql
SELECT * FROM sample_table WHERE NOT(aa<>0 OR bb<>0);
```
