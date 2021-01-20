---
# 목차 

1. 인텔리제이란?

2. 인텔리제이의 특징

3. 이클립스와의 비교 

4. 인텔리제이의 기능 

5. 프로젝트 설정 

---

---
# 인텔리제이란? 

* IntelliJ IDEA는 JetBrains사에서 제작한 상용 **자바 통합 개발 환경** 이다. 줄여서 **IntelliJ** or **IDEA** 로도 불린다.  

* 안드로이드 스튜디오 - 구글과의 협력을 통해 IntelliJ IDEA를 안드로이드 개발 전용 IDE로 만든 것  

* Jetbrains는 Kotlin을 만든 회사로도 유명하다. 

## 권장사양 

![image](https://user-images.githubusercontent.com/47850258/94012190-690bb580-fde3-11ea-8979-9884b973332f.png)

---
# 인텔리제이 버전

* IntelliJ IDEA는 Ultimate Edition으로 불리는 상용버전과 Community Edition으로 불리는 무료 버전이 존재한다.

* 상용버전은 30일간 무료로 사용해 보고 계속 사용할지 여부를 결정할 수 있다. 

* 무료 버전은 상용버전에 비하여 일부 기능이 제약된다.

## 두 버전의 차이점 
[Ulitmate version vs Community version](https://www.jetbrains.com/ko-kr/idea/features/editions_comparison_matrix.html)


---
# 인텔리제이 가격책정 (월)
![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FVSWeK%2FbtqDWsLK7i8%2FnzpOAE2MsIC7wSToo6gVYk%2Fimg.png)
![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fc3Od4D%2FbtqDWVmAZtg%2FQ5pax8UNNGK2KuHcFsIDGk%2Fimg.png) 

1인 기준 월 18,000원 정도의 비용을 지불해야 상용버전을 사용할 수 있다. 개인이 사용하기에 부담스러울 수 있는 금액이지만, 
한번 사용해보면 그 편리함에 매료되어서, 개인이 돈을 지불하고 사용하는 사례도 꽤 자주 볼 수 있습니다. 


---
# 인텔리제이의 특징 

## 스마트 완성 

![image](https://www.jetbrains.com/idea/features/screenshots/16/why_smart_completion.png)

* Mac 기준: ⌃ + ⇧ + Space 

* Window 기준: Ctrl + Shift + Space


---
# 인텔리제이의 특징 

## 정적 멤버 완성
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_static_members_completion.png)

* 정적 메소드와 상수를 간편하게 사용할 수 있습니다. 

* 입력 내용에 맞는 심볼 목록이 제공되고 필요한 import 문이 자동으로 추가됩니다.


---
# 인텔리제이의 특징 

## 데이터 흐름 분석 
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_data_flow.png)

* IntelliJ IDEA는 데이터 흐름을 분석하여 가능한 런타임 심볼 유형을 추측하고 해당 정보에 따라 선택지를 개선해 클래스의 형 변환을 자동으로 추가합니다.


---
# 인텔리제이의 특징 
## 교차언어 리팩토링 
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_rename.png)

* IntelliJ IDEA는 심볼의 사용 위치를 모두 파악하기 때문에 매우 효과적이며 완벽한 리팩토링을 제공합니다.


---
# 인텔리제이의 특징 
## 중복 탐지
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_duplicates.png)

* 중복된 코드 부분을 바로 찾아냅니다. 

* 변수나 상수, 메소드만 추출하려고 하는 경우에 작업 중인 코드를 대체할 수 있는 유사한 코드가 있음을 알려줍니다. 



---
# 인텔리제이의 특징 

## 검사 및 빠른 수정

![image](https://www.jetbrains.com/idea/features/screenshots/16/why_unobtrusive.png)

* IntelliJ IDEA에서 사용자의 실수를 탐지할 때마다 에디터에 작은 전구를 표시합니다. 

* 전구를 클릭하거나 ⌥Enter(Window의 경우 Alt + Enter)를 누르면 오류 수정을 위해 선택할 수 있는 액션 목록이 열립니다.


---
# 인텔리제이의 특징 
## 인라인 디버거
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_inline_debugger.png)

* 코드를 디버그할 때 소스 코드에서 변수가 사용된 위치 바로 옆에 변숫값이 표시됩니다.

* 변숫값이 변경되면 IntelliJ IDEA에서 해당 변수를 다른 색상으로 강조 표시하므로 코드의 상태 변화를 손쉽게 파악할 수 있습니다.



---
# 인텔리제이의 특징 
## 빌드 도구 

![image](https://www.jetbrains.com/idea/features/screenshots/16/why_gradle.png)

* Maven, Gradle, Ant, Gant, SBT, NPM, Webpack, Grunt, Gulp 및 기타 빌드 도구를 지원합니다. 

* 원활하게 통합된 이 도구들은 자동 컴파일, 패키징, 테스트 실행, 배포 등의 작업에 도움이 됩니다.


---
# 인텔리제이의 특징 
## 테스트 러너 및 커버리지
![image](https://www.jetbrains.com/idea/features/screenshots/16/why_test_runner.png)

* IntelliJ IDEA를 사용하면 유닛 테스트를 간편하게 수행할 수 있습니다. 

* IntelliJ IDEA에는 JUnit, TestNG, Spock, Cucumber, ScalaTest, spec2, Karma 등 주요 테스트 프레임워크에 사용할 수 있는 테스트 러너 및 커버리지 도구가 포함되어 있습니다.


---
# 인텔리제이의 특징 

## 그 외..
* 에디터 중심의 환경 

* 모든 작업을 단축키로 실행 

* 인체 공학적 사용자 인터페이스

* 버전 관리 등등


[JetBrain이 소개하는 InelliJ 특징](https://www.jetbrains.com/ko-kr/idea/features/)

---
# vs Eclipse 
* eclipse는 여러 프로젝트들을 관리하는 Workspace가 존재한다 

* IntelliJ는 각각의 프로젝트당 하나의 IntelliJ 윈도우를 실행하는 것이 일반적인 사용방법이다. 

* 즉 Workspace 개념이 없다


![image](https://user-images.githubusercontent.com/47850258/94774510-032db800-03f9-11eb-8a82-d5ffde46fd11.png)



---
## 편리한 단축키 (General) 

mac | window | 기능 
-|-|-
``⌘+0 ~ 9`` | ``Alt+0 ~ 9`` | 각 단축키에 해당하는 도구창을 열고 닫는다.
``⌘+,`` | ``Ctrl+Alt+S `` | 설정(Preferences) 창을 연다. 
``⌘+;`` | ``Ctrl+Alt+Shift+S`` | 프로젝트 구조를 확인 및 변경할 수 있는 창을 연다.
``⌘+⇧+A`` | ``mac과 동일 `` | 액션을 검색 및 실행. 설정변경 및 단축키를 모를 때 유용한 기능 
``Double⇧`` | ``mac과 동일 `` | 키워드에 관련된 가능한 모든 것을 검색해 보여준다.


---
## 편리한 단축키 (Editing)

mac | window | 기능 
-|-|-
``⌘+B`` | ``Ctrl+B`` | 해당 코드의 선언부로 이동 
``⌘+⌥+B`` | ``Ctrl+Shift+B`` | 해당 코드의 구현부로 이동
``⌘+D`` | ``Ctrl+D`` | 라인 복제 
``⌘+⌫`` | ``Ctrl+Y`` | 라인 삭제 
``⌘+/`` | ``Ctrl+/`` | 라인단위로 주석처리
``⌘+N`` ``⌃+↩︎`` | ``Alt+Insert`` | 코드를 생성 (Getter/Setter, 오버라이드 etc..)
``⌥+↩︎`` |``Alt+↩︎``| Quick Fix 제안
``⌘+⇧+/`` | ``Ctrl+Shift+/`` | 블록단위로 주석처리
``⌘+⌥+L``|``Ctrl+Alt+L`` | 해당 프로젝트의 서식에 맞도록 코드정렬


---
## 편리한 단축키 (Compile And Run)
mac | window | 기능 
-|-|-
``⌘+F9``|``Ctrl+F9``| 프로젝트 빌드(Make Project)
``⌘+Shift+R``|``Ctrl+Shift+F10``| 최초실행(Run)
``⌘+R``|``Shift+F10``| 실행 (Run)
``⌘+D``|``Shift+F9``| 디버그 (Debug)

---
## 편리한 단축키 (Refactoring)
mac | window | 기능 
-|-|-
``⌃+⌥+O``|``Ctrl+Alt+O``| Optimize Imports (import 자동 정리) 
``⌃+⌥+키``|``Ctrl+Alt+키``| Refactor (키: **M**ethod, **C**onstant, **F**eild, **V**ariable, **P**arameter, **T**his로 모든 리팩토링 항목 조회 가능)
``⇧+F5`` | ``Shift+F5`` | 복사 (Copy) 
``⇧+F6`` | ``Shift+F6`` | 이름 변경(Rename)
``⌘+F6`` | ``Ctrl+F6`` | 접근제어자, 반환타입, 이름 등 주요정보를 변경


---
## 'Key Promoter X' Plugin 소개 

> Navagator(shift 2번) → 'plugins' 검색, 실행 → 'Marketplace' 선택 → 'Key Promoter X' 설치 & Enable 설정

![image](https://user-images.githubusercontent.com/47850258/95120735-f3abc780-0788-11eb-9c64-12862bcb5ca4.png)
![image](https://user-images.githubusercontent.com/47850258/95121314-d88d8780-0789-11eb-86a3-3156bdbd5b97.png)

사용하는 기능의 단축키를 하단의 초록색 창으로 보여준다


---
## 편리한 자동완성 기능 

### ``psvm`` : main 함수 
![image](https://user-images.githubusercontent.com/47850258/94777595-ac2ae180-03fe-11eb-954d-5a7d490eccae.png)

![image](https://user-images.githubusercontent.com/47850258/95131324-d1ba4100-0798-11eb-8e06-f7108b324ca2.png)

---
## 편리한 자동완성 기능 

### ``(조건식).if`` : if 조건문 
![image](https://user-images.githubusercontent.com/47850258/95131713-818fae80-0799-11eb-90f9-70e8fd5755d0.png)

![image](https://user-images.githubusercontent.com/47850258/95131748-98360580-0799-11eb-88a7-0026b80ca28a.png)

---
## 편리한 자동완성 기능 

### ``fori`` : for문 
![image](https://user-images.githubusercontent.com/47850258/95154432-c41eae80-07cc-11eb-894c-6ede5f9cd9c4.png)

![image](https://user-images.githubusercontent.com/47850258/95154456-d26cca80-07cc-11eb-8bdd-566e831cfec9.png)


---
## 편리한 자동완성 기능 

### ``prsf`` : (private) 상수 구조
![image](https://user-images.githubusercontent.com/47850258/95132515-dc75d580-079a-11eb-86a2-6686e16faa9d.png)

![image](https://user-images.githubusercontent.com/47850258/95132027-0e3a6c80-079a-11eb-8278-fa29ab17970e.png)


---
## 편리한 자동완성 기능 

### ``psf``: (public) 상수 구조
![image](https://user-images.githubusercontent.com/47850258/95132126-39bd5700-079a-11eb-9c43-68e1c4743da6.png)

![image](https://user-images.githubusercontent.com/47850258/95132189-52c60800-079a-11eb-8c23-b3f50e1ff154.png)

---
# 프로젝트 설정 
### 1. New Project 클릭

![image](https://user-images.githubusercontent.com/47850258/95132842-5e65fe80-079b-11eb-821d-6478fccbdca2.png)


---
# 프로젝트 설정 
### 2. Gradle 프로젝트 선택

![image](https://user-images.githubusercontent.com/47850258/95133274-067bc780-079c-11eb-8325-76c0776acd48.png)


---
# 프로젝트 설정 
### 3. 프로젝트명, GroupId 설정 

![image](https://user-images.githubusercontent.com/47850258/95133685-aa657300-079c-11eb-8e4e-bc02e9e8fc64.png)



---
# 프로젝트 설정 

### 4. Gradle 프로젝트 생성

![image](https://user-images.githubusercontent.com/47850258/95134040-2b246f00-079d-11eb-9157-c398dfd4b47f.png)



---
# 프로젝트 설정 

### 5. 프로젝트 빌드 설정 

![image](https://user-images.githubusercontent.com/47850258/95134112-455e4d00-079d-11eb-9eed-769efdeb79f8.png)


---
# 프로젝트 설정 

### 6. 테스트 라이브러리 의존성 추가

![image](https://user-images.githubusercontent.com/47850258/95135451-61fb8480-079f-11eb-8725-bc984a6906be.png)

테스트 라이브러리 의존성 추가 후 우측 상단의 **gradle 아이콘 클릭**


---
# 프로젝트 설정 

### 7. 프로젝트 설정 

![image](https://user-images.githubusercontent.com/47850258/95135048-d3870300-079e-11eb-908b-b74300d156e4.png)


---
# 프로젝트 설정 

### 8. 프로젝트 테스트 

![image](https://user-images.githubusercontent.com/47850258/95153358-3772f100-07ca-11eb-8b65-41e08155226b.png)


---
# 프로젝트 설정 

### 9. JUnit test

![image](https://user-images.githubusercontent.com/47850258/95153693-02b36980-07cb-11eb-8ea1-a761e597c11f.png)
![image](https://user-images.githubusercontent.com/47850258/95153576-b405cf80-07ca-11eb-934a-906d5335dd99.png)

—
# 프로젝트 설정

### 9. JUnit test

![image](https://user-images.githubusercontent.com/47850258/95153984-b87eb800-07cb-11eb-9242-bd9d4477ab3a.png)![image](https://user-images.githubusercontent.com/47850258/95154036-da783a80-07cb-11eb-9cbd-c4285b07860b.png)

테스트코드를 실행했을 때, 아래에 초록색 바가 나온다면 설정이 완료된 것이다.

—
# Thanks You!
