
# Closed Shape
전체가 이어져서 반복되는 형태를 의미한다.</br>
`2D Object -> Sprite Shape -> Closed Shape` </br>
![](./img/Pasted%20image%2020250520155538.png)</br>
**Sprite Shape Controller 컴포넌트**가 추가되어 있고, 자동으로 Profile 이 Sprite Shape Profile 로 설정되어 있다.</br>

---
# Sprite Shape Profile
`우클릭 -> Create -> 2D -> Sprite Shape Profile`</br>

---
# Sprite Shape Controller
`Profile/Edit Spline` 으로 정점 추가 및 위치 수정을 할 수 있다.</br>
![](./img/Pasted%20image%2020250520160628.png)</br>
생성된 edge collider 의 위치때문에 공이 공중에 떠 있는것처럼 보인다.</br>
![300](./img/Pasted%20image%2020250520164318.png)</br>
Sprite Shape Controller 의 속성중 **Collider/Offset** 을 조정하면 Collider 의 위치를 수정할 수 있다.</br>
![300](./img/Pasted%20image%2020250520170220.png)</br>

---
# Edge Collider 2D
Closed Shape 전체에 콜라이더가 생성됨</br>
![](./img/Pasted%20image%2020250520162419.png)</br>
Edit Spline 으로 Closed Shape 의 형태를 변경하여도 그에 맟줘 Collider가 수정된다.</br>

---
# Dynamic Sprite
`우클릭 -> 2D Object -> Physics -> Dynamic Sprite`</br>
해당 과정을 통해 객체를 생성하면 자동으로 Collider 와 RigidBody가 추가된 채로 Sprite가 생성된다.</br>
