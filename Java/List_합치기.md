# List 합치기

### list.addAll()
```java
total.addAll(aaList);
```

### stream 이용해서 합치기
```java
List<String> totalList = Stream.concat(aaList.stream(), bbList.stream()).collect(Collectors.toList());
```

### stream 이용해서 중복 없이 합치기
```java
List<String> totalList = Stream.concat(aaList.stream(), bbList.stream()).distinct().collect(Collectors.toList());
```
