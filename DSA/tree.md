# Tree
## 기본개념
### 정의
트리는 **노드**와 **링크**로 구성 된 자료구조다.
그래프의 일종으로서 **비순환적**이다.
폴더구조, 조직도, 계층도와 같이 **계층적 구조**를 표현할 때 쓴다.

### 기본구조
#### 필수구성요소
- 노드(node): 트리에서 자료값을 담고 있는 기본단위
- 간선(edge): 노드를 연결해주는 선으로서 link, bridge라고도 한다.

#### 노드의 분류
- 잎새노드(Leaf) : 자식노드가 없는 노드
- 내부노드(internal): 잎새노드를 제외한 모든 노드
- 부모노드(parent): 연결된 노드 중 상위노드
- 자식노드(child): 연결 된 노드 중 하위노드
- 형제노드(sibling): 부모를 공유하는 같은 레벨의 노드

#### 트리의 성질
- 깊이(depth): 루트에서 표적 노드까지의 간선의 수
- 레벨(level): 트리에서 특정 깊이를 점유하는 노드의 집합
- 높이(height): 트리에서 가장 큰 레벨 값
- 크기(size): 자신을 포함한 자식노드의 개수
- 차수(degree): 노드에 연결 된 간선의 개수
- 트리차수 : 트리에서 가장 값이 큰 차수

## 트리의 특징
- 노드 간의 경로는 **유일**하다
- 노드의 수 : 간선의 수 = N : N -1
- 트리에서 연결되어 있지 않은 노드는 없다
- 트리는 **비순환적**이다
- 하나의 간선을 끊으면 sub tree 2개가 생긴다

## 이진트리의 종류
### 이진트리
- 부모가 최대 2개의 자식노드를 가지는 트리
- 트리의 좌우는 구분 됨
  ![image 2.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2F7C23F9E2-925D-41DC-9D30-3CE9A774AE07%2Fimage%202.png)![](image%202.png)<!-- {"width":303} -->

### 포화이진트리(Perfect Binary Tree) vs 완전이진트리(Complete Binary Tree)
- PBT: 모든 레벨에서의 노드들이 점유된 이진 트리
- CBT: 마지막 레벨을 제외하고 모든 레벨에서 노드들이 점유 된 이진트리
  ![image 3.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2F4541BDE5-11A4-48CD-B484-AD4D30B1FFF2%2Fimage%203.png)![](image%203.png)<!-- {"width":465} -->

### 정이진트리(Full Binary Tree) vs 편향트리(Skewed Binary Tree)
- FBT : 노드가 0개 또는 2개의 자식노드를 가지는 이진트리
- SBT: 한쪽으로만 노드가 구성된 트리(연결리스트도 SBT에 포함 됨)
  ![image 4.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2FCBFCE76E-FC78-41BD-8E58-7A09B0CBAA55%2Fimage%204.png)![](image%204.png)<!-- {"width":465} -->

### 균형이진트리(Balanced Binary Tree)
- 좌우대비 높이차이가 1이하인 이진트리
  ![image 5.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2F316AD268-BC19-4787-9000-3470D107FA01%2Fimage%205.png)![](image%205.png)<!-- {"width":459} -->

## 이진트리의 특징
- 높이(h) = 2log(2)N (PBT, CBT 해당)
- 노드의 개수 N = 2^(h+1) - 1

## 이진트리의 순회(Traversal)
- 정의 : 모든 노드를 빠지지 않고, 그리고 중복하지 않고 방문하는 연산
- DFS형 : 전위 순회, 중위 순회, 후위 순회(깊이기준)
- BFS형: 레벨 순회(레벨기준)

### 전위순회(Pre-order Traversal)
- 방문순서 : 현재 > 왼쪽 > 오른쪽
  ![image 6.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2F420EBEEC-7B5A-414B-9436-6674BCF698E1%2Fimage%206.png)![](image%206.png)<!-- {"width":415} -->

### 중위순회(In-Order Traversal)
- 방문순서 : 왼쪽 > 현재 > 오른쪽
  ![image 7.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2F0CAE026E-8981-42C4-84DF-82522C12439C%2Fimage%207.png)![](image%207.png)<!-- {"width":419} -->

### 후위순회(Post-Order Traversal)
- 우선순위 : 왼쪽 > 오른쪽 > 현재
  ![image 9.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2FB6A0C6BF-E32B-400C-B32F-415DF831BF39%2Fimage%209.png)

### 레벨순회(Level Traversal)
- 루트로부터 가까운 레벨의 노드부터 순회
  ![image 8.png](..%2F..%2F..%2F..%2FLibrary%2FGroup%20Containers%2F9K33E3U3T4.net.shinyfrog.bear%2FApplication%20Data%2FLocal%20Files%2FNote%20Images%2FBC8D435D-733E-4250-BA08-7F03C09C09BD%2Fimage%208.png)![](image%208.png)<!-- {"width":329} -->





