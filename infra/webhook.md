# Web Hook

### 웹훅은 아래의 그림으로 간략히 설명할 수 있다!

<img src="https://miro.medium.com/max/1400/1*WStVIykpS0sKLD2IFOxJUA.png" width="60%">

### Polling 방식 
* 우리의 애플리케이션이 엔드포인트에 이벤트가 발생했는지 주기적으로 요청을 보내는 방식
* 비효율적이다

### Webhook 방식
* 엔드포인트에서 발생한 이벤트가 우리의 애플리케이션에 수신되는 형태
* 우리의 애플리케이션은 그 이벤트에 대한 처리를 한 다음에 다시 엔드포인트에 응답을 보낸다


[위키피디아아에서는 webhook을 아래와 같이 설명](https://en.wikipedia.org/wiki/Webhook)하고있다.
> A webhook in web development is a method of augmenting or altering the behavior of a web page or web application with custom callbacks. These callbacks may be maintained, modified, and managed by third-party users and developers who may not necessarily be affiliated with the originating website or application. The term "webhook" was coined by Jeff Lindsay in 2007 from the computer programming term hook.[1]

### (일부만...) 번역 
> 웹훅은 웹페이지 또는 웹앱애서 발생하는 특정 행동(이벤트)들을 커스텀 Callback으로 변환해주는 방법이다.
조금 더 풀어서 설명하자면, 일반적인 API(Polling)는 클라이언트가 서버를 호출하는 방식이다. 하지만 웹훅의 경우 서버에서 특정 이벤트가 발생했을 때 클라이언트를 호출하는 방식이며 "역방향 API"라고도 부른다.

여기서 `callback URL`은 `서버측에서 이벤트가 발생했을 때 클라이언트의 어느 URL로 데이터를 보낼지 정해놓은 주소`라고 생각하면 된다. 간략히 말해 `webhook`은 `이벤트 핸들러`이고 `webhook endpoint`는 이벤트의 목적지라고 보면 된다. 

## Webhook을 사용하는 이유 

(위에서 이미 요약해두었지만 다시한번 언급하면...)
지속적으로 수신 되었는지에 대한 여부를 확인하는 Polling과는 달리 웹훅을 이용하면 서버 측에서 이벤트가 발생할 경우에 클라이언트로 HTTP POST를 하므로 클라이언트에서는 해당 이벤트를 핸들러를 통해 처리만 해주면 된다. 
즉, 절대적인 API 요청 횟수가 적어지기 때문에 웹훅을 사용할 경우 보다 `효율적이게 된다`.

## Webhook 구현 시 유의해야할 점 
만약 웹앱이 중단되었을 경우 웹훅으로부터 오는 데이터는 유실될 가능성이 존재한다. 
또, 웹훅으로 부터 오는 요청에 대하여 처리를 완료하였으나 response를 제대로 보내지 못했을 경우에는 웹훅에서 response가 실패인 것을 확인하고 동일한 정보를 다시 보낼 가능성이 있다. 
이러한 문제점이 생길 수 있는 가능성에 대해 잘 이해하고 생각해보면서 상황에 맞는 예외처리를 해주어야한다. 

## 사용 예시 
* Jenkins가 깃헙의 특정 브렌치에 push가 된 것을 감지하여 CI/CD를 진행할 때. 깃헙에서 webhook을 발생시키고 Jenkins는 이 webhook을 수신 
* 슬랙 및 디스코드도 위와 유사 
* 이 외에도 `지라` 같은 협업 툴들도 가능하지 않을까?  


### 참고자료 
[웹훅이란?](https://simsimjae.medium.com/%EC%9B%B9%ED%9B%85%EC%9D%B4%EB%9E%80-e41cf1ba92f0)
[[Webhook]웹훅이란?](https://leffept.tistory.com/329) 
[웹훅 (webhook)이 뭐야?, HTTP/2.0 Webpush 스펙 요약](https://lee95292.github.io/http/2020/05/10/principleOfwebhook.html)  <- 참고만 했음
