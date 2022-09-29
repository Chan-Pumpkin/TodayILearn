## ORACLE DB link CLOB 오류 발생
CLOB 컬럼은 데이터베이스 링크로 테이블 컬럼 조회가 안되는 문제가 발생

![DBLinkCLOBError](https://user-images.githubusercontent.com/62877858/193050282-309e7783-acb4-4157-8b9d-453717473853.png)

Oracle에서 개발 DB에서 운영 DB의 테이블을 DB link 방식으로 연결해서 SELECT를 해야한다. 하지만, 위와 같은 오류가 발생.

## LOB타입

그 전에 LOB타입에 대해서 먼저 알아야할 거 같다.

LOB 타입은 Large Object라는 의미로서, 대용량의 데이터를 저장하고 관리하기 위해서 오라클에서 제공하는 타입이다. 사진, 영상 등의 대용량 데이터도 DB로 처리할 수 있도록 하기 위해 생겨난 타입

## LOB타입 종류

| 종류 | 파일 | 저장방식 |
| --- | --- | --- |
| BLOB | Internal | 바이너리 데이터 저장 (최대 4G 저장) 컴퓨터가 인식하는 모든 파일 기록 |
| CLOB | Internal | Single-byte character data 저장(최대 4G 저장) 텍스트 데이터 저장 |
| NCLOB | Internal | Multi-byte character data 저장(최대 4G 저장) NCHAR data와 같은 national character set(9i 이상 유니코드) |
| BFILE | External(OS) | OS 파일에 저장된 데이터의 포인터 저장 (최대 4G 저장) READ ONLY |

## 왜 오류가 발생..?

오라클에서는 LOB 타입에 대해 원격지 DB간의 조회-삽입(수정)을 지원하지 않기 때문에, 발생하는 문제

## 해결 방법

로컬에 원격지의 테이블을 만들어준다.

```sql
create table temp_원격테이블asselect * from [원격테이블@DB](mailto:%EC%9B%90%EA%B2%A9%ED%85%8C%EC%9D%B4%EB%B8%94@DB)링크명where 1=2;
```

원격지 테이블을 그대로 insert해온다.

```sql
insert into temp_원격테이블select * from [원격테이블@DB](mailto:%EC%9B%90%EA%B2%A9%ED%85%8C%EC%9D%B4%EB%B8%94@DB)링크명
```

이제 로컬 테이블에서 사용한다.

```sql
select * from temp_원격테이블where rownum = 1;
```

## 참조

[https://blog.naver.com/nolbudr/150030600887](https://blog.naver.com/nolbudr/150030600887)

[https://ooz.co.kr/280](https://ooz.co.kr/280)

[http://www.gurubee.net/lecture/2768](http://www.gurubee.net/lecture/2768)
