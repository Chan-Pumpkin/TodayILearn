# StringUtils

## StringUtils 라이브러리는 왜 사용할까
Null-safe가 가능하다.


### StringUtils.defaultIfEmpty 
- 해당 변수가 Null이면 해당 문구로 바꿔줌.

```java
StringUtils.defaultIfEmpty( 변수 , 문구 or 변수);
```

### StringUtils.equals(문자열, 비교할문자열)
- String 클래스의 경우 값이 null이면 NullPointerException이 발생한다.
- StringUtils 클래스의 경우 문자열이 null 이어도 예외가 발생하지 않고 null로 반환함.

## 참고
- 김민태 차장님
- https://velog.io/@kmdngmn/Java-StringUtils%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0
- https://bigstupid.tistory.com/40
