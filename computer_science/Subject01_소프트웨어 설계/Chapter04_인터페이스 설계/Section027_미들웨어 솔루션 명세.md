## CS Study - Section027 미들웨어 솔루션 명세
### ✏️ Study
#### 💡 미들웨어(Middleware)의 개념
- 의미
  - `미들(Middle)` + `소프트웨어(Software)`
- 특징
  - 분산 컴퓨팅 환경에서 서로 다른 기종 간의 하드웨어나 프로토콜, 통신 환경 등을 연결하여 운영체제와 응용 프로그램, 또는 서버와 클라이언트 사이에서 원만한 통신이 이루어지도록 다양한 서비스를 제공.
  - 표준화된 인터페이스를 제공 ➡️ 시스템 간 데이터 교환에 일관성을 보장.
  - 위치 투명성을 제공.
    - `위치 투명성`❓시스템의 논리적인 명칭 만으로 액세스할 수 있는 것.
  - 시스템들을 1:1, 1:N, N:M 등의 여러 가지 형태로 연결 가능.
- 종류
  - DB, RPC, MOM, TP-Monitor, ORB, WAS 등
<br>

#### 💡 DB(DataBase)
- 데이터베이스 벤더에서 제공하는 `클라이언트`에서 원격의 `데이터베이스`와 연결하기 위한 미들웨어.
- DB를 사용하여 시스템을 구축하는 경우 `2-Tier 아키텍처`라고 함.
- Ex> 마이크로소프트의 ODBC, 볼랜드의 IDAPI, 오라클의 Glue 등
<br>

#### 💡 RPC(Remote Procedure Call; 원격 프로시저 호출)
- 응용 프로그램의 `프로시저`를 사용하여 **원격 프로시저를 마치 로컬 프로시저처럼 호출**하는 방식의 미들웨어.
- Ex> 이큐브시스템스의 Entrea, OSF의 ONC/RPC 등
<br>

#### 💡 MOM(Message Oriented Middleware; 메시지 지향 미들웨어)
- 메시지 기반의 `비동기형 메시지`를 전달하는 방식의 미들웨어.
- **이기종 분산 데이터 시스템의 데이터 동기**를 위해 많이 사용됨.
- 서로 다른 플랫폼에서 독립적으로 실행되는 소프트웨어 간의 상호 작용을 통해 **하나의 통합된 시스템처럼 동작되게 함**.
- EX> IBM의 MQ, 오라클의 Message Q, JCP의 JMS 등
<br>

#### 💡 TP-Monitor(Transaction Processing Monitor; 트랜잭션 처리 모니터)
- 온라인 트랜잭션 업무에서 `트랜잭션을 처리 및 감시`하는 미들웨어.
- 사용자 수가 증가해도 빠른 응답 속도를 유지해야 하는 업무에 주로 사용됨.
- Ex> 오라클의 tuxedo, 티맥스 소프트의 tmax 등

##### 🔖 트랜잭션 처리
- 온라인 업무 처리 형태의 하나.
- 네트워크 상의 여러 이용자가 실시간으로 데이터베이스의 데이터를 갱신하거나 검색하는 등의 단위 작업을 처리하는 방식.
- 온라인 트랜잭션 처리(OLTP; Online Transaction Processing)이라고도 함.
<br>

#### 💡 ORB(Object Request Broker; 객체 요청 브로커)
- 객체 지향 미들웨어.
- 코바(CORBA) 표준 스펙을 구현한 미들웨어.
- Ex> Micro Focus의 Orbix, OMG의 CORBA 등
<br>

#### 💡 WAS(Web Application Server; 웹 애플리케이션 서버)
- 정적인 콘텐츠를 처리하는 웹 서버와 달리, 사용자의 요구에 따라 변하는 `동적인 콘텐츠를 처리`하기 위해 사용되는 미들웨어.
- HTTP 세션 처리를 위한 웹 서버 기능 뿐만 아니라, 미션-크리티컬한 기업 업무까지 JAVA, EJB 컴포넌트 기반으로 구현이 가능.
- Ex> 오라클의 WebLogic, IBM의 WebSphere 등
<br>