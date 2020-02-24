## Gradle 버전 5.x에서 Lombok이 작동하지 않는 이슈

Gradle 빌드시 Lombok으로 처리하던 getter, setter, log 쪽이 모두 컴파일 오류가난다.<br>
(아마도 class not found exception 에러가 발생했던 것 같다)<br>
구글 검색을 해보고 annotationProcessor, compileOnly 설정으로 해결할 수 있음을 알게되었다. <br>
~~~
 dependencies {
        annotationProcessor("org.projectlombok:lombok:${lombokVersion}")
        compileOnly("org.projectlombok:lombok:${lombokVersion}")
        implementation 'org.springframework.boot:spring-boot-starter-web'
        ...
        ...
    }
~~~

~~~
 compileOnly("org.projectlombok:lombok:${lombokVersion}")
    testCompileOnly("org.projectlombok:lombok:${lombokVersion}")
    annotationProcessor("org.projectlombok:lombok:${lombokVersion}")
    testAnnotationProcessor("org.projectlombok:lombok:${lombokVersion}")
~~~

참조: https://eblo.tistory.com/70
