# Images and Light

이제 우리는 light ray가 surface에 부딪히면 흡수(absorbed)되거나 분산(scattered) 된다는 것을 알고있다. 따라서, surface 표현을 위해서는 scattering, absorption, intercepting rays를 고려할 필요가 있다. 우리는 `object`를 surfaces의 집합체로 모델링한다. 하지만, rendering때에는 mass, interior detail과 같이 rendering과 관계없어 보이는 properties는 무시한다.  

아래와 같이 surface를 models 쌍으로 표현할 수 있다.

1. `Geometry`는 surface에 의해 차지되는 공간을 모델링한다
2. `Material`은 light와의 상호작용을 모델링한다

이 챕터에서는 `surface`의 정의를 알아보고, 임의의 geometry와 triangle mesh representation을 위한 `implicit` & `explicit` 형태의 방정식을 알아볼 것이다.

### The speeds of light

특정 주파수에서 하나의 매체로의 빛 전파 속도는 그 매체의 화학적 구성성분과 구조에 의존한다. 우리가 평소에 빛의 속도라고 부르는 것은 $c_0$으로 표기되며, 이는 진공상태에서의 빛의 속도를 나타내는 상수이다. 당연히, 매체를 통한 빛의 전파 속도는 이보다 느리다. 규모로 따지면, 진공상태의 빛 속도보다 물속의 경우 1.3배, 다이아몬드 속의 경우 2.5배 가까이 더 느리다.

### Surfaces are Interfaces

매체에 따라 빛의 전파 속도가 다르다는 것을 알았으니 우리는 surface와 geometry 정의를 알 수 있다. 어떤 매체로 채워진 Volume에서, Volume의 어느 부분에서든 빛의 전파속도가 동일한 경우, 이를 `homogeneous` 하다고 한다. 물리 용어로, 두개의 서로다른 homogeneous media가 만나는 곳을 `optical interface`라고 부른다. 

- Optical surace in the 2D **bounary** between adjacent volumes of two different, homogeneous media.