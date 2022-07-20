# jsonb_array_elements()

여러 개의 json 데이터가 있는 한 컬럼에서 json 데이터를 여러행으로 select하는 함수

## 예시

> cls(json 데이터가 있는 컬럼) 컬럼에 있는 여러 json 데이터를 여러 행으로 select 해보려고 함.
> 

### 22562954의 cls를 select 했을 때

- sql 문

```sql
select cls from ps_service_ctlg where ctlg_sn = '22562954'
```

- 결과

| cls |
| --- |
| [[{"lang": "ko", "subject": "정보검색", "valueURI": "EE0112", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}], [{"lang": "ko", "subject": "달리 분류되지 않는 자연재해 분석/예측", "valueURI": "ND0799", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}], [{"lang": "ko", "subject": "달리 분류되지 않는 건설/교통", "valueURI": "EI9999", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}]] |

### jsonb_array_elements() 함수 사용했을 때

- SQL 문

```sql
select ctlg_sn, jsonb_array_elements(cls) from ps_service_ctlg
where ctlg_sn = '22562954'
```

- 결과

| ctlg_sn | jsonb_array_elements |
| --- | --- |
| 22562954 | [{"lang": "ko", "subject": "정보검색", "valueURI": "EE0112", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}] |
| 22562954 | [{"lang": "ko", "subject": "달리 분류되지 않는 자연재해 분석/예측", "valueURI": "ND0799", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}] |
| 22562954 | [{"lang": "ko", "subject": "달리 분류되지 않는 건설/교통", "valueURI": "EI9999", "schemeURI": "S", "subjectScheme": "과학기술표준분류"}] |

### jsonb_array_elements() 함수 중첩 사용했을 때

- SQL 문

```sql
select ctlg_sn, jsonb_array_elements(jsonb_array_elements(cls)) from ps_service_ctlg
where ctlg_sn = '22562954'
```

- 결과

| ctlg_sn | jsonb_array_elements |
| --- | --- |
| 22562954 | {"lang": "ko", "subject": "정보검색", "valueURI": "EE0112", "schemeURI": "S", "subjectScheme": "과학기술표준분류"} |
| 22562954 | {"lang": "ko", "subject": "달리 분류되지 않는 자연재해 분석/예측", "valueURI": "ND0799", "schemeURI": "S", "subjectScheme": "과학기술표준분류"} |
| 22562954 | {"lang": "ko", "subject": "달리 분류되지 않는 건설/교통", "valueURI": "EI9999", "schemeURI": "S", "subjectScheme": "과학기술표준분류"} |

## 참고

[How to turn a json array into rows in postgres](https://stackoverflow.com/questions/36174881/how-to-turn-a-json-array-into-rows-in-postgres)
