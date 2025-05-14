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