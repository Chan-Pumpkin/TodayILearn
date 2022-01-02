# ElasticSearch 개념

## ElasticSearch란?
Elasticsearch는 Apache Lucene( 아파치 루씬 ) 기반의 Java 오픈소스 분산 검색 엔진입니다.

## ElasticSearch 사용이유
- 검색 속도 빠름
- 분산환경 :   
샤드(shard)라는 단위로 나누어 데이터를 분산하고, 빠르게 제공함.
- 광범위한 기능 제공 :   
데이터를 효율적으로 저장하고 검색할 수 있는 기본 기능들이 탑재되어 있음.

## ElasticSearch 용어
- 매핑(Mapping):     
RDBMS의 스키마와 같은 개념으로, 인덱스/타입/문서의 규칙을 정의한 것으로 사용자가 마음대로 정의할 수 있다.     
- 인덱스(index):     
RDBMS의 database과 같은 개념
- 타입(type):     
RDBMS의 table과 같은 개념
- 로우(row):      
RDBMS의 row과 같은 개념
- 필드(Field):     
RDBMS의 Column과 비슷한 개념으로써, 엘라스틱서치 문서는 JSON인데, 각 JSON의 프로퍼티를 엘라스틱서치에서 필드라고 부른다.    

## ElasticSearch GET/PUT/POST/DELETE
ElasticSearch의 GET/PUT/POST/DELETE를 RDBMS와 CRUD로 비교해보면 아래와 같다.
- GET      
RDBMS : SELECT      
CRUD : READ      
- PUT      
RDBMS : UPDATE       
CRUD : UPDATE      
- POST      
RDBMS : INSERT     
CRUD : CREATE      
- DELETE      
RDBMS : DELETE      
CRUD : DELETE     



