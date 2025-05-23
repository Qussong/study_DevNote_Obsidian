# UI Canvas
UI = User Interface</br>
Text, Button, Slider, Menu, etc 을 포함한다.</br>
`우클릭 -> UI -> Canvas` 를 통해 생성할 수 있으며, 생성시 EventSystem 도 함께 생성된다.</br>
![](./img/Pasted%20image%2020250523093942.png)</br>
UI 요소의 Inspector 를 확인해보면, 일반 객체와 달리 **Standard Transform Component** 대신 **Rect Transform** 이 있다.</br>
![](./img/Pasted%20image%2020250523103644.png)</br>

---
# TextMeshPro
`Window ->Package Manager -> TextMeshPro`를 통해 추가해준다.</br>
Font 변경을 하기위해선 Font Asset 이 필요하다.</br>
`Window -> TextMeshPro -> Font Asset Creator` </br>
![500](./img/Pasted%20image%2020250523135316.png)</br>
설정할게 많아보이지만 SourceFont만 신경써주면 된다.</br>
SourceFont 를 설정하고 Generate Font Atlas 버튼을 클릭하면 Font Asset 이 생성된다.</br>
생성된 Font Asset 으로 변경해주면 Font 가 적용된다.</br>
![350](./img/Pasted%20image%2020250523140231.png)</br>
TextMeshPro의 색상 변경 옵션에서 Color Gradient 옵션을 활성화하면 추가 설정이 활성화된다.</br>
![350](./img/Pasted%20image%2020250523140709.png)</br>

---
# Button-TextMeshPro
`우클릭 -> UI -> Button-TextMeshPro` 를 선택하여 버튼을 생성할 수 있다.</br>
Button 의 Inspector 창에서 Interactable 옵션은 버튼의 활성화 여부를 결정하며 기본값은 true이다. 이를 false 로 만들면 동작은 회색으로 변하며 비활성화된다.</br>
