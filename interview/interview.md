# Java 관련 내용 

<!--
양식
<details>
<summary>제목</summary>
  내용
</details>

-->

<details>
<summary>자바란...?</summary>

* 썬 마이크로시스템즈에서 `제임스 고슬링`과 다른 연구원들이 개발한 `객체 지향 프로그래밍 언어`다. 
* 특징 
    * JVM위에서 동작하기 때문에 이식성이 높음
      * 자바가상머신(JVM)에서 동작하기 때문에 운영체제의 종류에 상관없이 작동
    * GC(Garbage Collector)라는 프로세스를 통해 자동으로 메모리 관리를 수행 
      * 사용하지 않는 객체는 자동으로 메모리에서 체크하고 반환
    * 분산 네트워크 기술을 지원
      * TCP/IP 라이브러리가 기본적으로 포함되어있고, HTTP 프로토콜을 지원
    * 멀티 스레딩을 지원한다
      * 동일한 쓰레드를 동시에 수행할 수 있음.
      * 사용자 인터페이스 쓰레드와 장시간 계산이 필요한 쓰레드가 동시에 필요할 때 효과적이다.
    * 동적 로딩 지원
      * 프로그램 실행시 모든 클래스가 로딩되지 않고, 필요한 시점에 클래스를 로딩하여 사용할 수 있음
      * 애플리케이션의 변경사항도 비교적 적은 작업만으로 처리할 수 있음

</details>

<details>
<summary>JVM이란?</summary>

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FVRZ6k%2FbtqDcw8qekS%2Fvi32KUQkZ19yVZwh9xaze1%2Fimg.png)

* OS는 Java 프로그램을 바로 실행할 수 없는데, 그 이유는 자바 프로그램은 완전한 기계어가 아닌, 중간 단계의 바이트 코드이기 때문이다.
  * 이것을 해석하고 실행할 수 있는 가상의 운영체제가 자바 가상 기계(JVM: Java Virtual Machine)이다. 
  * JVM은 실 운영체제를 대신해서 자바 프로그램을 실행하는 가상의 운영체제 역할을 함.
  * 따라서 개발자는 운영체제와 상관없이 자바 프로그램을 개발할 수 있다.
  * 바이트 코드는 모든 JVM에서 동일한 실행 결과를 보장하지만, JVM은 운영체제에 종속적이다. 
    * 자바 프로그램을 운영체제가 이해하는 기계어로 번역해서 실행해야 하므로 JVM은 운영체제에 맞게 설치되어야한다.
    * ![image](https://blog.kakaocdn.net/dn/bitjuO/btq05p51dnQ/aRqlqfWFaTNS8Gee17Hdmk/img.png)
* Java Virtual Machine의 약자이다. 
* Java는 OS에 독립적인 특징을 가지는데, 그 이유가 JVM상에서 실행되기 때문이다.

</details>



<details>
<summary>Java 동작원리</summary>

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fb8Ggxw%2FbtqDbFdEZdY%2FHo1kpzsNqFz3Pbpy8OfiFk%2Fimg.png)

1. 작성한 자바소스(.java)를 `자바 컴파일러`를 통해 자바 바이트 코드(.class)로 `컴파일`한다.
   * 자바 바이트 코드: JVM이 이해할 수 있는 코드로 아직 컴퓨터는 읽을 수 없는 반기계어이다.
   * 자바 바이트 코드의 각 명령어는 1바이트 크기의 Opcode와 추가 피연산자로 이뤄져있다.
2. 컴파일된 바이트 코드를 JVM의 클래스 로더에게 전달한다. 
   1. 로드: 클래스 파일을 가져와서 JVM의 메모리에 로드
   2. 검증: 자바 언어 명세(Java Language Specification) 및 JVM 명세에 명시된 대로 구성되어 있는지 검사한다.
   3. 준비: 클래스가 필요로하는 메모리를 할당. (필드, 메서드, 인터페이스 etc)
   4. 분석: 클래스의 상수 풀 내 모든 심볼릭 레퍼런스를 다이렉트 레퍼런스로 변경
   5. 초기화: 클래스 변수들을 적절한 값으로 초기화 (static 필드)
3. JVM의 클래스 로더는 `동적 로딩`(Dynamic Loading)을 통해 필요한 클래스들을 로딩 및 링크하여 런타임 데이터 영역, 즉 JVM의 메모리에 올린다.
4. 실행 엔진(Execution Engine)은 JVM 메모리에 올라온 바이트 코드들을 명령어 단위로 하나씩 가져와서 실행한다. 이때, 실행엔진은 2가지 방식으로 동작할 수 있다. 
   1. 자바 인터프리터: 바이트 코드 명령어를 하나씩 읽어서 해석하고 실행. 하나하나의 실행은 빠르나, 전체적인 실행 속도가 느리다는 단점이 있다.
   2. JIT 컴파일러(Just-In-Time Compiler): 인터프리터의 단점을 보완하기 위해 도입된 방식
      * 바이트 코드 전체를 컴파일하여 바이너리 코드로 변경하고 이후에는 해당 메서드를 더 이상 인터프리팅하지 않고, 바이너리 코드로 직접 실행
      * 하나씩 인터프리팅하여 실행하는 것이 아니라 바이트 코드 전체가 컴파일된 바이너리 코드를 실행하는 것이기 때문에 전체적인 실행속도는 인터프리팅 방식보다 빠르다.
      
</details>

<details>
<summary>JVM 메모리 구조</summary>

> JVM의 구조와 동작원리에 대해 알아본다.

* JVM의 구조
  * ![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpjywN%2FbtqSduBXLIK%2F2QEL5c2nEJXRm0cyhvwxF1%2Fimg.png) 
  * (1)Class Loader, (2)Execution Engine, (3)Garbage Collector, (4)Runtime Data Area로 총 4가지 존재
    * (1) Class Loader 
      * JVM 내로 클래스 파일을 로드하고, 링크를 통해 배치하는 작업을 수행하는 모듈, 런타임 시에 동적으로 클래스를 로드한다. 
    * (2) Execution Engine
      * 클래스 로더를 통해 JVM 내의 Runtime Data Area에 배치된 바이트 코드들을 명령어 단위로 읽어서 실행한다.
      * 최초 JVM이 나왔을 당시에는 인터프리터 방식이었기 때문에 속도가 느리다는 단점이 있었으나 JIT 컴파일러 방식을 통해 이 점을 보완.
        * `JIT 컴파일러`는 바이트 코드를 어셈블러 같은 네이티크 코드로 바꿈으로써 실행이 빠르지만 역시 변환하는데 비용이 발생한다. 
        * 이 같은 이유로 JVM은 모든 코드를 JIT 컴파일러 방식으로 실행하지 않고, 인터프리터 방식을 사용하다가 일정한 기준이 넘어가면 JIT 컴파일러 방식으로 실행
    * (3) Garbage Collector
      * GC는 힙 메모리 영역에 생성된 객체들 중에서 참조되지 않은 객체들을 탐색 후 제거하는 역할을 한다. 
      * 이때, GC가 역할을 하는 시간은 언제인지 정확히 알 수 없다. 
    * (4) Runtime Data Area
      * JVM의 메모리 영역으로 자바 애플리케이션을 실행할 때, 사용되는 데이터들을 적재하는 영역이다. 
      * 이 영역은 크게 Method Area, Heap Area, Stack Area, PC Register, Native Method Stack로 나뉨 (위의 JVM 구조 사진 참고!)
      * [메모리 영역]
        1. Method Area
           * 모든 쓰레드가 공유하는 메모리 영역이다. 메서드 영역은 클래스, 인터페이스, 메서드 필드, Static 변수 등의 바이트 코드를 보관 
        2. Heap Area
           * 모든 쓰레드가 공유하며, `new 키워드로 생성된 객체`와 `배열`이 생성되는 영역이다. 
           * 또한, 메서드 영역에 로드된 클래스만 생성이 가능하고 GC가 참조되지 않는 메모리를 확인하고 제거하는 영역 
        3. Stack Area
           * ![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FulBPu%2FbtqSmAVJhzs%2Ft5uaU3DyAmRUbNKnu10bak%2Fimg.png)
           * 메서드 호출 시마다 각각의 `스택 프레임`(그 메서드만을 위한 공간)을 생성한다. 
           * 그리고 메서드 안에서 사용되는 값들을 저장하고, 호출된 메서드의 매개변수, 지역변수, 리턴 값 및 연산 시 일어나느 값들을 임시로 저장
           * 마지막으로 메서드 수행이 끝나면 프레임별로 삭제
        4. PC Register
           * 쓰레드가 시작될 때 생성되며, 생성될 때마다 생성되는 공간으로 쓰레드마다 하나씩 존재한다.
           * 쓰레드가 어떤 부분을 무슨 명령으로 실행해야할 지에 대한 기록을 하는 부분으로 현재 수행중인 JVM 명령의 주소를 갖는다. 
        5. Native Method Stack
           * 자바 외 언어로 작성된 네이티브 코드를 위한 메모리 영역이다. 
           
> 추가 학습할 내용들: 다음에는 힙은 또 몇 가지의 영역으로 나뉘는데... 더 자세히 알아보고 가비지 컬렉터는 또 어떻게 동작을 하는지에 대해서도 알아보자! 

</details>

<details>
<summary>제목</summary>
내용
</details>

<details>
<summary>함수형 프로그래밍이란?</summary>
  * 관심사의 분리
  * '작업을 어떻게 수행할 것인지, How에 집중' <br>
  * 구체적인 작업 방식은 라이브러리가 결정, `무엇(What)`을 수행할 것인지에 집중  <br>  
  * side-effect가 발생하지 않는다 <br> 
</details>

<details>
<summary>함수란?</summary>
  * 같은 인수값으로 함수를 호출했을 때, `항상 같은 값을 반환`한다. <br>
  * 함수나 메서드는 지역 변수만을 변경해야 함수형이라 할 수 있다. <br>
  * 그리고 함수나 메서드에서 참조하는 객체가 있다면 그 객체는 `불객체`여야 한다. <br> 
  * 메서드 내에서 생성한 객체의 필드는 갱신할 수 있으나, 새로 생성한 객체의 필드 갱신이 외부에 노출되지 않아야 하고 다음에 메서드를 다시 호출한 결과에 영향을 미치지 않아야 함 <br>
  * 함수나 메서드가 어떤 예외도 일으키지 않아야 한다. 
</details>

<details>
<summary>함수형 프로그래밍의 장점은?</summary>
  * 멀티코어와 동시성 제어 <br> 
  
  
</details>


<details>
<summary>ArrayList</summary>
내용
</details>


<details>
<summary>LinkedList</summary>
  내용
</details>
