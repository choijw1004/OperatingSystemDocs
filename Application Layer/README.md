# Application Layer

IP 주소와 포트를 통해 매핑 
포트 하나 당 하나의 프로세스를 매핑 시커준다. 
IP주소 + 포트번호를 클라이언트에서 입력하게되면 DNS를 통해 사이트에 접속할 수 있게 된다.

## 왜 공통된 포트를 사용할까? ex 80, 8080 
DNS는 IP 주소만 변환해주기 때문에 공통된 포트를 사용하게 됨

## TransPort Layer에서의 지원
**데이터 무결성**

## HTTP(Hyper Text Transfer Protocol)
- Request
- Response

- Transport Layer의 TCP를 사용하게 된다.
- **Staeless**

### Http Connections
1. non - persistent
connection을 재사용하지 않는 경우
2. persistent (Default)
connection을 맺고 재사용하게 되는 경우

## Socker Programming 

### Socket의 종류
- TCP Socket
- UDP Socket

### Socket Functions
Server: socket () -> bind() -> listen() -> accept()
Client: socket() -> connect() ->read(), write()


