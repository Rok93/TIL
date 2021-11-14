# Java 관련 내용 

> 읽어볼 내용들!!! 
> https://deveric.tistory.com/104
> https://github.com/binghe819/tech-interview/blob/master/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0/List/ArrayList.md
> https://github.com/binghe819/TIL/blob/master/JAVA/%EA%B8%B0%ED%83%80/%EC%97%B4%EA%B1%B0%ED%98%95(enum).md
> 
> Lv1 내용 관련 자료들
> https://developerfarm.wordpress.com/2012/02/03/object_calisthenics_summary/
> https://techcourse.woowahan.com/s/zmAj9jfu/ls/aGd7xPCD
> https://developerfarm.wordpress.com/2012/02/01/object_calisthenics_10/
> 


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


JVM 관련해서는 [마크의 학습로그](https://github.com/binghe819/tech-interview#jvm-gc)를 참고해보자!

<details>
<summary>Call By Value VS Call By Reference</summary>

프로그래밍 언어들은 메서드 매개변수 호출 방식에는 여러 가지가 있으며 호출 방식은 언어마다 다르게 되어있다. <br>
C++은 대표적인 Call By Reference를 사용한다. (매개변수를 넘겨주는 행위이기 때문에 Pass by Value, Pass by Reference)

Call By Value는 함수의 인자를 전달할 때 '값을 전달하는 방식'이고 Call By Reference는 '주소를 전달하는 방식'이다. <br>
결론적으로 자바는 확실하게 `Call By Value` 방식을 사용한다. 

Call By Value는 '값을 전달하는 방식'이며 다르게 말하면 `값만 전달하는 방식`이다. 
만약 함수 A에서 B로 int 변수를 전달한다고 했을 때, 넘겨받은 B에서 어떤 행동을 하던지 변수에는 변함이 없다. 

[예시]
![image](https://media.vlpt.us/images/ahnick/post/17de5a63-6c46-46f2-8dc2-b0f3952c67b6/image.png)

이렇게 method_1과 method_2의 두 함수가 존재할 때, method1은 a = 10, b = 5의 값을 넘겨주고 method2는 이 값을 다른 값으로 교체합니다. <br> 
그 이후 다시 method1에서 이 변수를 출력했을 때 어떤 변화가 생길까? 

![image](https://media.vlpt.us/images/ahnick/post/7f0ef1fd-c9cb-4b81-ac01-5c6429adb875/image.png)

method1에서 a=10, b=5 -> method2에서 a=20, b=10으로 바꿨지만 결과는 a=10,b=5로 처음과 같다! 
이게 바로 자바가 Call By Value 방식을 사용하기 때문에 나오는 결과이다. 

> 그렇다면 자바의 기본 타입을 제외한 참조 타입에서는 어떤 결과가 나올까?

![image](https://media.vlpt.us/images/ahnick/post/fbc0940e-1b6c-463a-96ec-bb7eff839149/image.png)

결과
![image](https://media.vlpt.us/images/ahnick/post/b1366ede-070d-45cc-86a9-e243613f1281/image.png)

자바의 대표적인 참조 타입인 String을 사용했을 때 int로 테스트한 것과 동일한 결과가 나온다. 

> String이 아닌 객체를 가지고 테스트를 해보면 어떻게 될까?

![image](https://media.vlpt.us/images/ahnick/post/556ea6a2-6a5d-4307-beeb-393a0a986e9d/image.png)

위의 테스트를 조금 바꿔서, 이번엔 새롭게 선언한 클래스를 가지고 테스트를 해보겠습니다. <br> 
예상대로라면 아까와 같이 method1의 person은 field 값이 변하지 않아야한다! 

![image](https://media.vlpt.us/images/ahnick/post/c188fe41-8e82-477d-a7d5-1a7a889a65c2/image.png) 
앗...? 아까와 다른 결과가 나왔다. 

### Reference Type의 동작 원리를 살펴보자... 
자바에서는 Call By Value 방식을 사용한다고 했다. 그렇다면 int를 전달할 때와 Person을 전달할 때는 어떤 차이가 있었던걸까요? 

![image](https://media.vlpt.us/images/ahnick/post/00259c6c-3f5b-4d3f-8db9-2e33fc45a152/image.png)

자바에서는 Call By Value 방식을 수행할 때, 값을 넘겨받은 메서드에서 **값을 복사하여 새로운 지역 변수에 저장한다**. <br>
이 때, Method2는 `Method1의 변수를 사용한 것이 아니라, 자신이 새롭게 생성한 지역 변수`에 Method1의 `변수 이름과 변수 값을 복사하여 사용`하는 것이다. 

이 때문에 아무리 Method2에서 A와 B의 값을 바꾸어도 Method1의 A,B에게 영향을 끼칠 수 없습니다. <br> 
이 A, B는 이름만 같을 뿐 다른 주소를 가지는 별개의 친구들이기 때문이다. (만약 자바가 Call By Reference 방식을 사용한다면 A와 B에 영향을 끼칠 수 있다, 왜냐하면 A와 B는 서로 공유하는 변수이기 때문이다)

이렇게 기본 타입에서의 작동 방식은 명확해졌다. 그럼 좀전의 (Person) 객체에서는 왜 그런 결과가 나왔을까? 

![image](https://media.vlpt.us/images/ahnick/post/160db5c4-0b20-4536-88ea-119d46fe1b01/image.png)

참조 타입은 위와 같은 방식을 사용하기 때문이다. <br>
`애초에 '참조 타입'인 이유가 Heap Memory 영역에 생성된 객체의 주소값을 참조하기 때문에` '참조타입'이라고 불린다. <br>
따라서 Method1에서 Method2로 넘겨준건 Person의 주소값이고, Method1이 가지고 있는 주소값과 동일한 주소값을 가지고 이 객체의 상태를 수정하면... 

![image](https://media.vlpt.us/images/ahnick/post/e96c41f3-caac-4fa1-9235-fc0521f3362f/image.png)

결과
![image](https://media.vlpt.us/images/ahnick/post/b0a79183-1dde-457e-bbb2-919da82ca64c/image.png)

당연히 두 Person은 동일한 주소를 참조하기 때문에 이러한 결과가 나온다. 



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
