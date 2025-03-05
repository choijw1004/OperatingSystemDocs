# Computer Network Basic

### Closer look at network structure
- network edge
어플리케이션, 호스트
- network core
라우터, 네트워크의 네트워크
- access network, physical media
communication link

### network edge
- end system (hosts)
application 
- client / server model 
- peer to peer model 

### 데이터 통신 서비스 
connection oriendted service
1. TCP 
- **reliable**: 신뢰성을 보장하며 메시지의 유실을 방지한다.
- **in order byte** 
- **flow control**: 보내는 사람의 속도에 맞춰서 조절해서 보내주게 된다.
- **congestion control**: 혼잡 제어
**but, 비용이 TCP에 비해 상대적으로 많이 든다** 
2. UDP
- **No connection Control**
- **unreliable**
- **no flow control** 
- **no congestion control** 
**but, 속도가 TCP에 비해 상대적으로 빠르다**
 
### Protocol
메시지를 전송하기 위한 규약. sender와 receiver의 protocol이 일치해야만 한다.

### Network Core
라우터가 위치하고 있음.
- **Circuit switching**
출발지에서 목적지의 위치를 지정해놓고 중간에 사용자가 개입하는 방식 
- **Packet switching** 
user가 보내는 패킷을 포워딩해주는 방식

### Packet Switching VS Circuit Swiching
가령 1Mbps 대역폭을 가진 링크에선 1명의 user가 100kb/s를 점유하고있는 경우 Circuit Swiching 방식은 10명, Packet Swiching 은 대략 35명이 이용이 가능하다.

###  딜레이가 생기는 이유
패킷이 전송될 때 다음과 같은 프로세스가 발생한다.
1. **패킷 검사 -> 패킷 목적지 결정 delay**
- 개선할 수 있는 방법
라우터 성능 개선
2. **queueing delay**
라우터 앞단에는 속도, 대역폭을 제어하기 위한 buffer가 존재한다.
- 개선할 수 있는 방법
현실적인 방법의 부재로 대부분의 delay는 queueing delay

3. **transmition delay**
비트의 처음과 끝이 나가야 전송이 되었기 때문에 link 대역폭 / 패킷 대역폭 만큼 transmition delay가 발생한다. 
- 개선할 수 있는 방법
대역폭의 성능 개선

4. **propagation delay**
패킷이 완벽하게 도착할 떄까지의 걸리는 딜레이  
link 대역폭 / 빛의 속도

### 패킷 유실
if(queue.size() < queueing size) 일때 패킷 유실이 일어난다. 이런 경우 TCP는 재전송을 하게 한다. 패킷 유실이 발생하는 경우 sender가 재전송하게 된다. sender, reciever을 제외한 라우터들은 dummy core로 정의한다.
