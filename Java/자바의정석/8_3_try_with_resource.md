## **Try-With-Resources**

- try-with-resources 문은 하나 이상의 리소스를 선언하는 try 문입니다.
- 리소스는 프로그램이 완료된 후 닫아야 하는 개체입니다.
- try-with resources 문을 사용하면 각 리소스가 문의 끝에 닫힙니다.

### 사용 방법

- FileReader 및 BufferedReader는 프로그램이 완료된 후 닫아야 하는 리소스입니다.
- FileReader 와 BufferedReader는 Java SE 7이상에서, `java.lang.AutoCloseable` 구현한다.
- FileReader 및 BufferedReader 인스턴스는 try-with-resource 문에서 선언되므로 try 문이 정상적 또는 급작스럽게 완료되는지 여부 관계없이 자동으로 닫힌다.

```java
static String readFirstLineFromFile(String path) throws IOException {
	    try (FileReader fr = new FileReader(path);
	         BufferedReader br = new BufferedReader(fr)) {
	        return br.readLine();
	    }
	}
```

## Try-With-Resources를 권하다

Java SE 7 이전 버전에서는 try 문이 정상적으로 완료되는지 또는 갑자기 완료되는지 여부에 관계없이 최종 블록을 사용하여 리소스를 닫을 수 있습니다.

finally문 예시)

```java
static String readFirstLineFromFileWithFinallyBlock(String path) throws IOException {
   
    FileReader fr = new FileReader(path);
    BufferedReader br = new BufferedReader(fr);
    try {
        return br.readLine();
    } finally {
        br.close();
        fr.close();
    }
}
```

이 예시에서는 리소스 누수가 있을 수 있다.

프로그램이 완료되면 GC(가비지 수집기)를 사용하여 리소스의 메모리를 회수하는 것 이상의 작업을 수행해야 한다. 또한 프로그램은 일반적으로 리소스의 닫기 메서드를 호출하여 리소스를 운영 체제에 다시 릴리스해야 한다.

그러나 GC가 리소스를 회수하기 전에 프로그램이 이 작업을 수행하지 못하면 리소스를 해제하는 데 필요한 정보가 손실 되어지고, 그 리소스는 운영체제에서 여전히 사용되는 것으로 간주되어 누출 되어짐.

위에 예시에서 만약 readLine 메소드에서 예외가 발생하고, finally문의 br.close()에서도 예외가 발생한다면, FileReader는 누수가 되어진 것이다.

그러므로 finally문으로 프로그램 리소스를 닫는 대신에 try-with-resources문을 사용해야함.

## 참고

- 오라클 공식문서 [https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)
