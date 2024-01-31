# 5. 인덱스
필요성
- 데이터를 빠르게 찾을 수 있는 하나의 장치

## B - 트리
- 인덱스는 B - 트리 자료구조로 이루어져 있음
- 루트 노드, 브랜치 노드, 리프 노드로 구성

인덱스가 효율적인 이유와 대수확장성
- 효율적인 단계를 거쳐 모든 요소에 접근할 수 있는 균형 잡힌 트리구조 + 트리 깊이의 대수확장성 때문
- 대수확장성 : 트리 깊이가 리프 노드 수에 비해 매우 느리게 성장하는 것을 의미
- 트리깊이가 1 깊어질때, 인덱스 항목은 최대 4배까지 증가함
  
  ## 인덱스 만들기
  1. MySQL 의 경우
    - 클러스터형 인덱스, 세컨더리 인덱스

  2. MongoDB
    -  도큐먼트를 만들면 자동으로 키 생성 
-  

## 인덱스 최적화 기법
1. 인덱스는 비용이다 : 인덱스는 두 번 탐색을 강요하기에 탐색 비용이 많이 든다, 탐색의 효율을 높이기 위해서 B트리를 균형있게 조절하는 비용 + 데이터의 효율적 조회를 위한 분산 비용, 읽기 비용을 줄여야 함
2. 항상 테스팅하라. : 서비스 특징에 따라 최적화 기법이 다르기 때문에 항상 테스팅을 해야한다.
3. 복합 인덱스는 같음, 정렬, 다중 값, 카디널리티 순 : 인덱스는 생성할 때 순서가 있고 생성 순서에 따라 인덱스 성능이 달라짐


# 6. 조인의 종류
`조인(join)이란 하나의 테이블이 아닌 두 개 이상의 테이블을 묶어서 하나의 결과물로 만드는 것`

- 종류 : 내부 조인, 왼쪽 조인, 오른쪽 조인, 합집합 조인

- 내부 조인 : 두 테이블의 교집합 -> A and B
- 왼쪽 조인 : 왼쪽 테이블의 값을 표기 -> A
- 오른족 조인 : 오른족 테이블의 값을 표기 -> B
- 합집합 조인 : 두 테이블의 합집합 -> A or B


# 7. 조인의 원리
- 중첩 루프 조인, 정렬 병합 조인, 해시 조인 이라는 원리를 기반으로 작입이 이루어짐

## 중첩 루프 조인(NLJ)
- 중첩 for 문과 같은 원리로 조건에 맞는 조인을 하는 방법
- 랜덤 접근에 대한 비용이 많이 증가하므로 대용량은 X

## 정렬 병합 조인
- 각각의 테이블을 조인할 필드 기준으로 정렬하고 정렬이 끝난 이후에 조인 작업 수행
- 적절한 인덱스 존재 X, 대용량 조인, 조인 조건이 <, > 같은 범위 비교 연산자가 있을때 사용

## 해시 조인
- 해시 테이블을 기반으로 조인
- 빌드 단계, 프로브 단계로 조인