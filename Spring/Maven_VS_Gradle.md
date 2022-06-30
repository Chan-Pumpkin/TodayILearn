## 빌드 도구란?

소스코드 파일들을 실행할 수 있도록 변환하는 일련의 과정을 자동화해주는 도구라고 생각하면 된다.

## 빌드 도구 역사

- Make(1세대)
- Ant(2세대)
- Maven(3세대)
- Gradle

## Gradle vs Maven

### 1. 성능
![Untitled](https://user-images.githubusercontent.com/62877858/176635702-bf904c95-8e6d-403e-930a-cd1362e0fb6e.png)

Gradle은 거의 모든 시나리오에서 최소 2배 빠름.

### 2. 종속성 관리

두 빌드 시스템 모두 구성 가능한 리포지토리에서 종속성을 해결하는 기본 기능을 제공함. 둘 다 종속성을 로컬로 캐시하고 병렬로 다운로드 할 수 있음.

- 종속성 충돌 해결

Maven : 선언 순서의 영향을 받는 최단 경로로 작동함.

Gradle : 그래프에서 발견된 종속성의 가장 높은 버전을 선택하여 전체 충돌 해결을 수행함.

## Gradle이 Maven보다 빠른 3가지 이유

### Incrementality

Gradle은 작업의 입출력을 추적, 필요한 것만 실행, 가능한 변경된 파일만 처리하여 작업을 방지한다.

### Build Cache

컴퓨터 사이를 포함하여 동일한 입력으로 다른 Gradel 빌드의 빌츠 출력을 재사용함.

### Gradle Daemon

빌드 정보를 메모리에 뜨거운 상태로 유지하는 긴 수명 프로세스

## 참고

[https://gradle.org/maven-vs-gradle/](https://gradle.org/maven-vs-gradle/)

[https://gradle.org/gradle-vs-maven-performance/](https://gradle.org/gradle-vs-maven-performance/)
