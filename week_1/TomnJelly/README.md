# Week 1 과제

24.09.16 ~ 24.09.20

---

## JVM이란 무엇인가

Java Virtual Machine의 약자로 자바를 실행하기 위한 가상 기계

![JVM](/assets/0924_1.png)

---

## JVM 구성 요소

![JVM 구성요소](/assets/0924_2.png)

1.  Class Loader - 클래스 로더
    클래스 로더는 JVM 내로 클래스 파일을 동적으로 로드하고,
    링크를 통해 JVM의 메모리 영역인 Runtime Data Area에 배치하는 역할을 한다
    클래스 파일의 로딩 순서는 ( Loading -> Linking -> Initialization ) 이다

    ![클래스 파일의 로딩 순서](/assets/0924_3.png)

2.  Runtime Data Area - 런타임 데이터 영역
    위 단계에서 링크를 통해 넘어온 데이터를 적재하는 영역이다
    종류는 그림처럼 나눌 수 있다.

3.  Execution Engine - 실행 엔진
    런타임 데이터 영억에 배치된 바이트 코드를 명령어 단위로 읽어서 실행하는 영역
    중간 레벨로 컴파일된 바이트 코드를 실제로 JVM 내부에서 기계가 실행할 수 있는 형태로 변경
    구성요소는 인터프리터, JIT 컴파일러, 가비지 콜렉터 세가지이다.

4.  Native Method Interface - 네이티브 메소드 인터페이스
    자바가 다른 언어로 만들어진 어플리케이션과 상호 작용할 수 있는 인터페이스를 제공하는 프로그램
    JNI가 사용되면 native mathod stack에 바이트 코드가 적재된다.

5.  Native Method Library - 네이티브 메소드 라이브러리
    C, C++로 작성된 라이브러리를 칭한다.
    만일 헤더가 필요하면 JNI는 이 라이브러리를 로딩해 실행한다.

---

## 컴파일 하는 방법

src 파일 안에 있는 HelloWorld.java 파일은
Java Compiler에 의해 .java 파일을 .class 라는 Java Byte Code로 변환하는 과정이다
Java Compiler는 JDK를 설치하면 JDK의 bin 폴더 내부에 javac.exe라는 실행파일로 존재한다
-> 해당 디렉토리로 이동하여 javac 명령어를 실행하면 된다

---
## 실행하는 방법

java 명령어를 사용하여 .class 파일(JVM)을 실행할 수 있다

![실행결과](/assets/0924_5.png)

---
## 바이트코드란 무엇인가

자바 바이트 코드(Java bytecode)는 JVM이 이해할 수 있는 언어로 변환된 자바 소스코드를 의미한다

바이트 코드는 다시 실시간 번역기 또는 JIT 컴파일러에 의해 바이너리 코드(이진 코드)로 변환된다

---

## JIT 컴파일러란 무엇이며 어떻게 동작하는지

JIT 컴파일(just-in-time compliation) 또는 동적 번역(dynamic translation) 이라고 한다.

JIT 컴파일러는 프로그램을 실제 실행하는 시점에 기계어로 번역하는 컴파일러이다.

---

## JDK와 JRE의 차이

JDK | Java Development Kit (자바 개발 키트)

Java 를 사용하기 위해 필요한 모든 기능을 갖춘 Java용 SDK (Software Development Kit)이다
JDK 는 JRE를 포함하고 있다
JRE에 있는 모든 것 뿐만 아니라 컴파일러(javac)와 jdb, javadoc 과 같은 도구도 있다
-> JDK는 프로그램을 생성, 실행, 컴파일할 수 있다

JRE | Java Runtime Environment (자바 런타임 환경)

JVM + 자바 클래스 라이브러리(Java Class Library) 등으로 구성되어 있다
컴파일 된 Java 프로그램을 실행하는데 필요한 패키지이다
