## 1. Build

- 소스코드 파일을 컴퓨터에서 실행할 수 있는 독립 프로그램으로 변환하는 과정 또는 결과물
- 우리가 작성한 소스코드, 프로젝트에서 쓰인 각각의 파일 및 자원등을 JVM이나 톰캣같은 WAS가 인식할 수 있는 구조로 패키징 하는 과정 및 결과물이라 할 수 있음.

## 2. Maven

- Apache Ant의 대안으로 자바용 프로젝트 관리도구로 만들어짐.
- 프로젝트의 전체적인 라이프 사이클을 관리하는 도구
- XML 문서를 통해 해당 프로젝트의 버전 정보 및 라이브러리 정보들을 통합하여 관리하는 도구

## 3. Maven 설정파일

### settings.xml

- 메이븐 빌드 툴과 관련된 설정파일

### pom(프로젝트 객체 모델)

- 메이븐을 이용하는 프로젝트의 root에 존재하는 xml 파일

### pom.xml의 구성

project

- modelVersion
- groupId
- artifactId
- name
- version

properties

- maven 내부에서 반복적으로 사용될 상수 값을 정의할 때 사용한다.

dependencies (의존성 라이브러리 정보)

- project 태그 바로 하위에 위치한다.
- 의존성 라이브러리 정보를 포함한다.
- 최소 groupId, artigfactId, version의 정보가 필요하다.
- dependencies 색션 아래 세부 'dependency'가 기술된다.

build

- project 태그 바로 하위에 위치한다.
- plugins - 빌드에서 사용할 플러그인을 의미
- 디렉토리의 구조를 하고 있다.

## 참조

[https://goddaehee.tistory.com/199](https://goddaehee.tistory.com/199)

[https://velog.io/@orol116/Maven](https://velog.io/@orol116/Maven)
