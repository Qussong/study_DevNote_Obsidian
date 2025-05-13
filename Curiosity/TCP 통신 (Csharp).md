# TcpClient
C#에서 **TCP (Transmission Control Protocol)** 연결을 관리하는 클래스
이를 통해 클라이언트는 서버와 연결을 맺고 데이터를 주고받을 수 있다.
신뢰성 있는 데이터 전송을 보장하는 **프로토콜**로, 네트워크 통신에서 많이 사용된다.

---
# GetStream()
TcpClient 에서 제공하는 메서드
서버와의 데이터 송수신을 위해 **네트워크 스트림**을 가져오는 역할을 한다.
```csharp
TcpClient client = new TcpClient("127.0.0.1", 8080);  // 서버 연결
NetworkStream stream = client.GetStream();  // 네트워크 스트림 가져오기
```
NetworkStream 객체를 반환하며 이를 통해 데이터를 Read(), Write() 로 송수신할 수 있다.
스트림을 통해 서버와 클라간의 통신이 이루어진다.

---
# 프로토콜 (Protocol)
컴퓨터나 네트워크 장치가 서로 데이터를 주고받기 위해 따르는 규칙과 약속
네트워크에서 올바르게 정보를 전달하기 위해 정해진 규칙의 일종

## 프로토콜의 종류
1. TCP
2. UDP
3. HTTP/HTTPS
4. FTP

---
# 네트워크 스트림 (Network Stream)
데이터를 연속적으로 주고받는 방식을 의미한다.
스트림을 통해 데이터를 읽거나 쓸 수 있다.

## 특징
1. 데이터를 순차적으로 전송
2. 네트워크를 통해 데이터를 주고받을 때 사용
   -> **데이터의 신뢰성**과 **순차적인 흐름을 보장**하기에 TCP 기반에서 많이 사용
3. 비트 또는 바이트 단위로 데이터를 처리함

```csharp
TcpClient client = new TcpClient("127.0.0.1", 8080);  // 서버 연결
NetworkStream stream = client.GetStream();  // 네트워크 스트림 가져오기

byte[] message = Encoding.UTF8.GetBytes("Hello, Server!");
stream.Write(message, 0, message.Length);  // 데이터 전송

stream.Close();
client.Close();
```

---
# 패킷 (Packet)
네트워크에서 데이터를 작은 조각으로 나누어 전송하는 단위
컴퓨터는 데이터를 주고받을 때, 한번에 큰 데이터를 전송하는 것이 아닌 **작은 패킷 단위로 쪼개서 보내고, 다시 조립하여 원본 데이터를 복구**하는 방식으로 동작한다.

## 패킷의 구성
일반적으로 **헤더**와 **페이로드**로 구성된다.

1. 헤더 (Header)
	- 패킷이 어디서 왔고, 어디로 가야 하는지 정보를 담고 있다.
	- 송신자 IP, 수신자 IP, 패킷 번호, 오류 검출 코드 등이 포함됨
2. 페이로드 (Payload)
	- 실제 전송할 데이터가 포함된 부분

---
# BitConverter.ToSingle()
바이트 배열을 float 형식으로 변환하는 메서드
```csharp
BitConverter.ToSingle(byte[] buffer, in startIndex)
// buffer : 변환할 바이트 배열
// startIndex : 변환을 시작할 위치 (인덱스)
```

## BitConverter
숫자 데이터(int, float, double)를 바이트 배열로 변환하거나, 반대로 바이트 배열을 숫자로 변환하는 기능을 제공
네트워크 통신, 파일 저장, 바이너리 데이터 처리 등에 활용됨
![600](./img/Pasted%20image%2020250513094822.png)
기본적으로 **리틀 엔디언(Little Endian)** 방식으로 변환한다.
엔디언 차이를 고려하지 않으면, 네트워크 통신이나 파일 저장 시 데이터가 잘못 해석될 가능성이 있다.

---
# Encoding.UTF8.GetBytes()
문자열을 UTF-8 형식의 바이트 배열로 변환하는 메서드
문자열은 가변 길이를 가지며, 단순한 숫자 변환이 아닌 문자 인코딩이 필요함
`BitConverter` 로는 직접 문자열을 반환할 수 없기 때문에 사용된 대체 방법

## 역할
텍스트를 네트워크로 전송하거나 파일에 저장할 때 올바른 문자 인코딩을 유지하면서 데이터를 변환할 수 있다.
```csharp
string text = "Hello, 세계!";
byte[] bytes = Encoding.UTF8.GetBytes(text);
Console.WriteLine(BitConverter.ToString(bytes));
```

## 문자열 변환
바이트 배열에서 문자열로 변환하는 방법은 두가지며, 각각의 목적이 다르다.
1. Encoding.UTF8.GetString(byte[])
	바이트 배열을 실제 문자열로 복원할 때 사용한다.
	네트워크 송수신, 파일처리 등에서 사용
	```csharp
	byte[] bytes = Encoding.UTF8.GetBytes("Hello, 세계!");  // 문자열 → 바이트 배열
	string result = Encoding.UTF8.GetString(bytes);  // 바이트 배열 → 문자열
	Console.WriteLine(result);  // 출력: "Hello, 세계!"
	```

2. BitConverter.ToString(byte[])
	바이트 배열을 사람이 읽기 쉬운 16진수 (Hex) 문자열로 변환하는 역할을 한다.
	```csharp
	byte[] bytes = Encoding.UTF8.GetBytes("Hello");
	string hexString = BitConverter.ToString(bytes);
	Console.WriteLine(hexString);  // 출력: "48-65-6C-6C-6F"
	```

