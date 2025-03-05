# Transport Layer
message : Application Layer - Application Layer 
segment : Transport Layer - Transport Layer
packet : Network Layer - Network Layer
frame : Link Layer - Link Layer

Segment Header
1. source port 16 bit
2. dest port 16 bit
3. length 16 bit
4. checksum 16 bit

> port의 개수가 66xxx인 이유 0 ~ 2^16 -1


segment = data + header(source port, destination port)

## Multiplexing / Demultiplexing
- **Multiplexing**
하나의 Peer의 Application Layer에서부터의 세그먼트들을 한꺼번에 합치는 과정

- **DeMultiplexing**
다른 Peer의 Physical 계층에서 Application Layer까지 올라갈 때의 합쳐진 세그먼트를 분할 하는 과정

### UDP의 demux
destination IP, destination port 만을 가지고 demux를 진행하게 된다.

### TCP의 demux
source IP, source port, destination IP, destination port를 모두 고려하여 demux를 진행하게 된다.
**Connection oriented**

## UDP
**unreliable**

but,  
**multiplexing**
**checksum을 통해 에러는 잡아준다**

## TCP
### Reliable한 Data Transfer의 원리
Transport의 위에 계층까지는 reliable 하지만 아래의 계층들을 실질적으로 unreliable하다.

### RDT 1.0 
아래의 채널들이 전부 안전하다고 가정하는 경우, 문제가 생기지 않는다.

### RDT 2.0 
ERROR의 발생 
ACK: 정상 수신
NAK: 비정상 수신

Sender의 입장에서 
1. send
2. sender ACK/NAK 기다림
3. sender NAK 수신, send 재전송

- Error Detection
CheckSum추가 Reciever에서 에러를 발생한 지 확인한 후 
- FeedBack
- retransmission

### RDT  2.1
패킷 손상의 발생
1. send
2. sender ACK/NAK 기다림 

sequence number 도입
모든 패킷에 sequence number을 붙여 중복여부(duplicated)를 확인한다

OverHead를 방지하기 위하여 sequence number의 개수를 최소화 해야한다.
1개씩 받을때는 seq.size = 2[0,1];

### RDT 2.2 
패킷 유실의 발생


### RDT 3.0
Packet Loss까지 가정해야하는 것이기 때문에 Timer 도입
Timer를 길게 잡는 경우 

