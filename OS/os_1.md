# 3.1 운영체제와 컴퓨터

## 3.1.1 운영체제의 역할과 구조
 
 ### 운영체제의 역할
 1. CPU 스케줄링과 프로세스 관리 : CPU 소유권을 어떤 프로세스에 할당할지, 프로세스 생성과 삭제, 자원 할당 및 반환을 관리
 2. 메모리 관리 : 한정된 메모리를 어떤 프로세스에 얼만큼 할당해야 하는지 관리
 3. 디스크 파일 관리 : 디스크 파일을 어떠한 방법으로 보관할지 관리
 4. I/O 디바이스 관리 : I/O 디바이스들(키보드, 마우스) 간에 데이터를 주고받는 것을 관리

 ### 운영체제의 구조
 유저 프로그램
 운영체제
 {
    인터페이스(GUI, CUI)
    시스템콜
    커널(드라이버, 파일 시스템 등)
 }
 하드웨어

* 드라이버 - 하드웨어를 제어하기 위한 소프트웨어
* GUI - 그래픽으로 유저와 컴퓨터간 상호 작용할 수 있는 사용자 인터페이스
* CUI - 그래픽이 아닌 명령어로 처리하는 인터페이스



- 시스템콜 -  운영체제가 커널에 접근하기 위한 인터페이스, 유저 프로그램이 운영체제의 서비스를 받기 위해 커널 함수를 호출할 때 사용.

유저 프로그램 < - > 시스템콜(유저모드/커널모드) < - > 파일 시스템

유저 프로그램이 I/O 요청할 시, 올바른 요청인지 확인 후 유저모드가 시스템콜을 통해 커널모드로 변환되어 실행

프로세스,스레드에서 운영체제로 어떠한 요청 시 시스템콜 인터페이스와 커널을 거쳐 운영체제에 전달

네트워크 통신, 데이터베이스 같은 낮은 단계의 영역 처리에 대한 부분에 대한 신경을 줄이고 프로그램 구현가능한 장점이 있다.


* 유저 모드 - 유저가 접근할 수 있는 영역을 제한적으로 두며 컴퓨터 자원에 함부로 침범하지 못하는 모드
* 커널 모드 - 모든 컴퓨터 자원에 접근할 수 있는 모드
* 커널 - 운영체제의 핵심 부분이자 시스템콜 인터페이스를 제공하며 보안, 메모리, 프로세스, 파일 시스템, I/O 디바이스, I/O 요청 관리 등 운영체제의 중추적인 역할



## 3.1.2 컴퓨터의 요소
- 컴퓨터는 CPU, DMA 컨트롤러, 메모리, 타이머, 디바이스 컨트롤러 등으로 이루어져 있다.

### CPU
- 산술논리연산장치, 제어장치, 레지스터로 구성되어 있는 컴퓨터 장치
- 인터럽트에 의해 단순히 메모리에 존재하는 명령어를 해석해서 실행하는 일꾼

#### 제어장치(CU)
- 프로세스 조작을 지시하는 CPU의 한 부품
- 입출력장치 간 통신을 제어하고 명령어들을 읽고 해석하며 데이터 처리를 위한 순서를 결정

#### 레지스터
- CPU 안에 있는 매우 빠른 임시기억장치를 가리킨다.
- 연산속도가 메모리보다 수백 배까지 빠름
- CPU는 레지스터를 거쳐 데이터를 전달

#### 산술논리연산장치(ALU)
- 덧셈, 뺄셈 같은 두 숫자의 산술 연산, 배타적 논리합, 논리곱 같은 논리 연산을 계산
- 메모리에 계산할 값을 로드 + 레지스터로 로드 -> 레지스터에 있는 값을 계산 -> 다시 레지스터에서 메모리로 계산한 값을 저장

#### 인터럽트
- 어떤 신호가 들어왔을 때 CPU를 잠깐 정지시키는 것
  - 하드웨어 인터럽트 : IO 디바이스에서 발생
  - 소프트웨어 인터럽트 : 트랩(trap), 프로세스 오류 등으로 프로세스가 시스템콜을 호출할 때 발동

### DMA 컨트롤러
- I/O 디바이스가 메모리에 직접 접근할 수 있도록 하는 하드웨어 장치
- CPU의 일을 부담하여 CPU 부하를 막아줌
- 하나의 작업을 CPU와 DMA 컨트롤로가 동시에 하는 것을 방지

### 메모리
- 데이터나 상태, 명령어 등을 기록하는 장치
- 보통 RAM을 일컬어 메모리라고 한다.

### 타이머
- 특정 시간까지 특정 프로그램에 시간 제한을 다는 역할

### 디바이스 컨트롤러
- 컴퓨터와 연결되어 있는 IO 디바이스들의 작은 CPU를 말함


