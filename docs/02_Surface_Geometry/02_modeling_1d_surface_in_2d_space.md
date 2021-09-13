# Modeling a 1D Surace in 2D Space

### A Surface is a Set of Points

  계산하기 적절한 set of points의 mathematical model을 알아야 한다. 임의의 교차하는 object의 surface에는 무한한 수의 points가 존재하므로, 그 점들을 모두 셀 수는 없다.

  무한한 수의 points set을 나타내기 위해서는, 1D surface를 경계로 하는 2D `Volume` 을 생각해보자. 1D surface는 2D 공간에서의 임의의 curve이다. surface는 낮은 차원의 points set 자체를 나타낸다. 가장 간단한 1D surface는 선(line)이다.

### Implicit form

  2차원 공간에서 line을 나타내는 방법은 상수 기울기(m)과 y 절편(b)를 x, y 변수의 방정식으로 나타내는 것이다.  $y=mx+b$

  

  이는 line에 대한 `implicit` equation이다. 이는 test 처럼 동작하는데 임의의 2D point $P=(x,y)$를 equation에 집어넣어 point가 line위에 교차하는지 확인 해볼 수 있다.

  이러한 형태의 line equation은 한계가 있는데, 기울기(slope)가 무한이 될 수는 없으니 vertical line을 나타낼 수는 없다. 저 일반화된 형태의 implicit equation for a line은 다음과 같다.  $(x_1-x_0)\cdot(y-y_0)=(y_1-y_0)\cdot(x-x_0)$

  $(x_1,y_1),(x_2,y_2)$는 line 위의 constant points이며, 아래와 같이 slope-intercept form으로 나타낼 수 있다. $m=\frac{y_1-y_0}{x_1-x_0}, b=y_0-mx_0$

  slope(m)의 분모에 있는 $x_1-x_0$을 통해 vertical line을 판별 할 수 있다.

### Explicit Form

  line의 points set을 나타내는 또 다른 방법은, 1D 실수를 line 위의 point coordinates로 나타내는 `explicit` equation이다. $x(t)=x_0+(x_1-x_0)\cdot{t},\ y(t)=y_0+(y_1-y_0)\cdot{t}$

  t를 음의 무한대에서 양의 무한대로 움직임에 따라 line위의 모든 점들을 나타낼 수 있다($P=(x(t),y(t))$

  equation들이 동일한 구조를 가지므로, 좀더 compact하게 아래와 같이 나타낼 수 있다

$P(t)=P_0+(P_1-P_0)\cdot{t}$