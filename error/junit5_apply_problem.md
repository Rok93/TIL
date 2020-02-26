# jUnit5 설정시에 아래와 같은 오류 발생
![image](https://user-images.githubusercontent.com/47850258/75324490-6e8b3680-58ba-11ea-954a-de6988265c98.png)

아래는 **build.gradle** 의 dependency 부분의 코드이다.

~~~
dependencies {
    compile('com.sparkjava:spark-core:2.9.0')
    compile('com.sparkjava:spark-template-handlebars:2.7.1')
    compile('ch.qos.logback:logback-classic:1.2.3')

    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.3.1'
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine:5.3.1'
    testImplementation("org.assertj:assertj-core:3.11.1")
}
~~~

분명 jUnit5 라이브러리 의존성 설정을 제대로 했는데도 실행이 안됐음 

참고: https://java.ihoney.pe.kr/525 에서 build.gradle에서 test { } 로 된 부분이 있는 것을 확인<br>
dependencies 밑에 아래와 같은 코드를 추가하니 정상적으로 테스트 코드가 실행되었다. <br>

~~~
test {
    useJUnitPlatform()
}
~~~

