
> 의외로 종종 나오는 면접 질문이다. 따로 준비해가지 않으면 현장에서 바로 떠올리기 힘들 수 있지만,
> 한 번 준비했다면 쉽게 답할 수 있다. stack 두 개를 사용하여 enqueue와 dequeue를 구현하는 것에 초점을 맞춰서 문제를 해결하면 된다. 
> 
> 사실 이런 문제는 답이 다양하고, 답 자체가 중요하기 보단 답을 찾아가는 과정을 더 중요하게보기 때문에, 
> 풀이를 외우기보단 접근 방식을 주의깊게 보자! 

<details>
<summary>Q. Stack 두 개를 이용하여 Queue를 구현해보라.</summary>
<div markdown="1">       

queue의 enqueue()를 구현할 때 첫 번째 stack(= instack)을 사용하고, dequeue()를 
구현할 때 두 번째 stack(= outstack)을 사용하면 queue를 구현할 수 있다.

편의상 enqueue()에 사용할 stack을 instack이라고 부르고 dequeue()에 사용할 stack을 outstack이라고 칭하고 
두 개의 stack으로 queue를 구현하는 방법은 다음과 같다. 

1. enqueue() :: instack에 push()를 하여 데이터를 저장한다. 
2. dequeue() :: 
   1. 만약 outstack이 비어있다면 instack.pop()을 하고 outstack.push()를 하여 instack에서 outstack으로 모든 데이터를 옮겨 넣는다. 이 결과로 가장 먼저 왔던 데이터는 outstack의 top에 위치하게 된다.  
   2. outstack.pop()을 하면 가장먼저 왔던 데이터가 가장 먼저 추출된다. (FIFO)


</div>
</details>

[//]: # (kotlin이나 java or js 코드로 변경하기!)
```Python3
class Queue(object):
    def __init__(self):
        self.instack=[]
        self.outstack=[]
        
    def enqueue(self, element):
        self.instack.append(element)
        
    def dequeue(self):
        if not self.outstack:
            while self.instack:
                self.outstack.append(self.instack.pop())
        return self.outstack.pop()
```

## 심화 질문

<details>
<summary>Q. 시간복잡도는 어떻게 되는지 설명해 주세요.</summary>
<div markdown="1">       

* enqueue() : instack.push()를 한번만 하면 되기 때문에 시간복잡도 O(1)이다. 
* dequeue() : 두 가지 경우를 따져봐야 한다. 
  * worst case는 outstack이 비어있는 경우이다. 이 때는 instack에 있는 n개의 데이터를 instack.pop()을 한 이후에 outstack.push()를 해줘야 한다. 따라서 2*n 번의 operation이 실행되어야 하므로 O(n)의 시간복잡도를 갖는다. 
  * 하지만 outstack이 비어있지 않는 경우에는 outstack.pop()만 해주면 된다. 이는 O(1)의 시간복잡도를 갖는다. 
  * 이를 종합했을 때, amortized O(1)의 시간복잡도를 갖는다고 할 수 있다. 

enqueue() - O(1)
dequeue() - O(1)

</div>
</details>

