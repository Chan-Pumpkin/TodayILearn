# HashMap

## HashMap
Map의 인터페이스를 구현한 대표적인 Map 컬렉션 입니다.   
HashMap 이름대로 해싱(Hashing)을 사용하기 때문에 많은 양의 데이터를 검색하는 데 있어서 뛰어난 성능을 보입니다.

## 해싱이란   
데이터를 Key, value값으로 저장하는 구조의 해시테이블에 저장을 해서,   
하나하나 값을 비교하면서 검색을 하는 것이 아닌,   
키에 산술적인 연산을 적용하여 항목이 저장되어 있는 테이블의 주소를 계산하여 항목에 접근하는 것.

## 예제
- HashMap 선언
```
HashMap<키 자료형, 값 자료형> map이름 = new HashMap<키 자료형, 값 자료형>();

HashMap<String, String> mapA = new HashMap<String, String>(); // 예시
```

- 값 추가
```
변수 이름.put(Key, Value);

mapA.put("1", "Hi"); //예시
```
