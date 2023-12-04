
Balanced Tree

[[Binary Search Tree]]의 변형으로, Node에 들어가는 key의 값을 늘려서 트리의 height를 낮추어 성능을 개선한 Tree

이때, 하나의 Node가 가질수있는 최대 Key의 갯수를 
Branching Factor라고 한다.

Node 한개를 Page 또는 Block이라 부르며, 한번의 [[I/O]]  연산에서
하나를 통째로 들고온다.


장점: Insertion, Delete, Search등의 연산이 
전부 O(Log(N))의 시간복잡도를 갖는다.

