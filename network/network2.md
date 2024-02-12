# 2. TCP/IP 4계층 모델
인터넷 프로토콜 스위트(internet protocol suite)는 인터넷에서 컴퓨터들이 서로 정보를 주고받는 데 쓰이는 프로토콜의 집합

이를 TCP/IP 4계층 모델로 설명하거나 OSI 7계층 모델로 설명하기도 함

## 2.1 계층 구조
TCP/IP 계층은 네 개의 계층을 가지고 있다.

OSI는 7계층


TCP/IP : 애플리케이션 계층, 전송 계층, 인터넷 계층, 링크 계층

OSI : [애플리케이션, 프레젠테이션, 세션 계층], 전송 계층, 네트워크 계총, [데이터 링크 계층, 물리 계층]

계층들은 각각 독립적이다.

## 애플리케이션 계층
- FTP, HTTP, DNS 등 응용 프로그램이 사용되는 프로토콜 계층
- 웹 서비스, 이메일 등 서비스를 실질적으로 사람들에게 제공하는 층

## 전송 계층
- 송신자와 수신자를 연결하는 통신 서비스를 제공
- 애플리케이션과 인터넷 계층 사이 중개 역할을 한다.
- TCP, UDP 가 있다.
- TCP : 패킷 사이 순서 보장, 수신 여부를 확인하며 '가상회선 패킷 교환 방식'을 사용
- UDP : 순서 보장 X, 수신 여부 X, 단순히 데이터만 주는 '데이터그램 패킷 교환 방식'

### 가상회선 패킷 교환 방식
- 각 패킷에는 가상회선 식별자가 포함되며 모든 패킷을 전송하면 가상회선이 해제되고 패킷들은 전송된 '순서대로' 도착하는 방식
- 1,2,3 순서로 보내면 1,2,3, 순서로 수신됨

### 데이터그램 패킷 교환 방식
- 패킷이 독립적으로 이동하며 최적의 경로를 선택하여 가는데, 하나의 메시지에서 분할된 여러 패킷은 서로 다른 경로로 전송될 수 있으며
- 도착한 '순서가 다를 수' 있는 방식을 뜻함
- 1,2,3 을 보내도 1,3,2 순서로 수신될 수 있음

### TCP 연결 성립 과정
- TCP는 신뢰성을 확보할 때 '3-웨이 핸드셰이크'라는 작업을 진행함
    1. SYN 단계: 서버에 클라이언트의 ISN을 담아 SYN 을 보냄
    2. SYN + ACK 단계 : 서버는 클라이언트의 SYN을 수신하고 서버의 ISN을 보내며 승인번호로 클라이언트의 ISN+1을 보냄
    3. ACK 단계 : 클라이언트는 서버의 ISN + 1한 값인 승인번호를 담아 ACK를 서버에 보냄
- 3-웨이 핸드셰이크 과정 이후 신뢰성이 구축, 데이터 전송을 시작함
- 이 과정때문에 TCP는 신뢰성이 있는 계층, UDP는 신뢰성이 없는 계층이라 함

### TCP 연결 해제 과정
- 4-웨이 핸드셰이크 과정으로 TCP 연결 해제

## 인터넷 계층
- 인터넷 계층은 장치로부터 받은 네트워크 패킷을 IP 주소로 지정된 목적지로 전송하기 위해 사용되는 계층
- IP, ARP, ICMP 등이 있다.
- 패킷을 수신해야 할 상대의 주소로 지정하여 데이터 전달
- 상대방이 제대로 받았는지에 대해 보장하지 않는 비연결형적 특징

## 링크 계층
- 전선, 광섬유, 무선 등으로 실질적으로 데이터를 전달하며 장치 간에 신호를 주고받는 '규칙'을 정하는 계층
- 네트워크 접근 계층이라고도 함
- 물리 계층과 데이터 링크 계층으로 나누기도 함
- 물리 계층 : 무선LAN과 유선LAN을 통해 0과 1로 이루어진 데이터를 보내는 계층
- 데이터 링크 계층 : '이더넷 프레임'을 통해 에러 확인, 흐름 제어, 접근 제어를 담당하는 계층


### 유선 LAN
- 전이중화 통신 : 양쪽 장치가 동시에 송수신할 수 있는 방식
- CSMA/CD : 데이터를 '보낸 이후' 충돌이 발생한다면 일정 시간 이후 재전송 하는 방식
- 트위스트 페어 케이블
- 광섬유 케이블

### 무선 LAN
- 반 이중화 통신 - 한번에 한방향만 통신
- CSMA/CA : 사전에 가능한 한 충돌을 방지
- 와이파이 : 전자기기들이 무선 LAN 신호에 연결할 수 있게 하는 기술
- BSS : 기본 서비스 집합
- ESS : 하나 이상의 연결된 BSS 그룹


## 이더넷 프레임
- 데이터 링크 계층은 이더넷 프레임을 통해 전달받은 데이터의 에러를 검출하고 캡슐화한다.

## 계층 간 데이터 송수신 과정
전송자의 애플리케이션 계층 -> 전송 -> 인터넷 -> 링크 -> 수신자의 링크 계층 -> 인터넷 -> 전송 -> 애플리케이션

### 캡슐화 과정
- 상위 계층의 헤더와 데이터를 하위 계층의 데이터 부분에 포함시키고 해당 계층의 헤더를 삽입하는 과정

### 비캡슐화 과정
- 하위 계층에서 상위 계층으로 가며 각 계층의 헤더 부분을 제거하는 과정

## PDU
- 네트워크의 어떠한 계층에서 계층으로 데이터가 전달될 때 한 덩어리의 단위
- 제어 관련 정보들이 포함된 '헤더', 데이터를 의미하는 '페이로드'로 구성