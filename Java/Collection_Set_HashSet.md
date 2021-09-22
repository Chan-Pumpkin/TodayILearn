# HashSet

### HashSet   
- 기본적인 Set 컬렉션의 기본 클래스이다.
- 입력 순서를 보장하지 않고, 저장 순서도 유지하지 않는다.
- 중복되는 요소를 허용하지 않는다.

### HashSet 사용하는 예

'아이디'와 '닉네임'을 만들 때, '중복확인'을 눌러 중복된 '아이디'와 '닉네임' 확인할 때 사용
이는 데이터가 정렬되어있을 필요도 없고, 빠르게 중복되는 값인지만 찾으면 되기 때문에 유용한 방법이 될 수 있다.
hash에 의해 데이터의 위치를 특정시켜 해당 데이터를 빠르게 색인 할 수 있게 만든 것이다.

즉, Hash 기능과 Set 컬렉션이 합쳐진 것이 HashSet이다.
그렇기 때문에 삽입, 삭제, 색인이 매우 빠른 컬렉션 중 하나다.


### 중복을 걸러내는 과정

HashSet은 객체를 저장하기 전에 먼저 객체의 hashCode() 메소드를 호출해서 해시 코드를 얻어낸 다음 저장되어 있는 객체들의 해시 코드와 비교한 뒤 같은 해시 코드가 있다면, 다시 equals() 메소드로 두 객체를 비교해서 true가 나오면 동일한 객체로 판단하여 중복 저장을 하지 않는다.

문자열을 HashSet에 저장할 경우, 같은 문자열을 갖는 String객체는 동일한 객체로 간주되고 다른 문자열을 갖는 String객체는 다른 객체로 간주되는데, 그 이유는 String클래스가 hashCode()와 equals() 메소드를 재정의해서 같은 문자열일 경우 hashCode()의 리턴 값을 같게, equals()의 리턴 값은 true가 나오도록 했기 때문이다.

### HashSet 변수 선언   

```java
HashSet<데이터타입> 변수명 = new HashSet<데이터타입>();

HashSet<Integer> intSet = new HashSet<Integer>();
HashSet<String> stringSet = new HashSet<String>();
```
