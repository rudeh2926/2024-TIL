# JVM이란?

---

Java Virtual Machine의 줄인 것으로 직역하면 자바 실행을 위한 가상 기계라고 할 수 있다

![Untitled](https://github.com/rudeh2926/2024-TIL/blob/main/JAVA/JVM%EC%9D%B4%EB%9E%80%3F/JVM%EC%9D%B4%EB%9E%80%20e1f32cbdcbc24cae91561c8424f8b40b/Untitled.png)

일반 애플리케이션의 코드는 OS만 거치고 하드웨어로 전달되는데 비해 Java애플리케이션은 JVM을 한 번 더 거치기 때문에, 그리고 하드웨어에 맞게 완전히 컴파일된 상태가 아니고 실행 시에 해석되기 때문에 속도가 느리다는 단점을 가지고 있다

위 그림에서 볼 수 있듯이 **Java 애플리케이션은 JVM하고만 상호작용**을 하기 때문에 OS와 하드웨어에 독립적으로 다른 OS에서도 프로그램의 변경없이 실행이 가능한 것이다. 단, **JVM은 OS에 종속적**이기 때문에 해당 OS에서 실행가능한 JVM이 필요하다.

![Untitled](https://github.com/rudeh2926/2024-TIL/blob/main/JAVA/JVM%EC%9D%B4%EB%9E%80%3F/JVM%EC%9D%B4%EB%9E%80%20e1f32cbdcbc24cae91561c8424f8b40b/Untitled%201.png)

이렇게 함으로써 자바의 중요한 장점 중의 하나인 **WORA**(**Write Once Run Anywhere)**가능해졌다

## 알아야 하는 이유

메모리 효율성을 위해 메모리 구조를 알아야하기 때문이다. 
**동일한 기능의 프로그램이라도 메모리 관리에 성능이 좌우된다**. 
메모리 관리가 되지 않는 경우에는 속도저하 형상이나 튕김형상 등이 일어날 수 있다. 그래서 꼭 알아야 한다

## 역할

JVM의 역할은 자바 애플리케이션을 클래스 로더를 통해 읽어 들여 자바 API와 함께 실행하는 것이다.그리고 JVM은 Java와 OS 사이에서 중개자 역할을 수행하여 Java가 OS에 종속되지 않고 
독립적으로 작동이 가능하다. 또한가장 중요한 메모리 관리, Garbage collection(가비지 컬렉션)을 수행한다.

### 특징

1. 컴파일된 바이트 코드를 기계가 이해할 수 있는 기계어로 변환
2. 스택 기반의 가상머신
3. 메모리 관리와 GC를 수행

### JVM 구조와 작동원리

![Untitled](https://github.com/rudeh2926/2024-TIL/blob/main/JAVA/JVM%EC%9D%B4%EB%9E%80%3F/JVM%EC%9D%B4%EB%9E%80%20e1f32cbdcbc24cae91561c8424f8b40b/Untitled%202.png)

1. Class Loader

<aside>
💡 **클래스 파일을 로드하고, 링크 및 초기화 작업**을 수행한다. 클래스 로더는 필요한 클래스 파일을 찾고 동적으로 로드하여 실행 시에 클래스를 사용할 수 있도록 한다. 로드된 클래스는 JVM의 메모리 영역에 저장된다.

</aside>

1. Execution Engine

<aside>
💡 **JVM이 로드한 클래스 파일을 실행하는 역할**을 담당한다. 실행 엔진은 바이트 코드를 기계어로 변환하고, 이를 실행하여 프로그램을 실행한다. 주요한 실행 엔진 구성 요소로는 인터프리터와 JIT컴파일러가 있다

</aside>

1. Runtime Data Area

<aside>
💡 **Java 프로그램의 실행과 관련된 데이터와 자원을 저장한다**. 주요한 메모리 영역으로는 메서드 영역(Method Area), 힙(Heap), 스택(Stack), PC 레지스터(Program Counter Register), 네이티브 메서드 스택(Native Method Stack)이 존재한다

</aside>

![Untitled](https://github.com/rudeh2926/2024-TIL/blob/main/JAVA/JVM%EC%9D%B4%EB%9E%80%3F/JVM%EC%9D%B4%EB%9E%80%20e1f32cbdcbc24cae91561c8424f8b40b/Untitled%203.png)

<aside>
💡 **자바는 멀티스레드 환경으로 모든 스레드는 Heep, Method Area를 공유한다**

</aside>

- Method Area
    - 클래스 정보, 상수 풀(Constant Pool), 메서드 코드 등의 정보를 저장한다.
- Heap
    - 동적으로 생성된 객체와 배열을 저장한다. 가비지 컬렉션은 힙에서 불필요한 객체를 자동으로 정리한다.
- JVM Stack
    - 메서드 호출과 관련된 데이터를 저장한다. 스레드마다 별도의 스택이 생성되며, 메서드 호출 시에는 호출된 메서드의 프레임(Frame)이 스택에 추가된다.
- PC Register
    - 현재 실행 중인 명령어의 주소를 저장한다.
- Native Method Stack
    - Java 외부에서 사용되는 네이티브 코드(C/C++)를 위한 스택을 저장한다.

## 장점, 단점

1. **JVM은 플랫폼에 독립적**이므로, 한 번 작성한 자바 프로그램은 여러 운영체제와 장치에서 실행될 수 있다.  JVM은 특정 운영체제에 종속되지 않고 **중간 계층으로서 작동**하기 때문에, 자바 프로그램은 운영체제에 구애받지 않고 이식성을 갖는다.
2. **JVM은 초기화 및 클래스 로딩 등의 작업이 필요하므로**, 프로그램의 시작 시간이 상대적으로 오래 걸릴 수 있다. 특히 작은 규모의 애플리케이션의 경우, 이러한 시작 시간이 부담이 될 수 있다.
