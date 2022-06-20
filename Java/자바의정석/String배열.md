## 1. String배열의 선언과 생성

```java
String[] name = new String[3]; // 3개의 문자열을 담을 수 있는 배열을 생성한다.
```

3개의 String타입의 참조변수를 저장하기 위한 공간이 마련되고 참조현 변수의 기본값은 `null` 이므로 각 요소의 값은 `null`로 초기화 된다.

![1](https://user-images.githubusercontent.com/62877858/174629068-d67aec05-72f3-418c-8578-307f11a89c0d.png)


- 변수 타입의 기본 값

| 자료형 |  기본값 |
| --- | --- |
|  boolean | false |
| char | ‘\u0000’ |
| byte, short, int | 0 |
| long | 0L |
| float | 0.0f |
| double | 0.0d 또는 0.0 |
| 참조형 변수 | null |

## 2. String배열의 초기화

### 배열 초기화

```java
String[] name = new String[5]; //길이가 5인 String 배열 생성
name[0] = "Lee";
name[1] = "Kim";
name[2] = "Seo";
name[3] = "Jo";
name[4] = "Park";
```

### 간단히 초기화

```java
String[] name = new String[]{"Lee","Kim","Seo","Jo","Park"};

String[] name = {"Lee","Kim","Seo","Jo","Park"}; //new String[] 생략 가능
```

### 배열 그림 요약

![2](https://user-images.githubusercontent.com/62877858/174629122-93ce130b-f063-4a67-98d5-fe250f23c0ba.png)


- 배열에 실체 객체가 아닌 객체의 주소가 저장되어있음.
- 기본형 배열이 아닌 경우(참조형 배열), 배열에 저장되는 것은 객체의 주소
- 참조형 배열을 객체 배열이라고도 함.

## 3. char배열과 String 클래스

### 문자열이란?

문자를 연이어 늘어놓은 것으로 char배열과 같은 뜻

### char배열이 아닌 String클래스를 이용하는 이유는?

String클래스는 char배열에 여러 기능(메서드)를 추가하여 확장한 것이기 때문에 String 클래스를 사용하는 것이 문자열을 다루기 더 편리함.

### String클래스의 주요 메서드

| 메서드 | 설명 |
| --- | --- |
| char charAt(int index) | 문자열에서 해당 위치(index)에 있는 문자를 반환한다. |
| int length() | 문자열의 길이를 반환한다. |
| String substring(int from, int to) | 문자열에서 해당 범위(from~to)에 있는 문자열을 반환한다. |
| boolean equals(String str) |  문자열의 내용이 같은지 확인한다.
결과는 true, 다르면 false가 된다. |
| char[] toCharArray() | 문자열을 문자배열(char[])로 변환해서 반환한다. |

### charAt 메서드

문자열에서 지정된 index에 있는 한 문자를 가져옴.

### substring()

문자열의 일부를 뽑아낼 수 있다.

주의할 점으로는 범위의 끝은 포함되지 않는다.

ex) index 범위 2~5라면 5는 포함되지 않음.

### equals()

문자열의 내용이 같은지 다른지 확인하는데 사용

기본형 변수의 값을 비교하는 경우 `==` 연산자 사용

문자열의 내용을 비교할 때는 `equals()` 를 사용

대소문자 구분은 `equals()` , 대소문자 구분 없는 것은 `equalsIngnoreCase()`

### char배열과 String클래스 변환

```java
char[] chArr = new String(chArr);
String str = new String(chArr); // char배열 -> String
char[] tmp = str.toCharArray(); // String -> char배열
```

JVM은 입력된 매개변수가 없을 때, null 대신 크기가 0인 배열 생성을 한다.
