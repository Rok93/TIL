# Dynamic Array

<details>
<summary>Q. Dynamic Array는 어떤 자료구조인가?</summary>
<div markdown="1">       

Array의 경우 size가 고정되었기 때문에 선언시에 설정한 size보다 많은 갯수의 data가 추가되면 저장할 수 없다. 
이에 반해 Dynamic Array는 저장공간이 가득차게 되면 `resize`를 하여 유동적으로 size를 조절하여 데이터를 저장하는 자료구조이다. 

</div>
</details>

> TIP) Array의 특징중에 fixed-size의 한계점을 보완하고자 고안된 자료구조인 Dynamic Array에 대해서 
> 면접을 위해 깊게 공부할 내용은 크게 두 가지이다. 
> (1)resize를 하는 방식, (2) 데이터 추가(append)할 때의 시간복잡도 

## Dynamic Array

Dynamic Array는 size를 자동적으로 resizing을 하는 Array이다. 기존에 고정된 size를 가진 
Static Array의 한게점을 보안하고자 고안되었다. Dynamic Array는 data를 계속 추가하다가 기존에 할당된 memory를 초과하게 되면, 
size를 늘린 배열을 선언하고 그곳으로 모든 데이터를 옮김으로써 늘어난 크기의 size를 가진 배열이된다. 
이를 resize라고 한다. 이로써 새로운 data를 저장할 수 있게된다. 따라서 Dynamic Array는 size를 미리 고민할 필요없다는 장점이 있다.

resizing을 하는 방법은 여러 가지가 있는데, 대표적으로 기존 Array size의 2배 size를 할당하는 doubling이 있다. 


### Doubling 

> resize의 대표적인 방법으로는 Doubling이 있다. 데이터를 추가(O(1))하다가 메모리를 초과하게되면
> 기존 배열의 size보다 두배 큰 배열을 선언하고 데이터를 일일이 옮기는 (n개의 데이터를 일일이 옮겨야하므로 O(n)) 방법이다. 


### 분할상환 시간복잡도 Amortized time complexity 
> Dynamic Array에 데이터를 추가할 때마다 O(1)의 시간이 걸리게된다. -> 추가를 하다가 미리 선언된 size를 
> 넘어서는 순간에 resize를 하게 된다. -> 이 때는 일일이 데이터를 모두 옮겨야 되기 때문에 이 때만큼은 O(n)의 시간이 걸리게된다. \
> 그렇다면 결과적으로 append의 시간복잡도는 O(1)일까? 아니면 O(n)일까?
> append의 총 과정을 살펴보면 데이터를 마지막 인덱스에 추가하는 O(1) 작업이 대다수고, size를 넘어설 때는 
> size를 두 배 늘리고 데이터를 일일이 옮기는 과정 (resize O(n))이 아주 가끔 발생한다. 
> 결론부터 말하면 append의 전체적인 시간복잡도는 O(1)이다. 좀 더 정확히 말하면 `amortized O(1)`이라고 부른다. 
> 
> 쉽게 설명하자면 가끔 발생하는 O(n)의 resize하는 시간을, 자주 발생하는 O(1)의 작업들이 분담해서 나눠 가짐으로써 
> 전체적으로 O(1)의 시간이 걸린다고 생각하면 된다. 

## 심화 질문 
<details>
<summary>Q. Dynamic Array를 Linked List와 비교하여 장단점을 설명해주세요.</summary>
<div markdown="1">       

LinkedList와 비교했을 때, Dynamic Array의 장점은 
* 데이터 접근과 할당이 O(1)으로 굉장히 빠르다. 이는 index 접근하는 방법이 산술적인 연산 [배열 첫 data의 주솟값] + [offset] 으로 이루어져있기 때문이다. (random access == 바로 접근 가능)
* Dynamic Array의 맨 뒤에 데이터를 추가하거나 삭제하는 것이 상대적으로 빠르다. O(1)

LinkedList와 비교했을 때, Dynamic Array의 단점은
* Dynamic Array의 맨 끝이 아닌 곳에 data를 insert or remove할 때, 느린 편이다. O(n).
  * 느린 이유는 메모리상에서 연속적으로 데이터들이 저장되어 있기 때문에, 데이터를 추가 삭제할 때 뒤에 있는 data들을 모두 한칸씩 shift 해야되기 때문이다. 
* resize를 해야할 때, 예상치 못하게 현저히 낮은 performance가 발생한다. 
* resize에 시간이 많이 걸리므로 필요한 것 이상 memory공간을 할당받는다. 따라서 사용하지 않고 있는 낭비되는 메모리공간이 발생한다.

</div>
</details>

