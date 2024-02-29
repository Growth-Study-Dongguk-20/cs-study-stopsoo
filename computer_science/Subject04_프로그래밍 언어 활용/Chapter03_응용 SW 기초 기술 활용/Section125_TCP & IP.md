## CS Study - Section125 TCP/IP
### ✏️ Study
#### 💡 TCP/IP의 개요(Transmission Control Protocol/Internet Protocol)
- 인터넷에 연결된 서로 다른 기종의 컴퓨터들이 데이터를 주고 받을 수 있도록 하는 표준 프로토콜.
- 특징
  - 1960년대 말 ARPA에서 개발해, ARPANET(1972)에서 사용하기 시작.
  - TCP/IP는 UNIX의 기본 프로토콜로 사용되었음. 현재는 인터넷 범용 프로토콜로 사용됨.
- **`TCP(Transmission Control Protocol)`**
  - OSI 7계층의 **전송 계층(4)** 에 해당.
  - 신뢰성 있는 연결형 서비스를 제공.
  - 패킷의 다중화, 순서 제어, 오류 제어, 흐름 제어 기능을 제공.
  - 스트림(stream) 전송 기능을 제공.
- **`IP(Internet Protocol)`**
  - OSI 7계층의 **네트워크 계층(3)** 에 해당.
  - 데이터그램을 기반으로 하는 비연결형 서비스를 제공.
  - `Best Effort 원칙`에 따른 전송 기능을 제공.
    - `Best Effort 원칙`❓최선의 노력은 하지만 전송 결과는 보장하지 않음. ➡️ **"비신뢰성 전송"**
  - 패킷의 분해/조립, 주소 지정, 경로 선택 기능을 제공.
  - 헤더의 길이는 20Byte ~ 60Byte.
<br>

#### 💡 TCP/IP의 구조
- **네트워크 액세스 계층**
  - OSI : 물리 계층(1), 데이터 링크 계층(2)
  - 실제 데이터(프레임)를 송/수신하는 역할.
  - Ethernet, IEEE 802, HDLC, X.25, RS-232C, ARQ
- **인터넷 계층**
  - OSI : 네트워크 계층(3)
  - 데이터 전송을 위한 주소 지정, 경로 설정을 제공.
  - IP, ICMP, IGMP, ARP, RARP
- **전송 계층**
  - OSI : 전송 계층(4)
  - 호스트들 간의 신뢰성 있는 통신을 제공.
  - TCP, UDP
- **응용 계층**
  - OSI : 세션 계층(5), 표현 계층(6), 응용 계층(7)
  - 응용 프로그램 간의 데이터 송/수신을 제공.
  - TELNET, FTP, SMTP, SNMP, DNS, HTTP
<br>

#### 💡 네트워크 액세스 계층의 주요 프로토콜
- `Ethernet(IEEE 802.3)` : CSMA/CD 방식의 LAN 
- `IEEE 802` : LAN을 위한 표준 프로토콜
- `HDLC` : 비트 위주의 데이터 링크 제어 프로토콜
- `X.25` : 패킷 교환망을 통한 DTE와 DCE 간의 인터페이스를 제공하는 프로토콜
- `RS-232C` : 공중 전화 교환망(PSTN)을 통한 DTE와 DCE 간의 인터페이스를 제공하는 프로토콜
<br>

#### 💡 인터넷 계층의 주요 프로토콜
- `IP(Internet Protocol)` : 전송할 데이터에 주소를 지정하고, 경로를 설정하는 기능. 비연결형인 데이터그램 방식을 사용하기 때문에 신뢰성이 보장되지 않음.
- `ICMP(Internet Control Message Protocol, 인터넷 제어 메시지 프로토콜)` : IP와 조합하여 통신 중에 발생하는 오류 처리, 전송 경로 변경 등을 위한 제어 메시지를 관리.
- `IGMP(Internet Group Management Protocol, 인터넷 그룹 관리 프로토콜)` : 멀티캐스트를 지원하는 호스트, 라우터 사이에서 멀티캐스트 그룹 유지를 위해 사용됨.
- `ARP(Address Resolution Protocol, 주소 분석 프로토콜)` : 호스트의 IP 주소를 호스트와 연결된 네트워크 접속 장치의 물리적 주소(MAC Address)로 변경.
- `RARP(Reverse Address Resolution Protocol)` : ARP와 반대로 물리적 주소를 IP 주소로 변환하는 기능.
<br>

#### 💡 전송 계층의 주요 프로토콜
- `TCP(Transmission Control Protocol)`
  - 양방향 연결(Full Duplex Connection)형 서비스를 제공.
  - 가상 회선 연결(Virtual Circuit Connection) 형태의 서비스를 제공.
  - 스트림 위주의 전달(패킷 위주).
  - 신뢰성 있는 경로를 확립. 메시지 전송을 감독.
  - 순서 제어, 오류 제어, 흐름 제어 기능.
  - 패킷 분실, 손상, 지연 or 틀린 순서 등 발생 시, 투명성이 보장되는 통신을 제공.
  - TCP 프로토콜의 헤더는 최대 100Byte까지 확장 가능.
- `UDP(User Datagram Protocol)`
  - 데이터 전송 전에 연결을 설정하지 않는 비연결형 서비스 제공.
  - TCP에 비해 상대적으로 단순한 헤더 구조. ➡️ 적은 오버헤드, 흐름 제어/순서 제어가 없어 빠른 전송 속도.
  - 빠른 속도가 필요한 경우, 동시에 여러 사용자에게 데이터를 전달할 경우, 정기적으로 반복해 전송할 경우에 사용.
  - 실시간 전송에 유리.
  - **신뢰성보다는 속도가 중요시**되는 네트워크에서 사용.
- `RTCP(Real-Time Control Protocol)`
  - RTP(Real-time Transport Protocol) 패킷의 전송 품질을 제어하기 위한 제어 프로토콜.
  - 세션에 참여한 각 참여자들에게 주기적으로 제어 정보를 전송.
  - 하위 프로토콜은 데이터 패킷과 제어 패킷의 다중화(Multiplexing)를 제공.
  - 데이터 전송을 모니터링. 최소한의 제어와 인증 기능만을 제공.
<br>

#### 💡 응용 계층의 주요 프로토콜
- `FTP(File Transfer Protocol)` : 컴퓨터와 컴퓨터 or 컴퓨터와 인터넷 사이에서 파일을 주고 받을 수 있도록 하는 원격 파일 전송 프로토콜.
- `SMTP(Simple Mail Transfer Protocol)` : 전자 우편을 전송하는 프로토콜.
- `TELNET`
  - 먼 거리에 있는 컴퓨터에 접속해 자신의 컴퓨터처럼 사용할 수 있도록 해주는 서비스.
  - 프로그램을 실행하는 등, 시스템 관리 작업을 할 수 있는 가상의 터미널(Virtual Terminal) 기능을 수행.
- `SNMP(Simple Network Management Protocol)`
  - TCP/IP의 네트워크 관리 프로토콜.
  - 라우터, 허브 등 네트워크 기기의 네트워크 정보를 네트워크 관리 시스템에 보내는 데 사용되는 표준 통신 규약.
- `DNS(Domain Name System)` : 도메인 네임을 IP 주소로 매핑(mapping)하는 시스템.
- `HTTP(HyperText Transfer Protocol)` : 월드 와이드 웹(WWW)에서 HTML 문서를 송수신하기 위한 표준 프로토콜.
- `MQTT(Messagge Queuing Telemetry Transport)` : 발행-구독 기반의 메시징 프로토콜. IoT 환경에서 자주 사용됨.
