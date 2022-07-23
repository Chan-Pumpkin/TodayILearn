# 프로젝트 생성

## 강의 준비

- java 11 설치 (현재 자바 17,18까지 나옴)
- 인텔리제이를 사용함.

## 스프링 부트 링크
![1_1](https://user-images.githubusercontent.com/62877858/180603653-3b26c6fb-c0f4-49c1-99b7-64398a428aed.png)

[Spring Initializr](https://start.spring.io/)

### Project (여기서 Project 항목은 빌드 관리 도구)

라이브러리를 땡겨오고 빌드와 라이프사이클까지 관리해주는 툴

요즘은 Gradle로 하는 추세임.

- Maven Project
- Gradle Project

### Spring Boot (version)

SNAPSHOT은 만들고 있는 것

M1 정식 릴리즈가 아님

괄호가 없는게 정식 릴리즈인듯

### Project Metadata

Group : 보통 기업 이름 혹은 그룹 이름

Artifact : 빌드 될 때의 결과물로 프로젝트 명으로 보면 됨.

### Dependencies

어떤 라이프러리를 땡겨서 쓸 것인가에 대한 것.

### GENERATE

프로젝트 생성되어서 다운받아짐

### Open 할 때,

인텔리제이에서 open할 때, build.gradle파일을 클릭해서 프로젝트로 열면 된다.
