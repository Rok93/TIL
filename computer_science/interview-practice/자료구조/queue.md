# Queue

<details>
<summary>Q. Queue는 무슨 자료구조인가요?</summary>
<div markdown="1">       

queue는 선입선출 FIFO(First In First Out)의 자료구조이다. 
시간복잡도는 `enqueue`: O(1), `dequeue`: O(1) 이다. 
활용 예시는 Cache구현, 프로세스 관리, 너비우선탐색(BFS) 등이있다. 

</div>
</details>

> TIP) 기초적인 자료구조로 면접에서 간단한 질문으로 종종 나오는 문제이다. 
> LIFO(Last In First Out)인 stack과 다르게 FIFO자료구조임을 잘 기억하고있으면 된다. 
> 또한 활용 예시들과 Circular Queue 자료구조를 잘 알고 있으면 면접에서 충분한 답을 할 수 있다. 

![img.png](../../../img/queue.png)


### FIFO 
> queue는 시간 순서상 먼저 집어 넣은 데이터가 먼저 나오는 선입선출 FIFO(First In First Out)형식으로 데이터를 저장하는 자료구조이다.

### enqueue & dequeue 

> queue에서 데이터를 추가하는 것을 enqueue라고 한다. 
> queue에서 데이터를 추출하는 것을 dequeue라고 한다. 
> enqueue의 경우 queue의 맨 뒤에 데이터를 추가하면 완료되기 때문에 시간복잡도는 O(1)이다.
> 이와 비슷하게 dequeue의 경우 맨 앞의 데이터를 삭제하면 완료되기 때문에 동일하게 O(1)의 시간복잡도를 갖는다.

### 구현 방식
![img.png](../../../img/array_based_queue.png)


* Array-Based queue: enqueue와 dequeue 과정에서 남는 메모리가 생긴다. 따라서 `메모리의 낭비를 줄이기 위해 주로 Circular queue형식으로 구현`을 한다. 
* List-Based: 재할당이나 메모리 낭비의 걱정을 할 필요가 없어진다. <- Linked List의 특징  

### 확장 & 활용 
> queue의 개념에서 조금 확장한 자료구조들로는 **양쪽에서 enqueue와 dequeue가 가능한** `deque(데크)`(double-ended queue)와 
> 시간순서가 아닌 **우선순위가 높은 순서로 dequeue할 수 있는** `priority queue`가 있다.
> 
> 활용 예시로는 하나의 자원을 공유하는 프린터나, CPU task scheduling, Cache구현, 너비우선탐색(BFS) 등이 있다. 


### Circular queue
> 마치 원형처럼(= 맞물린 것처럼) 순환을 하기 때문에 원형 큐라고 부름.
> 앞의 배열 공간이 비어있고 뒷 공간이 다 차있는 경우 enqueue를 하면 앞의 공간에 다음 값들을 저장한다. 

## 심화 질문 

<details>
<summary>Q. Array-Base와 List-Base의 경우 어떤 차이가 있는가?</summary>
<div markdown="1">       

Array-Base의 경우 queue는 circular queue로 구현하는 것이 일반적이다. 
이는 메모리를 효율적으로 사용하기 위함이다. 또한 enqueue가 계속 발생하면 fixed size를 넘어서게 되기 때문에, 
dynamic array와 같은 방법으로 Array의 size를 확장시켜야 한다. 그럼에도 enqueue의 시간복잡도는 (amortized)O(1)를 유지할 수 있다. 

List-Base의 경우 보통 singly-linked list로 구현한다. enqueue는 단순히 singly-linkedlist에서 append를 하는 것으로 구현되고, 
이 때 시간복잡도는 O(1)이다. dequeue는 맨 앞의 원소를 삭제하고 first head를 변경하면 되기 때문에 이 연산도 O(1)의 시간이 걸린다. 

요약하자면, 두 가지 종류의 자료구조로 queue를 구현하더라도 enqueue와 dequeue는 모두 O(1)의 시간복잡도를 갖는다. 
Array-Base의 경우 전반적으로 performance가 더 좋지만, worst case의 경우에는 훨씬 더 느릴 수 있다(resize).
List-Base의 경우에는 enqueue를 할 때마다 memory allocation을 해야하기 때문에 전반적인 runtime이 느릴 수 있다. 

</div>
</details>

