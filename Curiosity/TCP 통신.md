# TcpClient
C#에서 **TCP (Transmission Control Protocol)** 연결을 관리하는 클래스
이를 통해 클라이언트는 서버와 연결을 맺고 데이터를 주고받을 수 있다.
신뢰성 있는 데이터 전송을 보장하는 **프로토콜**로, 네트워크 통신에서 많이 사용된다.

## 1. GetStream()
TcpClient 에서 제공하는 메서드
서버와의 데이터 송수신을 위해 **네트워크 스트림**을 가져오는 역할을 한다.
```csharp
TcpClient client = new TcpClient("127.0.0.1", 8080);  // 서버 연결
NetworkStream stream = client.GetStream();  // 네트워크 스트림 가져오기
```
NetworkStream 객체를 반환하며 이를 통해 데이터를 Read(), Write() 로 송수신할 수 있다.
스트림을 통해 서버와 클라간의 통신이 이루어진다.

## 2.프로토콜 (Protocol)
컴퓨터나 네트워크 장치가 서로 데이터를 주고받기 위해 따르는 규칙과 약속
