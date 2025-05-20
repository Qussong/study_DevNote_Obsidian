
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
눈의 양을 조절할 수 있는데, Edit Sprite 상태에서 전체 정점을 선택, 이후 Element Inspector 창에서 Height 값을 조절하면 눈의 양을 설정하 수 있다. (이때, Collider 의 위치는 자동으로 따라온다)</br>
![300](./img/Pasted%20image%2020250520171138.png)

---
# Edge Collider 2D
Closed Shape 전체에 콜라이더가 생성됨</br>
![](./img/Pasted%20image%2020250520162419.png)</br>
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
