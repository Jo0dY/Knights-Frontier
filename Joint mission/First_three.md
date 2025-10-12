# 🌙 Knights Frontier 공동 미션 (1)
- 모든 기수 BoB 프로젝트 주제 중 가장 관심있는 주제 3개 선택하고 지식 탐구 및 정리하기 
<br>

## CAN 네트워크를 통한 자동차 제어(5기)


### 탐구하려는 주제에 대한 간단한 소개


### 이 주제를 관심 있는 주제로 선정한 이유


<br>


### 차량 내부 통신 정리 및 비교

<br>

| 구분 | LIN | CAN | MOST | FlexRay | Ethernet |
| --- | --- | --- | --- | --- | --- |
| 최대 전송 속도    (bps) | 19.2k | 1M | 150M | 10M | 100M |
| 전송 선로 | 단선 | 꼬인 두 선  | 광섬유 | 꼬인 두선  | 비보호 꼬인 두 선(UTP) |
| 1회 전송 데이터 | 0-8byte | 0-8byte | 0-1008byte | 0-256byte | 0-1500byte |
| 주요 적용 시스템 | 저가형 센서      편의 센서 | 파워 트레인           섀시                     편의장치 | AV | 파워 트레인         편의장치 | 멀티미디어                카메라                         인포테인먼트 |
| 설치 비용 | 적음 | 중간 | 높음 | 높음 | 높음 |

<br>

LIN (Local Interconnect Network)

→ 다양한 기능이 필요하지 않은 분야에 저렴하면서 효율적인 통신을 제공 , 실제로 차량 시스템에서 베터리 센서, 제너레이터, 주차감지 시스템, 도어 제어 모듈 등에서 사용됨

FlexRay

→ CSMA(Carrier Sense Multiple Access) 방식을 사용하는 CAN과 다르게 FlexRay는 TDMA(Time Division Multiple Access) 방식을 사용하는데, 각 노드가 유효한 상태가 되면 전송하는 것이 아닌 정해진 시간에 메시지를 전송하기때문에 통신 속도를 향상 시킬 수 있음 

MOST(Multimedia Oriented System Transport)

→ 차량 멀티미디어 장치를 위한 광통신 규약으로 대용량 멀티미디어 자료를 초고속으로 전송할 수 있음 
<br>

### CAN의 개념 및 특징 

<br>
- 차량 및 산업용 제어 시스템에서 사용되는 통신 프로토콜로 각 모듈 간 데이터 통신에 이용된다.        
- CAN 은 차량 내 모든 EUC가 두 개의 통신선 (CAN_H,CAN_L)을 공유하며, 각 ECU는 고유한 ID를 가진 메시지를 주고받는다.       
- 통신선은 꼬인 두선이라고 표현한 2개의 선으로 활용된다.       
- 두 구리선의 전위차가 0V일때 0, 0V가 아닐때 1로 Binary Digit의 교환으로서 정보를 주고 받는다.       

<br>

### CAN Protocol 구성

<br>
<p align="center"><img width="731" height="178" alt="Image" src="https://github.com/user-attachments/assets/fade7ad7-473e-4558-b590-351ebfcdc44e" /></p>

<br>
- CAN 프로토콜은 표준화된 특성 임피던스를 가지고 있는 쌍선(꼬인 두선) 케이블을 통해 데이터를 전송하는데, 이로 인해 각종 외부 노이즈에 강한 쉴드로 보호를 받을 수 있음.                    
- CAN 통신 프로토콜에서는 프레임이 데이터의 전송단위고, 하나의 프레임은 총 아래 6가지로 구성               

<br>

| SOF | Identifier | Control Field |
| --- | --- | --- |
| EOF | Data Field | CRC |


<br>
언급된 것처럼, CAN 통신 프로토콜에서는 메시지를 식별하는 용도로 식별자를 이용하는데, 이 식별자(Identifier)은 11 또는 29비트의 길이를 가지고 있다.    

식별자는 가지는 비트의 길이마다 다른 이름을 가지며, 11비트 식별자는 SID, 29비트 식별자는 Extended CAN 즉, EID라는 명칭으로 불린다.      

오류 검출 및 복구 기능을 지원하기 위해 CRC 처리 기법을 사용하는데 CRC는 Cyclic Redundancy Check의 약자로, 데이터 전송 중 오류 발생 시 프레임 재전송 및 데이터의 신뢰성을 보장하기 위한 방법이다.             

<br>

### CAN Protocol 특징 정리

<br>


| 고속통신 | 빠른 데이터 전송 지원 |
| --- | --- |
| 오류 복구 및 검출 기능 지원 | 데이터 전송 중 오류 발생 시 오류 식별 및 수정 기능 지원 |
| 멀티 마스터 통신 | 다수의 디바이스의 동시 데이터 전송 지원 |
| 적은 전력 소비 | 배터리 수명 연장 및 저전력 소비 지원 |
| 우선 순위 기반 통신 | 메시지 우선순위 기반의 통신 처리 지원 |
| 신뢰적이고 안정적인 통신 | 여러방면에서 높은 신뢰성을 가진 통신을 지원 |

<br>

### CAN의 물리적 특성

<br>

- **Wired-AND 방식 동작**
    - 두 개의 신호선(CAN_H, CAN_L) 사용한다.
    - **Dominant(0)**: CAN_H = 3.5V, CAN_L = 1.5V (전압차 2V)
    - **Recessive(1)**: CAN_H = CAN_L = 2.5V (전압차 0V)
- **충돌 발생 시 동작 원리**
    - 하나의 노드라도 Dominant(0)를 보내면 버스는 Dominant 상태 유지한다.
    - 모든 노드가 Recessive(1)를 보내야만 버스가 Recessive 상태가 된다.

<br>


### CAN 계층 구조
<br>

<p align="center"><img width="1856" height="999" alt="Image" src="https://github.com/user-attachments/assets/aa5b28da-ca66-461d-aabd-7e2637e84e1b" /></p>


<br>
CAN에는 여러 종류의 다른 물리 계층이 있다.             

물리 계층은 전기적 레벨, 신호 구조, 케이블 임피던스, 최대 보드 (baud) 속도 등 CAN 네트워크의 특정 사항을 분류한다.          

가장 보편적이며 널리 사용되는 물리 계층은 아래와 같다.           
<br>
<br>

**High-Speed CAN**  

High-speed CAN은 현재까지 가장 보편적으로 사용되는 계층으로, 고속 CAN 네트워크는 두 개의 와이어로 실행되며 최대 1 Mb/s 전송 속도로 통신을 진행한다. 고속 CAN의 다른 명칭으로는 CAN C와 ISO 11898-2가 있다. 일반적인 고속 CAN 디바이스에는 ABS (anti-lock brake systems), 엔진 컨트롤 모듈 그리고 방출 시스템 등이 있다.
<br>

**저속/내고장(fault-tolerant) CAN 하드웨어** 

저속/내고장 CAN 네트워크 또한 두 개의 와이어로 실행되며, 최고 125 kb/s 속도로 디바이스와 통신하며, 내고장 기능이 있는 트랜시버를 제공한다.      

저속/내고장 CAN 디바이스는 CAN B 및 ISO 11898-3으로도 알려져 있으며, 자동차에서의 일반적인 저속/내고장 기기에는 안락장치가 있다.      

차량의 문을 열고 닫을 때의 강도를 고려하여 차량의 문을 통과해야 하는 와이어는 저속/내고장이다. 또한, 브레이크 등과 같이 강화된 보안 레벨이 요구되는 경우, 저속/내고장 CAN은 그 해결책이 될 수 있다.      

<br>

**단일 와이어 CAN 하드웨어** 

단일 와이어 CAN 인터페이스는 최고 33.3 kb/s (고속 모드에서는 88.3 kb/s) 속도로 디바이스와 통신한다.      

단일 와이어 CAN의 다른 명칭은 SAE-J2411, CAN A 및 GMLAN이다.  차량 내 일반적인 단일 와이어 디바이스는 고성능을 요구하지 않는다.       

일반적인 어플리케이션에는 좌석과 거울 조정기 등의 안락 장치가 있다.      

<br>

**소프트웨어 선택가능한 CAN 하드웨어**

NI사의 CAN 하드웨어 제품를 사용하여 소프트웨어 선택가능한 CAN 인터페이스를 구성하여 모든 온보드 트랜시버 (고속, 저속/내고장 또는 단일 와이어 CAN)를 사용할 수 있다. 소프트웨어 선택가능한 CAN 하드웨어를 사용하면, 사용자 고유의 외부 CAN 트랜시버를 선택할 수 있다.

<br>
<br>

### 메시지 프레임 구조

CAN 프레임은 여러 개의 비트 필드로 구성된다.
<br>

<p align="center"><img width="1699" height="999" alt="Image" src="https://github.com/user-attachments/assets/cf6c81b0-8b07-4f31-ad15-85f04fe9b954" /></p>

<br>

| 필드명 | 크기 | 설명 |
| --- | --- | --- |
| SOF (Start of Frame) | 1비트 | 프레임의 시작을 알리는 필드 |
| Arbitration Field | 11비트 또는 29비트 | 메시지의 우선순위 및 식별을 위한 필드 |
| Control Field | 6비트 | 데이터 길이 정보를 포함하는 필드 |
| Data Field | 0-8바이트 | 실제 전송할 데이터를 담는 필드 |
| CRC (Cyclic Redundancy Check) | 16비트 | 오류 검출을 위한 체크섬 필드 |
| ACK (Acknowledgement) | 2비트 | 수신 확인 필드 |
| EOF (End of Frame) | 7비트 | 프레임의 끝을 알리는 필드 |



<br>
<br>

### CAN 통신의 취약점


<br>

CAN 통신의 주요 보안 문제는 노드(ECU)가 이미 공격자에게 장악되었을 경우 발생한다.

<br>

**데이터 프레임 위변조**

- CAN Bus에서는 송신자 인증이 없기 때문에 공격자가 ECU를 조작하여 임의의 메시지를 전송할 수 있다.    
- 조향, 브레이크, 가속 등의 중요한 ECU 메시지를 조작하면 자동차 제어권을 탈취할 수 있다.     
- 예시: 악성 장치가 CAN 네트워크에 연결되어 브레이크프리 ECU로 "브레이크 해제" 명령을 지속적으로 전송하면, 운전자가 제동을 시도해도 반응하지 않는다.      

<br>

**Bus-Off 공격**

- CAN 표준의 설계 결함을 이용한 공격 방식이다.    
- 특정 ECU를 반복적으로 충돌시키면서 TEC 값을 증가시켜 네트워크에서 강제로 제거한다.     
- 메시지 충돌 시 동작: 공격자는 Data Field를 Dominant(0)로만 구성하여 전송한다.       
피해자의 Recessive (1) 비트와 충돌 시, CAN 버스의 물리적 특성상 Dominant (0)가 우선권을 가진다.           
피해자는 자신이 보낸 값과 버스 상태가 다름을 감지하여 에러 발생, TEC 증가한다.              
- 예시: 공격자가 특정 ECU에 지속적으로 충돌 프레임을 보내 TEC 값을 255 이상으로 증가시키면, 해당 ECU는 Bus-Off 상태가 되어 더 이상 네트워크에 참여할 수 없다.
  
<br>

**공격 탐지 어려움**

<br>

- CAN 프로토콜은 송신자 인증 및 암호화 기능이 없기 때문에 공격자가 쉽게 프레임을 위조 가능하다.
- 정당한 ECU가 보낸 것처럼 위장된 메시지를 탐지하기 어렵다.
- 예시: 해커가 OBD-II 포트를 통해 자동차 내부 네트워크에 접속하여 가짜 속도 정보를 계기판 ECU에 전송하면, 운전자는 실제 속도와 다른 값을 보게 된다.

<br>

### 주제를 조사하고나서 느낌 점




### **[참고 자료]**

[[차량통신] 자동차 통신의 종류 및 기본 개념 : 네이버 블로그](https://m.blog.naver.com/wjdzhdzhd/222020797962)

[[2주차] CAN 통신의 이해: CAN Protocol 및 통신 시스템 & CAN Dos Attack](https://alim11.tistory.com/314)

[원문보기 - ScienceON](https://scienceon.kisti.re.kr/commons/util/originalView.do?cn=CFKO200634741466208&oCn=NPAP08116964&dbt=CFKO&journal=NPRO00290005)

[CAN 통신 프로토콜](https://mokpo.tistory.com/857)

[자동차 통신 CAN (Controller Area Network) 통신 소개 및 동작 방법 :: 자율주행 자동차](https://weeklylife.tistory.com/26)
