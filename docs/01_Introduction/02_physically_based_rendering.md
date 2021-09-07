# Physically Based Rendering

`Physically Correct Rendering`은 computer graphics 분야로 addressed되는 문제들 중 하나이다.
Rendering의 목표는 가상공간의 image sensor의 각 pixel에 transferred 되는 energy를 계산하는 것이다. 그 energy는 photons(양자 입자)에 의해 전달된다.

물리에서는 고전역학이 scene에서의 거시규모(macroscopic) 물질의 bounces를 modeling 할 수 있다.  구현도 꽤 직관적이어서 당구게임의 시뮬레이션을 할 때엔 `momentum equation` 하나와 코드 몇줄으로 해결 할 수 있다. 미시규모(microscopic) 물질의 bounce도 비슷한 과정으로 처리할 수 있지만, 구현에 있어서 문제점이 있다. 
hard, smooth, frictionless surfaces에서 거시규모 물질의 bounce는 들어오는 속도와 나가는 속도가 같고 각도 역시 동일하다 .하지만 미시규모 물질의 경우에는, 거시규모의 surface가 미시규모로는 대부분 평평하지 않기에, 동일하지 않다. 
그래서 당구공의 pool game에 사용한 동일한 기술로 particles simulation을 한다면, 엄청나게 많은 시간과 미시규모 surface geometry를 위한 공간을 요구할 것이다.

빛을 효율적으로 재현하기 위해서는, 많은 photons의 행동을 동시에 계산할 필요가 있다. 한가지 접근방법으로, sensor에 도달하는 energy의 양을 시간, 공간, 방향에 대한 수식으로 유도하고, exposure 시간과 pixel area, 그리고 aperture의 3D angle으로 미분하는 것이다. 미분방정식을 통해서, numerical integration technique을 scene의 detail, photons의 수와 독립적으로 계산할 수 있게 된다.
Graphics에서 이를 `Rendering Equation`이라고 부른다.

자연에서는 `Rendering Equation`을 풀 때 동시에 수조개의 양자 물질을 동시에 해결한다.
물리에서는 대신, mathematical model을 제공한다. 이는 미분 계산을 위한 sampling 전략과, geometric intersection을 계산하는데 필요한 자료구조 그리고 illumination 계산을 위한 processor architecture등을 포함한다.