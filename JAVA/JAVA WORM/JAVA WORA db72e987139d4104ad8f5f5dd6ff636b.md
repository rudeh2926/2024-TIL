# JAVA WORA

---

## WORA란?

- **Write Once, Run Anyway**
- 한번 작성하면 어떠한 환경에서든 실행 가능한 프로그램

![Untitled](JAVA%20WORA%20db72e987139d4104ad8f5f5dd6ff636b/Untitled.png)

## Java 플랫폼의 특징

OS가 다른 경우 각 OS에 따라 API가 다르게 동작할 수 있음

- 자바는 WORA를 구현하기 위해, 단일한 자바 API를 제공함따라서 자바 플랫폼만 설치되어 있으면 OS가 다를지라도 자바 프로그램을 실행할 수 있음
- 플랫폼에 독립적임 (Platfrom Independent)
    - 단점
        1. 자바 플랫폼을 직접 설치해야 한다
        2. 자바 API가 특정 OS가 가지고 있는 API를 포함하지 않을 수 있음

## JAVA에서 WORA를 가능하게 하는 기술

### JRE

- 무료로 다른 기종의 컴퓨터를 대응할 수 있도록 해당 컴퓨터 운영체제에 맞는 JRE를 Java 공식 사이트에서 제공한다
- 하나의 자바소스를 실행하기 위해 OS에 맞는 **JRE를 컴퓨터에 한번만 세팅하면 된다**
- JRE는 모든 유형의 JVM에서 실행되는 단일 Java 코드 복사본을 생성한다

출처:

[https://mjmjmj98.tistory.com/116](https://mjmjmj98.tistory.com/116)

[https://aws.amazon.com/ko/what-is/java-runtime-environment/](https://aws.amazon.com/ko/what-is/java-runtime-environment/)