
# 코드 예제
```java
import java.util.ArrayList;
import java.util.List;

public class joinTest {
    public static void main(String[] args) {
        List<String> joinTest = new ArrayList<>();
        joinTest.add("a");
        joinTest.add("b");
        joinTest.add("c");

        String joinStringTest1 = String.join("\"", joinTest);
        String joinStringTest2 = String.join("\" \"", joinTest);
        String joinStringTest3 = String.join("\"\"", joinTest);
        String joinStringTest4 = "\"" + String.join("\" \"", joinTest) + "\"";

        System.out.println(joinStringTest1);
        System.out.println(joinStringTest2);
        System.out.println(joinStringTest3);
        System.out.println(joinStringTest4);
    }
}
```

# 코드 결과
```
a"b"c
a" "b" "c
a""b""c
"a" "b" "c"

Process finished with exit code 0
```
