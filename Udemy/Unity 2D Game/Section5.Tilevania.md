# Sprite Sheets
사용할 수 있는 작은 이미지들을 레도 블럭처럼 모아둔것</br>
![300](./img/Pasted%20image%2020250529145414.png)</br>
이대로 그냥 사용할 순 없고 잘라서 사용해야한다.</br>

---
# Game Design
```
- Player Experience
- Core Mechanic
- Core Game Loop
```

---
# MVP Game Feature
MVP 는 **Minimum Viable Product** 의 약자로 최소 실행 가능한 제품을 의미한다.</br>
제품 개발 과정에서 핵심 기능만 포함한 초기 버전을 만들어 시장에 테스트하는 전략을 의미한다.</br>
```
- Character Movement
- Traps / Obstacles
- Level Loading
- Countdown timer
```

---
# Sprite Sheets 수정
### case 1. Slice : Automatic
1. 이미지 파일을 선택하고 Sprite Mode 를 **Single → Multiple** 로 변경한다.
2. Sprite Editor 창을 열고 Slice 를 적용한다.
	자동으로 이미지가 잘려지고 잘려진 이미지는 개별로 저장된다.
	(slice option → type : **Automatic**)
	![600](./img/Pasted%20image%2020250529150311.png)

### case 2. Slice : Grid By Cell Size 
![500](./img/Pasted%20image%2020250529150945.png)</br>
위의 이미지와 같이 픽셀이 차지하는 범위만 자를게 아니라 추가적인 여백도 함께 포함되어 잘려야 하는경우 case1 번과 같이 Automatic 타입으로 slice 를 하면 안된다.</br>
해당 경우 Grid By Cell Size 타입을 고려할 수 있다.</br>
![](./img/Pasted%20image%2020250529151302.png)</br>
해당 타입을 선택하면 아래의 그림과 같이 붉은 선이 생기며 해당 선들을 경계로 이미지를 슬라이한다.</br>
![400](./img/Pasted%20image%2020250529151504.png)</br>
Pixel Size : 32x32 / Padding : 6x6</br>
![400](./img/Pasted%20image%2020250529152127.png)</br>

---
# Unity Tile Map
```
[ Tilemap Pipeline ]
Sprite Sheet -> Sliced Sprite -> Tile Asset -> Tile Palette -> Tilemap(scene)
```
`우클릭 -> 2D Object -> Tilemap -> Rectangular` 를 통해 타일 맵 생성
![500](./img/Pasted%20image%2020250529154720.png)</br>
`Window -> 2D -> Tile Palette` 를 통해 Tile Palette 창을 연다.</br>
![500](./img/Pasted%20image%2020250529154935.png)</br>
Tile Palette 편집창에서 새로운 Tile Palette 를 생성하고 Slice 작업을 거친 Sprite들을 전부 선택하여 Palette 에 Drag&Drop 한다. 저장까지 완료하면 각 슬라이스 되었던 각 타일들이 개별 애셋(\*.asset)이 된 걸 확인할 수 있다.</br>
![400](./img/Pasted%20image%2020250529162343.png)</br>
Palette 에서 사용할 Tile 을 선택하고 Scene 에 마우스 포인트를 올리면 TileMap 의 그리드에 맞게 이미지가 적용되는걸 확인할 수 있다.</br>
![](./img/Pasted%20image%2020250529162517.png)</br>
Palette 의 위에는 편집 도구가 있으며, 자주 사용되는 도구는 selection, move, erase 다.
![500](./img/Pasted%20image%2020250529163134.png)
### case 1.이미지 뒤집기
좌측 테두리 타일밖에 없을 경우 해당 이미지를 선택하여 Inspector 창에서 Scale 의 x 를 -1 로 설정해주면 이미지가 뒤집히면서 우측 테두리 타일이 된다.</br>
![300](./img/Pasted%20image%2020250529163439.png)</br>
### case 2.타일 편집
존재하는 타일 애셋의 다른 방향타일이 필요한 경우 매번 scale 값을 조정하는건 번거로운 작업이다.</br>
이런 경우 Tile Palette 에서 편집모드를 활용하여 요구되는 방향의 Tile을 생성해주면된다.</br>
![](Pasted%20image%2020250529164252.png)</br>

Tile Palette 를 통해 생성한 Tile 애셋을 활용하여 아래와 같이 맵을 손쉽게 생성할 수 있다.</br>
![](./img/Pasted%20image%2020250529165524.png)</br>

---
# Background Tilemap-Layer
Hierachy 창에서 편집할 Tilemap 을 선택하거나 Tile Palette 에서 타일을 적용할 타일맵을 선택할 수 있다.</br>
![](./img/Pasted%20image%2020250529170111.png)</br>
Background Tilemap 에 적용할 Tile 에셋을 Tile Palette 에 추가하여 개별 Tile 에셋을 생성한다.</br>
![200](./img/Pasted%20image%2020250529170503.png)</br>
배경 이미지로 사용하려고 했지만, 의도와는 달리 배경 타일이 땅 타일을 가린다.</br>
![400](./img/Pasted%20image%2020250529171554.png)</br>
### case 1. Order in Layer
TileMap 에셋의 Inspector 창을 확인해보면 Order in Layer 설정이 있는데, 해당 값이 높을수록 화면앞에 출력된다. 배경 타일맵의 Order 를 -1 로 변경해준다.</br>
아래와 같이 배경 타일맵의 순서가 낮아짐으로인해 땅 타일 뒤에 출력되는 것을 확인할 수 있다.</br>
![](./img/Pasted%20image%2020250529172034.png)</br>
### case 2. Sorting Layer
Sorting Layer 를 추가해준다. 이 역시 순서가 낮을 수록 뒤에 배치된다.</br>
![](./img/Pasted%20image%2020250529174632.png)</br>
타일맵의 Additional Settings 에서 Order in Layer 위에 있는 Sorting Layer 를 각각 Platforms 과 Background 로 선택해준다.</br>
![](./img/Pasted%20image%2020250529174735.png)</br>
그러면 아래와 같이 땅 타일맵이 배경 타일맵보다 앞에 출력되는것을 확인할 수 있다.</br>
![](./img/Pasted%20image%2020250529172034.png)</br>

---





