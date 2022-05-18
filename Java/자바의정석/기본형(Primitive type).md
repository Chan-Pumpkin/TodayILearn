# 기본형

## 1) 논리형 - boolean

- boolean형 변수에는 true와 false 중 하나를 저장한다
- default는 false이다.
- boolean형 변수는 대답(yes/no), 스위치(on/off)등의 논리 구현에 주로 사용
- boolean의 크기는 1byte
- 대소문자 구별되기에 true/false를 사용할 때 주의해야 함.

Q. boolean형은 2가지의 값만 표현하면 되는데, 크기는 왜 1byte?

- 자바에서 다루는 데이터 최소단위가 byte이기 때문에.

## 2) 문자형 - char

- char 타입의 변수는 단 하나의 문자만 저장할 수 있다.
- 크기는 2byte(=16bit)
- char은 문자형으로 음수가 될 수 없음

Q. char은 문자가 아닌 유니코드가 저장된다?

```java
char test = 'A';
```

- 변수에 문자가 저장되는 거 같지만, ‘문자의 유니코드’가 저장됨.
- 컴퓨터는 숫자밖에 모르기 때문에, 모든 데이터를 숫자로 변환하여 저장하는 것.

![기본형](https://user-images.githubusercontent.com/62877858/169051831-ad848761-eb2e-4274-9098-bbb1c049a4ed.png)

Q. 그럼 유니코드를 알 수 있을까?

- int 타입으로 형변환을 하면 된다.

```java
char test = 'A';
int testnum = (int) test
```

## 3) 특수문자

| 특수문자 | 문자 리터럴 |
| --- | --- |
| tab | \t |
| backspace | \b |
| form feed | \f  |
| new line | \n |
| carriage return | \r |
| 역슬래쉬 | \\ |
| 작은 따옴표 | \’ |
| 큰 따옴표 | \” |
| 유니코드(16진수)문자 | \u유니코드 |

## 4) char타입의 표현방식

- 예) 문자 ‘A’를 저장하면 65를 2진수로 저장된다.

![기본형2](https://user-images.githubusercontent.com/62877858/169051905-6812f303-cdf9-438c-a330-ac3e8a0c14ac.png)


- char 타입에 저장 되는 값인 유니코드는 모두 양수이므로 (범위 : 0~65535)
- 정수형인 short은 절반은 음수표현에 사용 (범위 : -32768~32767)

![기본형3](https://user-images.githubusercontent.com/62877858/169051952-53490ef9-7eb9-474f-b3aa-46c592d91cba.png)


## 5) 인코딩과 디코딩

- 인코딩 : ‘A’ → 65
- 디코딩 : ‘A’ ← 65

ex) 유니코드를 이용한 인코딩 / 디코딩

- 문자를 코드로 변환하는 것은 문자 인코딩
- 코드를 문자로 변환하는 것은 문자 디코딩

*인코딩에 사용된 코드표와 디코딩에 사용된 표가 다르면 엉뚱한 글자들로 바뀜
