# 리스트 중복 제거

```java
// List 준비        
List<String> list = Arrays.asList("A", "B", "C", "C");         
// 중복 제거        
List<String> distictList = list.stream().distinct().collect(Collectors.toList());          

```

Stream의 distinct() 이용해서 list에서 중복이 되는 값 제거 한다.

## 출처
https://hianna.tistory.com/582
