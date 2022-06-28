## 1. INSERT로 행 추가하기

```sql
INSERT INTO test_sample VALUE (2, 'AAA', 'BBB');
```

## 2. 값을 저장할 열 지정

- 해당 열을 지정해서 INSERT를 할 경우에는 VALUES 구의 개수가 동일해야한다.

```sql
INSERT INTO 테이블명 (열1, 열2, ....) VALUES(값1, 값2, ...);
```

## 3. NOT NULL 제약

- 유효한 값이 없는 상태로 두고싶을 때, NULL로 값을 지정할 수 있음.
- NOT NULL 값을 허용하지 않은 NOT NULL 제약이 걸려있으면 에러가 발생함

```sql
INSERT INTO test_sample VALUE (1, NULL, NULL);
```

## 4. DEFAULT

- Default는 명시적으로 값을 지정하지 않았을 경우 사용하는 초기값
- Default 값은 테이블의 정의할 때 지정할 수 있다.
- 열을 지정해 행을 추가할 때 지정하지 않은 열은 Default 값을 사용하여 저장된다.

- 테이블 열 구성 확인 (postgre에서는 안됨.)

테이블 열 구성을 확인해보면, Default값을 확인할 수 있다.

```sql
DESC sample_table;
```

- 해당 열에 DEFAULT 지정

```sql
INSERT INTO test_sample VALUE (2, DEFAULT, DEFAULT);
```

- 암묵적으로 디폴트 저장

디폴트값으로 저장한 열은 INSERT 명령문에서 생략을 해도 DEFAULT 값으로 INSERT가 된다. 

```sql
INSERT INTO test_sample(no) VALUE (2);
```
