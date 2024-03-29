# 선형 자료 구조
> 요소가 일렬로 나열되어 있는 자료 구조

## 연결 리스트
- 데이터를 감싼 노드를 포인터로 연결해서 공간적인 효율성을 극대화시킨 자료구조
- 삽입, 삭제에 O(1), 탐색에 O(n) 이 걸린다.
- 데이터 추가와 삭제를 많이 할때 사용
- 싱글 연결 리스트 : next 포인터만 가짐
- 이중 연결 리스트 : next 포인터와 prev 포인터를 가짐
- 원형 이중 연결 리스트 : 이중 연결 리스트와 비슷하지만 마지막 노드의 next 포인터가 헤드 노드를 가리킴



## 배열
- 같은 타입의 변수들로 이루어져 있고, 크기가 정해져 있으며, 인접한 메모리 위치에 있는 데이터를 모아놓은 집합
- 중복 허용, 순서가 있다.
- 접근 : O(1), 랜덤 접근 가능
- 삽입, 삭제 : O(n)
- 접근(참조)를 많이 하는 것에 좋다
- 랜덤 접근 : 동일한 시간에 배열과 같은 순차적인 데이터가 있을 때 임의의 인덱스에 해당하는 데이터에 접근할 수 있는 기능
- 순차적 접근 : 데이터를 저장된 순서대로 검색해야 하는 접근

### 배열과 연결리스트
- 배열은 랜덤 접근이 가능 O(1) , 인덱스만 알면 해당 요소 알 수 있음
- 연결 리스트는 불가능 O(n)

## 벡터
- 동적으로 요소를 할당할 수 있는 동적 배열
- 중복 허용, 순서 있음, 랜덤 접근 가능
- 탐색에 O(1)


## 스택
- 가장 마지막으로 들어간 데이터가 가장 첫 번째로 나오는 성질
- LIFO(후입선출)
- 재귀함수, 알고리즘에 사용
- 삽입 및 삭제에 O(1), 탐색에 O(n) 걸림


## 큐
- 먼저 집어놓은 데이터가 먼저 나오는 성질
- FIFO(선입선출)
- 스택과는 반대
- 삽입 및 삭제에 O(1), 탐색에 O(n)
- CPU 작업을 기다리는 프로세스, 너비우선 탐색, 캐시 등에 사용


