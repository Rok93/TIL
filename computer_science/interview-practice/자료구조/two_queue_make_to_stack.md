> TIP) queue 두 개를 사용하여 stack의 push와 pop를 구현하는 것에 초점을 맞춰서 문제를 해결하면 된다."
> 구현 방법을 외우기보다는 문제를 해결해 나가는 과정을 보여주는 것이 좋다. 

<details>
<summary>Q. Queue 두 개를 이용하여 Stack을 구현해보라.</summary>
<div markdown="1">       

편의상 push()에 사용할 queue는 q1, pop()에 사용할 queue를 q2라고 칭한다. 두 개의 queue로 stack을 구현하는 방법은 다음과 같다. 

1. push() :: q1으로 enqueue()를 하여 데이터를 저장한다. O(1)
2. pop() :: 
   1. q1에 저장된 데이터의 갯수가 1이하로 남을 때까지 dequeue()를 한 후,추출된 데이터를 q2에 enqueue()한다. 결과적으로 가장 최근에 들어온 데이터를 제외한 모든 데이터는 q2로 옮겨진다. 
   2. q1에 남아있는 하나의 데이터를 dequeue()해서 가장 최근에 저장된 데이터를 반환한다. (LIFO)
   3. 다음에 진행될 pop()을 위와 같은 알고리즘으로 진행하기 위해 q1과 q2의 이름을 swap한다.

</div>
</details>

```Python3 
import queue

class Stack(object):
    def __init__(self):
        self.q1 = queue.Queue()
        self.q2 = queue.Queue()
    
    def push(self, element):
        self.q1.put(element)
    
    def pop(self):
        while self.q1.qsize() > 1:
            self.q2.put(self.q1.get())
            
        temp = self.q1
        self.q1 = self.q2
        self.q2 = temp
        
        return self.q2.get()
```

## 심화 질문 

<details>
<summary>Q. 시간복잡도는 어떻게 되는지 설명해 주세요.</summary>
<div markdown="1">

* push(): q1.enqueue()를 한번만 하면 되기 때문에 O(1)의 시간복잡도를 갖는다. 
* pop(): q1에 저장되어 있는 n개의 원소중에 n-1개를 q2로 옮겨야 하므로 O(n)이 된다.

</div>
</details>
