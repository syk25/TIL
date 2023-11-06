# Tree
## 기본개념
### 정의
트리는 **노드**와 **링크**로 구성 된 자료구조다.
그래프의 일종으로서 **비순환적**이다.
폴더구조, 조직도, 계층도와 같이 **계층적 구조**를 표현할 때 쓴다.

### 기본구조
![image](https://github.com/syk25/TIL/assets/129013571/2afaf2f2-f64e-4995-a0fb-f981d18d499e)
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

![image](https://github.com/syk25/TIL/assets/129013571/37eb70d5-728a-4609-b42a-df636a0ccdc5)
  

### 포화이진트리(Perfect Binary Tree) vs 완전이진트리(Complete Binary Tree)
![image](https://github.com/syk25/TIL/assets/129013571/1e15192b-4c6f-4e3c-a246-6bd2976e5344)
- PBT: 모든 레벨에서의 노드들이 점유된 이진 트리
- CBT: 마지막 레벨을 제외하고 모든 레벨에서 노드들이 점유 된 이진트리


### 정이진트리(Full Binary Tree) vs 편향트리(Skewed Binary Tree)
![image](https://github.com/syk25/TIL/assets/129013571/07d0027b-887f-4ec7-ab67-6289b7bd5f0a)
- FBT : 노드가 0개 또는 2개의 자식노드를 가지는 이진트리
- SBT: 한쪽으로만 노드가 구성된 트리(연결리스트도 SBT에 포함 됨)
  

### 균형이진트리(Balanced Binary Tree)
![image](https://github.com/syk25/TIL/assets/129013571/f784f620-c85e-452c-8b12-d1678fffac74)
- 좌우대비 높이차이가 1이하인 이진트리
  

## 이진트리의 특징
- 높이(h) = 2log(2)N (PBT, CBT 해당)
- 노드의 개수 N = 2^(h+1) - 1

## 이진트리의 순회(Traversal)
- 정의 : 모든 노드를 빠지지 않고, 그리고 중복하지 않고 방문하는 연산
- DFS형 : 전위 순회, 중위 순회, 후위 순회(깊이기준)
- BFS형: 레벨 순회(레벨기준)

### 전위순회(Pre-order Traversal)
![image](https://github.com/syk25/TIL/assets/129013571/58868f36-d043-468e-a4cc-1e646956f7fd)
- 방문순서 : 현재 > 왼쪽 > 오른쪽
  

### 중위순회(In-Order Traversal)
![image](https://github.com/syk25/TIL/assets/129013571/d1b00a51-23fd-4dda-95b9-670d9c8fb4ad)
- 방문순서 : 왼쪽 > 현재 > 오른쪽
  

### 후위순회(Post-Order Traversal)
![image](https://github.com/syk25/TIL/assets/129013571/8db366ab-515d-4316-910e-807a0ecd59d5)
- 우선순위 : 왼쪽 > 오른쪽 > 현재
  

### 레벨순회(Level Traversal)
![image](https://github.com/syk25/TIL/assets/129013571/6e0c01f8-ea1e-4b43-a947-054f367d45ab)
- 루트로부터 가까운 레벨의 노드부터 순회
  





