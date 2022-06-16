## 1. while 문

- 조건식이 참(true)인 동안 조건식이 거짓이 될 때까지 블럭{}내의 문장을 반복한다.

```java
while (조건식) {
			// 조건식의 연산결과가 참(true)인 동안, 반복될 문장들을 적는다.
}
```

### for문과 차이점

- for문

```java
for(int i=1; i<=10; i++){
}
```

- while문

```java
int i=1;

while(i<=5){
	i++; //증감식
}
```

### while문 주의사항

- while문의 조건식은 생략불가

### 예제

```java
while(i--!=0){
}
```

- i의 값이 0이 아닌 동안만 참이 되고, i의 값이 매 반복마다 1씩 감소하다 0이 되면 조건식은 거짓이 되어 while문을 벗어난다.

## 2. do-while문

- while문과 같지만, 조건식과 블럭의 순서를 바꿔놓은 것이다.
- 블럭{}을 먼저 수행한 후에 조건식을 평가함.
- while문은 조건식에 따라 한 번도 수행되지 않을 수가 있지만, do-while문은 최소한 한번은 수행될 것을 보장함.

```java
do{
	//조건식의 연산결과가 참일 때 수행될 문장들을 적는다.
}while(조건식); // 끝에 세미클론 
```

## 3. break문

- break문은 자신이 포함된 가장 가까운 반복문을 벗어난다.
- 주로 if문과 함께 사용된다.

## 4. continue문

- continue문은 반복문 내에서만 사용할 수 있다.
- 반복이 진행되는 도중에 continue문을 만나면 반복문의 끝으로 이동하여 다음 반복으로 넘어감
- 반복문 전체를 벗어나지 않고 다음 반복으로 계속 수행하는 점이 break문과 다르다

### 예시

```java
public class forEx3 {
    public static void main(String[] args) {
			for(int i=0; i<=10; i++){
				if (i%2==0)
					continue;
				System.out.println(i);
		}
	}
}
```

## 5. 중첩 반복문을 break문으로 완전히 벗어나려면? : 이름 붙은 반복문

- break문은 근접한 단 하나의 반복문만 벗어날 수 있다.
- 여러 개의 중첩 반복문이 있을 때에는 반복문 앞에 이름으로 지정해주고, break문과 continue문에 사용해서 중첩 반복문을 완전히 벗어날 수 있다.

```java
public class forEx4 {
    public static void main(String[] args) {
		// for문에 Loop1이라는 이름을 붙임	
		Loop1 :	for(int i=1; i<=10; i++){
				for(int j=1; j<=10; j++){
						break Loop1;    //1
						break;          //2
						continue Loop1; //3
						continue;       //4
				// 4 contnue;가 향하는 곳
			}
			// 3 continue Loop1;이 향하는 곳
			// 2 break; 가 향하는 곳
		}
		//1 break Loop1이 향하는 곳
	}
}
```
