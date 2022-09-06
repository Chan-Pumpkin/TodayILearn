## try문

- 예외 발생할 가능성이 있는 코드 문장을 try문 안에 넣는다.
- try 블록 내에서 예외가 발생하면 해당 예외가 연결된 예외 처리기에 의해 처리가 된다.
- 예외 처리기를 try문과 연결하려면, try문 뒤에 catch문을 작성해줘야 함.

```java
try {
    //code
}
//catch and finally blocks . . .
```

## catch문

- try문 바로 뒤에 하나 이상의 catch문을 제공하여 예외 처리기를 try문과 연결할 수 있다.
- 어떠한 코드도 try문의 끝과 첫 번째 catch문의 시작 사이에 있을 수 없다.
- 처리기가 처리할 수 있는 예외 유형을 선언하며,  Throwable클래스로부터 상속하는 클래스의 이름이어야 함.
- 예외 처리기는 오류 메시지를 인쇄하거나 프로그램을 중지하는 것 이상의 작업을 수행할 수 있습니다.

```java
try {

} catch (ExceptionType name) {

} catch (ExceptionType name) {

}
```

### 예시

```java
try {

} catch (IndexOutOfBoundsException e) {
    System.err.println("IndexOutOfBoundsException: " + e.getMessage());
} catch (IOException e) {
    System.err.println("Caught IOException: " + e.getMessage());
}
```

## printStackTrace(), getMessage()

### printStackTrace()

예외발생 당시의 호출스택(Call Stack)에 있었던 메서드의 정보와 예외 메시지를 화면에 출력한다.

### getMessage()

발생한 예외클래스의 인스턴스에 저장된 메시지를 얻을 수 있음.

## 멀티 catch 블럭

JAVA SE 7이상에서 하나의 catch문이 둘 이상의 예외 유형을 처리할 수 있다.

- vertical bar `|` 로 각 예외 유형을 구분함.
- vertical bar `|` 로 연결할 수 있는 예외 클래스의 개수에는 제한이 없다.

```java
catch (IOException|SQLException ex) {
    logger.log(ex);
    throw ex;
}
```

## finally 블럭

> try 또는 catch 문이 실행되는 동안 JVM이 종료되면, finally문은 실행되지 않을 수 있다.
- oracle 공식문서-
> 
- 항상 try문이 종료될 때 실행됨.
- 예외가 발생한 경우 try→catch→finally 순으로 실행됨.
- 예외가 발생하지 않은 경우 try→finally의 순으로 실행됨.

## **Try-With-Resources**

- try-with-resources 문은 하나 이상의 리소스를 선언하는 try 문입니다.
- 리소스는 프로그램이 완료된 후 닫아야 하는 개체입니다.
- try-with resources 문을 사용하면 각 리소스가 문의 끝에 닫힙니다.

다음 예제에서는 파일에서 첫 번째 줄을 읽습니다.

파일 판독기 및 버퍼 판독기 인스턴스를 사용하여 파일에서 데이터를 읽습니다.

### 예시)

- FileReader와 BufferedReader를 파일로부터 데이터를 읽는데 사용하는 예시
- FileReader 및 BufferedReader는 프로그램이 완료된 후 닫아야 하는 리소스입니다.
- FileReader 와 BufferedReader는 Java SE 7이상에서, `java.lang.AutoCloseable` 구현한다.

FileReader 및 BufferedReader 인스턴스는 try-with-resource 문에서 선언되므로 try 문이 정상적 또는 급작스럽게 완료되는지 여부 관계없이 닫힌다.

```java
static String readFirstLineFromFile(String path) throws IOException {
	    try (FileReader fr = new FileReader(path);
	         BufferedReader br = new BufferedReader(fr)) {
	        return br.readLine();
	    }
	}
```

## 참고
- 오라클 공식문서 [https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
- 자바의 정석 3rd Edition
