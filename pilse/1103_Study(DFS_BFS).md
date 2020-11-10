1103 study<br><br>

## 깊이 우선 탐색(DFS) 과 너비 우선 탐색 (BFS)
<hr>

### DFS 란?
<br>

* **`DFS`** 와 **`BFS`** 에 앞서 **그래프 탐색** 이란 하나의 정점으로 부터 시작하여 차례대로 모든 정점들을 한번씩 방문하는 것이다. 예를 들어 특정 도시에서 다른도시로 갈 수있는지, 전자회로에서 특정 단자와 단자가 서로 연결되어 있는지에 **그래프 탐색** 을 이용할 수 있다.
<br>

* **`DFS(Depth-First Search`** 란 임의의 노드에서 시작해서 다음분기(branch)로 넘어가기 전에 해당 분기를 완벽하게 탐색하는 방법이다. 미로를 탑색할 때 한 방향으로 갈 수 있을 때까지 계속 가다가 더 이상 갈 수없게 되면 다시 가장 가까운 갈림길로 돌아와서 이곳으로부터 다른 방향으로 다시 탐색을 진행하는 방법과 유사하다.
<br>

* **`DFS(Depth-First Search)`** 은 모든 노드를 방문하고자 하는 경우에 사용한다. 검색속도는 **`BFS`** 보다 느리지만 좀더 간단하다는 장점이 있다.

<hr>

### DFS의 특징과 구현
<br>

* 자기 자신을 호출하는 순환 알고리즘의 형태를 가지고 있다.
* 다른 알고리즘과의 차이점은 **`DFS(Depth-First Search)`** 를 진행하면서 지나온 노드에는 표시를 남겨야한다. 그렇지않으면 무한루프에 빠질 위험이 있다.
<br>

* **`DFS(Depth-First Search)`** 를 구현하는 방법에는 크게 두가지가 있다. 첫번째로는 순환 호출을 사용하는 방법이다. 이는 재귀함수를 이용하는 것으로 구현할 수 있다. 두번째는 명시적인 스택을 사용하는 것이다. 방문한 노드들을 스택에 저장해였다가 인접노드가 없을 때 꺼내서 사용한다. 결국 첫번째 방법과 두번째 방법 모두 말만 조금 다를뿐이지 스택을 이용하는 것이다.

<hr>

### BFS 란?
<br>

* **`BFS(Breadth-First Search`** 란 임의의 노드에서 시작해서 인접한 노드를 먼저 탐색하는 방법이다. 즉 **`DFS`** 와 다르게 깊게가 아니라 넓게 탐색하는 것이다.
<br>

* **`BFS(Breadth-First Search)`** 은 두 노드 사이의 최단경로 혹은 임의의 경로를 찾고 싶을 때 이 방법을 선택한다. 예를 들어 지구상에 존재하는 모든 친구관계를 그래프로 표현 후 A와 B에 존재하는 경로를 찾는 경우 **`DFS`** 는 모든 친구관계를 살펴봐야할지도 모르지만
**`BFS`** 는 A와 가까운 관계부터 탐색하면 된다.

<hr>

### BFS의 특징과 구현
<br>

* **`BFS`** 는 시작노드에서 시작해서 거리에 따라 단계별로 탐색한다.
* **`BFS`** 는 재귀적으로 동작하지 않는다.
* **`DFS`** 와 마찬가지로 어떤 노드를 방문했었는지 여부를 표시해야한다. 그렇지않으면 무한루프에 빠질 위험이 있다.
<br>

* **`BFS(Breadth-First Search)`** 는 **`DFS`** 가 스택을 이용하는 것과 비슷하게 **`큐(queue)`** 를 사용하여 구현한다. 처음에 시작노드를 큐에 삽입하고 방문처리를 해준다. 이후 다음과 같이 작동한다. 1.큐에서 하나의 노드를 꺼낸다. 2.해당 노드에 연결된 노드 중 방문하지 않은 노드를 방문하고, 차례대로 큐에 삽입한다. 3. 1과 2를 반복한다.

<hr>

### 정리
<br>

* 두 알고리즘모두 `C` 보다는 `C++`에서 좀더 효율적으로 사용할 수 있기 때문에 여기서는 간단한 개념만 정리하였다.
* **`DFS`** 와 **`BFS`** 모두 각각으로는 큰 의미를 지니지 않는다. 하지만 다른 알고리즘과 결합하여 사용할 때 두 알고리즘이 효과적으로 작동할 수있다.

<hr>