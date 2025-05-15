# CallBack Method
Start(), Update()

---
# transform.Rotate()
![](./img/rotateCapsule.gif)
```csharp
void Update()
{
    gameObject.transform.Rotate(0f, 0f, 45f * Time.deltaTime);
}
```

---
# transform.Translate()
![](./img/capsuleMove.gif)
```csharp
void Update()
{
    gameObject.transform.Translate(new Vector3(0, 1 * Time.deltaTime, 0));
}
```
## Rotate + Translate
![](./img/capsuleMoveRotate.gif)
```csharp
void Update()
{
	gameObject.transform.Rotate(0f, 0f, 45f * Time.deltaTime);
	gameObject.transform.Translate(new Vector3(0, 1 * Time.deltaTime, 0));
}
```

---
# SerializeField
Inspector 창에서 변수에 접근할 수 있게된다.
```csharp
[SerializeField] float steerSpeed = 45f;
```
코드에서 값을 설정하더라도 Inspector 창에서 값을 수정하면 해당 값이 새로운 값으로 적용된다.

---
# Input.GetAxis()
플레이어의 물리적인 동작을 변환하는 방법
**Old System 방식**과 New System 방식이 존재한다.
```
eidt -> Project Settings -> Input Manager -> Axes 
(※ Axes 는 Axis 의 복수형)
```
`Horizontal`, `Vertical` 값은 -1(left) ~ +1(right)  범위의 값을 가진다.
![](./img/capsuleControl.gif)
```csharp
float steerAmount = Input.GetAxis("Horizontal");
float moveAmount = Input.GetAxis("Vertical");
gameObject.transform.Rotate(0f, 0f, steerSpeed * Time.deltaTime * -steerAmount);
gameObject.transform.Translate(new Vector3(0, moveSpeed * Time.deltaTime * moveAmount, 0));

```

---
# Time.deltaTime

각 프레임에 소요된 시간에 어떠한 값을 곱하면 프레임률에 독립성(`frame rate independent`) 을 가진 값을 구할 수 있다.
프레임률에 독립성을 가졌다는 의미는 어떠한 기기에서든 동일한 동작을 함을 의미한다.
```
A : 10FPS 의 성능을 가진 컴퓨터
B : 100FPS 의 성능을 가진 컴퓨터

매 프레임에 1cm 이동하게 하면...
A는 같은 시간동안 10cm 이동, B는 100cm 이동한다.
컴퓨터의 성능이 각 플레이어의 능력치에 영향을 주면안된다.
이를 위해 아래와 같은 연산을 수행하게된다.

A -> 1 x 10 x 0.1 = 1cm
B -> 1 x 100 x 0.01 = 1cm
위 연산에서 각 컴퓨터의 값을 보정해주는 10 과 100의 역할을 DeltaTime이 수행한다.
```

---
# Collider

