## Race Condition이란

여러 프로세스와 스레드가 하나의 자원을 놓고 동시에 읽거나 쓰는 동작을 할 때, 데이터 접근이 어떤 순서에 따라 이루어졌는지에 따라 실행 결과 값이 달라지는 상황을 말함.

## 직면할 수 있는 문제

### Deadlock(교착 상태)

공유 자원에 대한 요구가 엉켜서 자원 관리를 잘못하여 프로세스나 스레드가 자원의 락을 획득하기 위해 무한 대기 하는 것

### Starvation (기아상태)

스레드들에게 우선 순위를 부여하여 공유 자원에 접근할 때, 우선순위가 낮은 스레드가 소외되어 자신의 차례가 돌아오지 않아 아무일도 하지 못하는 상태

## 예방할 수 있는 방법

### **Semaphore(세마포어)**

현재 공유자원에 접근할 수 있는 쓰레드, 프로세스의 수를 나타내는 값을 두어 상호배제를 달성하는 기법

### **Mutex(뮤텍스)**

- 한 쓰레드, 프로세스에 의해 소유될 수 있는 key를 기반으로 한 상호 배제 기법
- 임계구역(Critical Section)을 가진 스레드들의 Running Time이 서로 겹치지 않고 각각 단독으로 실행되도록 하는 기술

## 출처

[https://worthpreading.tistory.com/90](https://worthpreading.tistory.com/90)

[https://chelseashin.tistory.com/40](https://chelseashin.tistory.com/40)

[https://iredays.tistory.com/125](https://iredays.tistory.com/125)

[https://arainablog.tistory.com/276](https://arainablog.tistory.com/276)
