# 데이터 구조

- 컴퓨터에서 <b>데이터를 효율적으로 저장, 관리, 구성</b>하는 방법입니다.
- 적절한 데이터 구조의 선택은 <b>메모리 사용, 성능, 처리 속도</b> 등 <u>프로그램의 전반적인 효율성</u>에 큰 영향을 미칩니다.

<br>

## 데이터 구조의 종류

1. **배열 (Array)**: 연속된 메모리 영역에 저장된 동일한 유형의 요소이며, 생성 시 크기를 결정하고 변경이 쉽지 않음. 인덱스를 통한 빠른 접근이 가능.
2. **연결 리스트 (Linked List)**: 요소들이 포인터로 연결된 선형 리스트.
  - 단일 연결 리스트, 이중 연결 리스트, 원형 연결 리스트 등의 변형이 존재.
3. **스택 (Stack)**: <U>LIFO(후입선출)</U> 원칙에 따라 요소가 추가되고 제거되는 선형 데이터 구조.
4. **큐 (Queue)**: <U>FIFO(선입선출)</U> 원칙에 따라 동작하는 선형 데이터 구조.
5. **덱 (Deque)**: <U>스택과 큐의 기능을 모두 가진 데이터 구조</U>로, 양쪽 끝에서 삽입과 삭제가 가능함.
  - 덱은 <U>Double-Ended Queue</U>의 약자입니다.
6. **트리 (Tree)**: <U>계층적 관계</U>를 가진 노드의 집합으로, 이진 트리, 이진 탐색 트리, AVL 트리, 힙 등이 있음.
7. **그래프 (Graph)**: <U>정점과 간선</U>으로 이루어진 비선형 데이터 구조로, 방향 그래프, 무방향 그래프, 가중치 그래프 등이 있음.
8. **해시 테이블(Hash Table)**: <U>키와 값</U>으로 이루어진 데이터 구조로, 효율적인 검색 및 저장 작업이 필요할 때 사용됨.
9. **힙 (Heap)**: 최대값 및 최소값 검색을 빠르게 수행할 수 있는 <U>완전 이진 트리 기반</U>의 데이터 구조로, 최대 힙과 최소 힙이 있음.
10. **우선순위 큐 (Priority Queue)**: 각 요소가 우선순위와 연관되어 있는 큐로, 우선순위가 높은 요소가 먼저 나옴. 힙으로 구현될 수 있음.
11. **세트 (Set)**: <U>유일한 값</U>을 저장하는 데이터 구조. 멤버십 검사와 같은 연산에 유용함.
12. **맵 (Map)**: <U>키와 값</U>으로 이루어진 데이터 구조로, 해시 테이블 또는 검색 트리를 사용하여 구현됨.