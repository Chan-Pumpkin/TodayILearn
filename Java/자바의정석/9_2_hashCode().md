## 해시코드란

객체를 식별하는 하나의 정수값

## hashCode() 메소드

해싱기법에 사용되는 해시함수를 구현한 것으로, 객체의 해시코드값을 반환한다.

## hashCode() 메소드의 규약?

- 변경되지 않은 한 객체의 hashCode 메소드를 호출한 결과는 항상 똑같은 integer 값이어야 한다.
: 객체가 변경 되었더라도, equals() 메소드가 참고하는 정보가 변경되지 않았다면, hashCode() 값은 달라지지 않는다.
- equals() 메소드가 같다고 판별한 두 객체의 hashCode() 호출 결과는 똑같은 integer 값이어야 한다.
- java.lang.Object.equals 메소드가 다르다고 판별한 두 객체의 hashCode()의 값이 반드시 달라야하는 것은 아니다.
: 단, 같지 않은 객체들이 각기 다른 hashCode 값을 가지면 해시 테이블 성능이 향상된다.

## String 클래스
![StringHashCode](https://user-images.githubusercontent.com/62877858/192554207-6dfc7435-9b98-4f2c-ac1b-76144fc31fe0.png)

String 클래스에서 hashCode() 메소드는 동일한 해시코드를 반환하도록 hashCode() 메소드가 오버라이딩이 되어있기에, 문자열이 같은 String 클래스의 객체라면 hashCode() 메소드를 호출했을 때 항상 동일한 해시코드값을 갖는다.

## System.identityHashCode(Object x)
![identityHashCodeEx1](https://user-images.githubusercontent.com/62877858/192554270-46f1578d-91c6-4b7d-81c5-2217500cd44a.png)
![identityHashCodeEx2](https://user-images.githubusercontent.com/62877858/192554296-e5931edf-a2e4-4883-b473-bdfd580d1a50.png)     

모든 객체에 대해 항상 다른 해시코드값을 반환할 것을 보장한다.

위와 같이 str1과 str2는 같은 객체를 가르켜서, 같은 해시코드값이 반환이 되지만, str3와 str4는 다른 객체를 의미하기에 다른 해시코드값이 반환이 된다.

## 참고

[https://docs.oracle.com/javase/10/docs/api/java/lang/Object.html](https://docs.oracle.com/javase/10/docs/api/java/lang/Object.html)

[https://johngrib.github.io/wiki/java/object-hashcode/](https://johngrib.github.io/wiki/java/object-hashcode/)

[https://blog.naver.com/PostView.nhn?isHttpsRedirect=true&blogId=travelmaps&logNo=220931531769&redirect=Dlog&widgetTypeCall=true](https://blog.naver.com/PostView.nhn?isHttpsRedirect=true&blogId=travelmaps&logNo=220931531769&redirect=Dlog&widgetTypeCall=true)

[https://dbjh.tistory.com/36](https://dbjh.tistory.com/36)
