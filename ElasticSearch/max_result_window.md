# ElasticSearch 오류
ElasticSearch는 검색 데이터 최대 개수 제한이 10000개라서, 10000개 이상의 데이터를 검색했을 때, 아래와 같은 오류 메시지를 볼 수 있다.
```
Result window is too large, from + size must be less than or equal to: [10000] but was [32100].      
See the scroll api for a more efficient way to request large data sets.     
This limit can be set by changing the [index.max_result_window] index level parameter      
```
다행히 아래와 같이 이것은 설정을 변경을 해주면, 원하는 값만큼 검색할 수가 있다. 아래의 설정은 데이터를 50000개까지 가져올 수 있도록 설정을 할 수 있는 것이다. 하지만, 많이 늘리면 성능에 문제가 생길 수 있다고 한다.
```
PUT your_index_name/_settings 
{ 
"max_result_window" : 50000
}
```
