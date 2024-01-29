# 컴퓨터구조 정리

컴퓨터는 하드웨어와 소프트웨어로 나눠짐

하드웨어
- 중앙처리장치(CPU)
- 기억장치
- 입출력장치

소프트웨어
- 시스템 소프트웨어
- 응용 소프트웨어

## 하드웨어

### 중앙처리장치(CPU)
주기억장치에서 프로그램 명령어와 데이터를 읽어와 처리하고 명령어의 수행 순서를 제어한다.
- 산술논리연산장치(ALU) - 비교와 연산 담당
- 제어장치 - 명령어의 해석과 실행 담당
- 레지스터 - 데이터를 일시적으로 빠르게 저장

작동원리
1. 기억장치(메모리)에 저장된 프로그램 명령을 CPU가 읽어옴
2. CPU가 가져온 명령어와 데이터를 읽어와 처리하고 결과를 다시 레지스터나 주기억장치에 저장
3. 주기억장치는 처리 결과를 보조기억장치에 저장하거나 출력장치로 보냄


### 기억장치
- 주기억장치(RAM & ROM) - 프로그램 실행 중 필요한 데이터와 명령어를 일시적으로 저장함, 읽기 쓰기가 가능, 휘발성
    * RAM과 ROM으로 나뉨
    * RAM : 읽고 쓰기가 가능 -> 응용 프로그램이나 운영체제들을 불러와 CPU가 작업할 수 있도록 함, 휘발성 메모리
    * ROM : 오직 읽기만 가능하고 수정이 힘든 특징 -> BIOS와 같은 주요 데이터를 저장, 비 휘발성 메모리

- 캐시메모리 - CPU가 자주 사용하는 데이터나 명령어를 빠르게 접근할 수 있도록 저항하는 고속 메모리
    * CPU코어와 메모리 사이의 속도 차이에 따른 병목현상을 완화해줌
    * CPU가 자주 사용하는 데이터를 캐시메모리에 저장시켜 다음에 사용할때 캐시 메모리에서 빠르게 데이터를 가져올 수 있게 해줌
    * 시간지역성, 데이터지역성이 존재한다
    * DRAM, SRAM으로 구성


- 보조기억장치 - 데이터를 장기적으로 저장하는 장치, 비휘발성, 대용량 : HDD,SDD
- 플래시 메모리 - 주로 이동식 저장 장치에 사용하는 메모리, usb 메모리 , 주기억장치와는 다르게 cpu에서 직접 읽고 쓸 수 없다
  

#### 추가적인 메모리
- Microprocessor cache
  - 마이크로프로세서 : cpu의 핵심 부분을 구성하는 칩 , 명령어 해석이나 데이터 처리 등 cpu의 역할이 가능함
  - 마이크로프로세서 캐시는 캐시메모리와 비슷한 역할을 한다 -> cpu와 주 메모리 간의 속도 차이를 극복하여 프로세서 속도 향상을 해주는 메모리 영역

- Virutal Memory 가상 메모리
  - 주 메모리의 용량 한계나 특정 프로세스의 메모리 요구를 초과하는 경우에 활용하여 주 메모리를 보조 해줌
  - 프로세스 : 컴퓨터에서 실행중인 프로그램
  - 프로그램 : 기억장치에 저장되어 있는 코드와 리소스 등이 집합된 파일, 이걸 말하고 실행하는 것이 프로그램이다.
  - 
### 입출력장치
- 입력장치 - 컴퓨터 내부로 자료를 입력 : 키보드, 마우스 등
- -출력장치 - 컴퓨터에서 외부로 자료를 표현 : 프린터, 모니터, 스피커 등

## 소프트웨어
- 시스템 소프트웨어 : 운영체제, 컴파일러
- 응용 소프트웨어 : 오피스 프로그램 등
