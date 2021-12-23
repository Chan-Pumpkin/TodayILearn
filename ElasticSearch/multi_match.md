# multi_match

하나의 값으로 여러 필드에 조건을 걸어 검색을 한다.

## 예시

```
{
    "query": {
        "multi_match" : {
            "query":    "Nike",
            "fields": [ "sports_brand", "shoes_brand" ]
        }
    }
}
```
