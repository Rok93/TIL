# Array vs LinkedList

<details>
<summary>Q. Array는 어떤 자료구조인가?</summary>
<div markdown="1">       

Array는 연관된 data를 `메모리에 연속적이며 순차적`으로 `미리 할당된 크기`만큼만 저장하는 자료구조이다. 

</div>
</details>


> TIP) Array에 관한 질문을 할 때는 매우 높은 확률로 LinkedList에 대한 질문도 나오게된다. 따라서 Array의 
> 다양한 특징들 중 LinkedList와 비교가되는 특성들을 위주로 대답을하게되면 편하게 풀어나갈 수 있다. 
> Array와 LinkedList의 가장 큰 차이점은 메모리에 저장되는 방식과 이에 따른 operation의 연산속도(time complexity)이다. 


## Array 

Array는 연관된 data를 모아서 메모리상에 연속적이며 순차적으로 저장하는 자료구조

### Array의 특징
* 고정된 저장 공간(fixed-size)
* 순차적인 데이터 저장(order)

### Array의 operation들의 time complexity
* 조회(lookup): O(1)
  * random access라고도 불림
* 마지막 인덴스에 추가(append): O(1)
* 마지막 인덱스에 삭제: O(1)
* 삽입(insert): O(n)
* 삭제(delete): O(n)
* 탐색(search): O(n)
  * 어떤 숫자가 몇 번째 인덱스에 있는지 탐색할 때 (순차적으로 방문하면서 탐색해야 함)

* Array 장점 
  * 조회와 추가가 빠르다는 것이다(추가의 경우에는 마지막 인덱스에 추가할 경우에). 따라서 조회를 자주해야하는 작업에서는 Array 자료구조를 많이 쓴다.
* Array 단점
  * fixed-size 특성상 선언시에 Array의 크기를 미리 정해야된다는 것이다. 이는 메모리 낭비나 추가적인 overhead가 발생할 수 있다.
    * ex1) 만약 배열 크기를 100으로 잡았는데 데이터를 10개만 받는다면? 나머지 90만큼의 메모리가 낭비됌
    * ex2) 사이즈 100을 했는데, 데이터가 101개 들어왔다면 기존 배열보다 더 큰 배열을 새로 선언하고, 이전 배열의 값들을 새로운 배열로 옮기고 마지막 101번째 데이터를 새로운 배열에 추가한다.


## 심화 질문 

<details>
<summary>Q. 미리 예상한 것보다 더  많은 수의 data를 저장하느라 Array의 size를 넘어서게됐다. 이 때, 어떻게 해결할 수 있을까?</summary>
<div markdown="1">       

기존의 size보다 더 큰 Array를 선언하여 데이터를 옮겨 할당한다. 모든 데이터를 옮겼다면 기존 Array는 메모리에서 삭제하면된다. 
이런식으로 동적으로 배열의 크기를 조절하는 자료구조를 `Dynamic Array`라고 한다.

또 다른 방법으로는, size를 예측하기 쉽지 않다면 Array 대신 Linked List를 사용함으로써 데이터가 추가될 때마다 메모리공간을 할당받는 방식을 사용하면된다. 

</div>
</details>

