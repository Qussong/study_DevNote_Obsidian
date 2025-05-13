# TcpListener
TCP 서버를 구현할 때 사용하는 클래스
클라이언트의 연결 요청을 수락하고 데이터를 송수신할 수 있도록 관리한다.
포트에서 클라이언트의 연결을 기다리고, 연결된 클라의 데이터를 송수신 가능
```csharp
TcpListener servver = new TcpListener(IPAddress.Any, port);
```
## 주요함수
1. `Start()` : 지정된 포트에서 서버 시작
2. `Stop()` : 서버 중지 
3. `AcceptTcpClient()` : 클라의 연결을 수락하고 TcpClient 객체 반환
4. `BeginAcceptTcpClient(callback, state)` : 비동기 방식으로 클라이언트 연결 수락
5. `Pending()` : 대기 중인 클라의 요청이 있는지 확인

---
# EndAcceptTcpClient(IAsyncResult)
BeginAcceptTcpClient()
