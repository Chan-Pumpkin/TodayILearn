# 기본형(Primitive type)

논리형 - boolean

- boolean형 변수에는 true와 false 중 하나를 저장한다
- default는 false이다.
- boolean형 변수는 대답(yes/no), 스위치(on/off)등의 논리 구현에 주로 사용
- boolean의 크기는 1byte
- 대소문자 구별되기에 true/false를 사용할 때 주의해야 함.

Q. boolean형은 2가지의 값만 표현하면 되는데, 크기는 왜 1byte?

- 자바에서 다루는 데이터 최소단위가 byte이기 때문에.

문자형 - char

- char 타입의 변수는 단 하나의 문자만 저장할 수 있다.
- 크기는 2byte(=16bit)
- char은 문자형으로 음수가 될 수 없음

Q. char은 문자가 아닌 유니코드가 저장된다?

```java
char test = 'A';
```

- 변수에 문자가 저장되는 거 같지만, ‘문자의 유니코드’가 저장됨.
- 컴퓨터는 숫자밖에 모르기 때문에, 모든 데이터를 숫자로 변환하여 저장하는 것.


Q. 그럼 유니코드를 알 수 있을까?

- int 타입으로 형변환을 하면 된다.

```java
char test = 'A';
int testnum = (int) test
```
