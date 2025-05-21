
# Closed Shape
전체가 이어져서 반복되는 형태를 의미한다.</br>
`2D Object -> Sprite Shape -> Closed Shape` </br>
![](./img/Pasted%20image%2020250520155538.png)</br>
**Sprite Shape Controller 컴포넌트**가 추가되어 있고, 자동으로 Profile 이 Sprite Shape Profile 로 설정되어 있다.</br>

---
# Sprite Shape Profile
`우클릭 -> Create -> 2D -> Sprite Shape Profile`</br>
![400](./img/Pasted%20image%2020250521105523.png)</br>

---
# Sprite Shape Controller
`Profile/Edit Spline` 으로 정점 추가 및 위치 수정을 할 수 있다.</br>
![](./img/Pasted%20image%2020250520160628.png)</br>
생성된 edge collider 의 위치때문에 공이 공중에 떠 있는것처럼 보인다.</br>
![300](./img/Pasted%20image%2020250520164318.png)</br>
Sprite Shape Controller 의 속성중 **Collider/Offset** 을 조정하면 Collider 의 위치를 수정할 수 있다.</br>
![300](./img/Pasted%20image%2020250520170220.png)</br>
눈의 양을 조절할 수 있는데, Edit Sprite 상태에서 전체 정점을 선택, 이후 Element Inspector 창에서 Height 값을 조절하면 눈의 양을 설정하 수 있다. (이때, Collider 의 위치는 자동으로 따라온다)</br>
![300](./img/Pasted%20image%2020250520171138.png)

---
# Edge Collider 2D
Closed Shape 전체에 콜라이더가 생성됨</br>
![](./img/Pasted%20image%2020250520162419.png)</br>
생성된 Edge Collider 의 위치 수정은 Sprite Shape Controller 의 offset 값을 통해 수정한다.</br>
Edit Spline 으로 Closed Shape 의 형태를 변경하여도 그에 맟줘 Collider가 수정된다.</br>

---
# Dynamic Sprite
`우클릭 -> 2D Object -> Physics -> Dynamic Sprite`</br>
해당 과정을 통해 객체를 생성하면 자동으로 Collider 와 RigidBody가 추가된 채로 Sprite가 생성된다.</br>

---
# Sprite Editor
Closed Shape 에 사용한 Shape Profile 의 눈 이미지를 보면 양 옆이 둥글게 되어 있다.</br>
![](./img/Pasted%20image%2020250520171408.png)</br>
하지만, 결과를 보면 저런 둥근 부분이 보이지 않는데 이는 Sprite의 Inspector 창에서 Sprite Editor 를 통해 사용하고자 하는 위치를 지정해줬기 때문이다.</br>
![](./img/Pasted%20image%2020250520171343.png)</br>
만약, 위와 같이 Sprite 를 수정하지 않았다면 아래와 같은 결과가 나온다.</br>
![](./img/Pasted%20image%2020250520171750.png)</br>

---
# Cinemachine
여러 대의 카메라를 동작할 수 있게 해주는 패키지</br>
Project 창의 Packages 폴더에는 현재 프로젝트에 설치되어 있는 패키지 목록을 확인 할 수 있다.</br>
하지만, Cinemachine 에 관련된 패키지는 확인할 수 없는데 모든 패키지를 가지고 있게되면 프로젝트의 크기가 너무 커지기 대문이다.</br>
필요한 패키지들은 `Window -> Package Manager` 를 통해 설치할 수 있다.</br>
`Unity Registry` 창에서 cinemachine 을 검색하여 설치한다.</br> 
![](./img/Pasted%20image%2020250520173008.png)</br>
`우클릭 -> Cinemachine -> Virtual Camera`과정을 통해 Virtaul Camera 객체를 생성한다.</br>
그러면 아래와 같이 Main Camera 객체에 자동으로 CinemachineBrain 컴포넌트가 추가된다. Hierachy 창에서도 Main Camera 객체옆에 CinemachineBrain 마크가 생긴것을 확인할 수 있다.</br>
![](./img/Pasted%20image%2020250520173750.png)</br>
![](Pasted%20image%2020250520173826.png)</br>
생성한 Virtual Camera 객체의 CinemachineVirtualCamera 컴포넌트를 확인해보면 다양한 옵션들이 존재한다.</br>
그 중 Body 의 값을 `Transposer(기본값) -> Framing Transposer`로 변경해준다.</br>
이는, 게임 내 특정 대상을 프레이밍해서 가상 카메라의 바디를 이동하겠다는 설정이다.</br>
CinemachineVirtualCamera 컴포넌트를 보면 Follow 라는 필드가 있는데, 해당 필드가 가상 카메라의 바디가 추적하는 객체를 설정하는 필드다.</br>
유니티에서 팔로우 카메라를 지정할 수 있는 가장 간단한 방법이다.</br>
![](./img/Pasted%20image%2020250520174013.png)</br>
게임의 특성상 카메라의 초점이 플레이어의 앞에 위치해야 할 경우가 존재한다.</br>
이럴 경우 CinemachineVirtualCamera 컴포넌트의 Body/Screen X 의 값을 조장히면 된다.</br>
↓ 카메라의 초점이 Circle 의 앞에 위치해있다.</br> 
![](./img/Pasted%20image%2020250521112752.png)</br>

---
# Player Character
Player 객체를 생성하는데 해당 객체의 월드상의 형태는 Sprite Renderer의 Sprite에 설정된 이미지에 의해 결정된다.</br>
```
[Character Hierarchy]
Player Van (Empty Object)
└─ Boarder_Top (Sprite Renderer)
└─ Boarder_Bottom (Sprite Renderer)

[Components]
- Rigidbody 2D
- Capsule Collider 2D
- Circle Collider 2D
```
![500](./img/Pasted%20image%2020250521115911.png)</br>
Player 캐릭터의 RigidBody2D 컴포넌트에서 충돌을 감지하는 필드인 Collision Detection 의 값을 `Discrete(기본값) -> Continuous` 로 변경해줘야 지속적으로 충돌 영역을 감지한다.</br>


---
# Surface Effector 2D
이를 사용하기위해선 Edge Collider 2D의 **Used By Effector** 설정을 활성화시켜줘야한다.</br>
![](./img/Pasted%20image%2020250521131135.png)</br>
- Speed : 컨베이어 벨트가 얼마나 빨리 움직이는가?
- Force Scale : 중력에 저항해서 게임 오브젝트에 얼마나 힘을 가하는지의 정도

---
# Torque
RigidBody 는 오브젝트가 유니티의 물리 법칙에 따라 반응하고 이동하도록 해주는 기능이다.</br>
Torque 를 적용하기위해선 RigidBody 컴포넌트로 접근해야 한다.</br>
```csharp
Rigidbody2D rb2d = GetComponent<Rigidbody2D>();
```

```csharp
[SerializeField] float torqueAmount = 1.0f;

void Update()
{
	if(Input.GetKey(KeyCode.LeftArrow))
	{
		rb2d.AddTorque(torqueAmount);
	}
}
```
- 양(+)의 방향 회전 = 반시계 방향 회전
- 음(-)의 방향 회전 = 시계 방향 회전

---
# Namespace & SceneManager
네임스페이스는 여러개의 클래스를 가지고 있고, 클래스는 여러 개의 메소드를 가지고 있다.</br>
![](./img/Pasted%20image%2020250521163434.png)</br>
SceneManager 를 사용하기위해선 UnityEngine.SceneManagement 를 참조해야한다.
```csharp
using UnityEngine.SceneManagement;
```
SceneManager.LoadScene() 을 통해서 원하는 Scene 을 불러올 수 있다.
```csharp
if(collision.tag == "Player")
{
    Debug.Log("You finished!");
    SceneManager.LoadScene(0);
}
```

---
# Invoke()
일정 시간이후 지정한 함수를 호출할 수 있는 기능을 제공하는 함수
```csharp
float delay = 1f;  // 딜레이 시간
Invoke("NameOfMethod", delay);
// NameOfMethod : delay 시간 이후 호출할 함수의 이름
```

---
# Particle Effect
`우클릭 -> Effect -> Particle System` 을 통해 생성한다.
![](./img/particleSystem.gif)
