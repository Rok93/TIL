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
