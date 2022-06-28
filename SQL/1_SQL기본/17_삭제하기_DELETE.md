## 1. DELETE로 행 삭제

- DELECT 명령

```sql
DELETE FROM 테이블명 WHERE 조건식
```

- 해당 행 삭제 : no 열이 2인 행 삭제

```sql
DELETE FROM sample_table WHERE no = 2;
```

DELETE 명령은 WHERE 조건에 일치하는 모든 행을 삭제하기 때문에, 조건식을 잘못 지정하면 의도하지 않은 데이터마저 삭제될 수 있기에, 주의해야함.

## 2. DELETE 명령 구

- WHERE구는 DELETE 명령에서 사용할 수 있다.
- ORDER BY구는 DELETE 명령에서 사용할 수 없다.

ORDER BY구를 사용하게 되면 어떤 행부터 삭제할 것인지의 의미로서, 중요하지 않기 때문이다.

(다만, MySQL에서는 ORDER BY구와 LIMIT구를 사용해 삭제할 행을 지정할 수 있다. )
