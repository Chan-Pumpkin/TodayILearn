# equals

![object_equals](https://user-images.githubusercontent.com/62877858/191760418-dbe6d101-b5c6-408a-bbc9-be2a41d2cba0.png)
    
`equals()`의 실제 내용이다.

서로 다른 두 객체를 `equals()`메서드로 비교하면 항상 false로 결과를 가져올 것이다.

왜냐하면, 두 객체의 같고 다름을 참조변수의 값으로 판단하기 때문이다.

한마디로, `equals()`는 두 인스턴스의 주소값을 비교하여 같은 인스턴스인지를 확인하고 같으면 `true`, 다르면 `false`의 `boolean`값을 리턴하는 메서드이다.

## 에? String으로 값을 비교할 때, true로 가져올 때는 뭐에요?

주소값을 비교할 때 사용하는 `equals()`라면서요..뭐지!?    
     
    

![string_equals](https://user-images.githubusercontent.com/62877858/191760679-1fd050b0-4961-466f-9666-8fad8474ad78.png)

String 클래스의 `equals()`는 오버라이딩 즉, 재정의가 되어있기 때문에 Object 클래스의 `equal()`와는 다르다.

String 클래스의 `equals()`는

1) 객체가 자기 자신과의 주소값이 같으면 true를 리턴한다.

2) 주소 값이 다르다면 Char 타입으로 하나하나 비교해서 같으면 true 다르면 false로 리턴한다.

String 클래스의 `equals()` 메소드는 비교하고자 하는 두개의 대상의 값 자체를 비교한다

## 참고

• [https://118k.tistory.com/458](https://118k.tistory.com/458)

• [https://go-coding.tistory.com/35](https://go-coding.tistory.com/35)

• 자바의 정석 3rd Edition
