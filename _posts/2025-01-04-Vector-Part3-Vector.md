---
layout: post
title: Vector - Part3 내적
description: 벡터의 내적
subtitle: Vector Description
author: Dev Fox
categories: Book, math
tags: [DirectX,Vector]
---

# 벡터 대수

[저번 포스팅](https://dev-foxx.github.io/posts/Vector-Part2/) 에서는 벡터의 단위벡터에 대해서 알아보았다.

## 1. 내적

내적(inner product)은 스칼라 값을 내는 벡터 곱셈의 일종이다. 결과가 스칼라 값이라서 스칼라 곱(scalar product)이라고 부르기도 한다. $\mathbf{u} = (u_x, u_y, u_z)$이고
$\mathbf{v} = (v_x, v_y, v_z)$ 라고 하자. 그러면 내적은 다음과 같이 정의된다.

$$
\mathbf{u} \cdot \mathbf{v} = u_xv_x+u_yv_y+u_zv_z \tag{3}
$$

다른 말로 하면 내적은 대응되는 성분들의 곱들의 합이다. 정의만 봐서는 내적의 기하학적 의미가 잘 보이지 않는다. 코사인 법칙을 이용하면 다음과 같은 관계를 찾아낼 수 있다.



$$
\mathbf{u} \cdot \mathbf{v} = \|\mathbf{u}\| \|\mathbf{v}\| \cos \theta \tag{4}
$$

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/3ca04b68-d6dc-4bc5-b33f-c42cd46ee825" alt="3차원 좌표계와 벡터" />
  <p><em></em></p>
</div>


여기서 $\theta$는 벡터 $u$와$v$사이의 각도로 $0 \leq \theta \leq \pi$이다. 따라서 위의 식은 **두 벡터의 내적이 두 벡터 사이의 각도의 코사인을 벡터 크기들로 비례시킨 것임을 뜻한다** 특히, $u$와$v$ 둘 다 단위벡터인 경우 $u\cdot v$는 두 벡터 사이의 각도의 코사인이다(즉 $u  \cdot v = \cos\theta$).

1. 만일 $ \mathbf{u} \cdot \mathbf{v} = 0 $이면 $ \mathbf{u} \perp \mathbf{v} $(즉, 두 벡터는 수직).
2. 만일 $ \mathbf{u} \cdot \mathbf{v} > 0 $이면 두 벡터 사이의 각도 $\theta$는 $ 90^\circ $보다 작다(즉, 두 벡터는 예각을 이룬다).
3. 만일 $ \mathbf{u} \cdot \mathbf{v} < 0 $이면 두 벡터 사이의 각도 $\theta$는 $ 90^\circ $보다 크다(즉, 두 벡터는 둔각을 이룬다).

### 예시 문제

#### 1.

$x = (1,2,3)$ 이고 $y=(-4,0,1)$이라고 할 때, $x$와 $v$사이의 각도를 구한다면 다음과 같이 크기들을 알 수 있다.

$$
\mathbf{x} \cdot \mathbf{y} = (1, 2, 3) \cdot (-4, 0, -1) = -4 - 3 = -7
$$  

$$
\|\mathbf{x}\| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{14}
$$  

$$
\|\mathbf{y}\| = \sqrt{(-4)^2 + 0^2 + (-1)^2} = \sqrt{17}
$$

다음으로 4번 식을 적용한 후 세타($\theta$)를 구한다.

$$
\cos\theta = \frac{\mathbf{x} \cdot \mathbf{y}}{\|\mathbf{x}\| \|\mathbf{y}\|} = \frac{-7}{\sqrt{14} \sqrt{17}}
$$

$$
\theta = \cos^{-1}\left(\frac{-7}{\sqrt{14} \sqrt{17}}\right) = 117^\circ
$$

#### 2.


그림과 같이 벡터 $\mathbf{v}$와 단위벡터 $\mathbf{n}$이 주어졌을 때, $\mathbf{p}$를 내적을 이용해서 $\mathbf{v}$와 $\mathbf{n}$으로 표현하는 공식을 구해 보자.

우선, 그림을 보면 $\mathbf{p} = k\mathbf{n}$을 만족하는 스칼라 $k$가 존재함을 알 수 있다. 더 나아가서, $\|\mathbf{n}\| = 1$이므로 반드시 $\|\mathbf{p}\| = |k| \|\mathbf{n}\| = |k| \cdot 1 = |k|$이다. 또한 $\mathbf{p}$와 $\mathbf{n}$이 반대 방향일 때에만 음수를 가질 수 있다. <br>
삼각함수를 이용하면 $k = \|\mathbf{v}\| \cos\theta$임을 알 수 있다. 따라서:

$$
\mathbf{p} = k\mathbf{n} = (\|\mathbf{v}\| \cos\theta)\mathbf{n}
$$

그런데 $\mathbf{n}$은 단위벡터이므로 이를 다음과 같이 표현할 수도 있다.

$$
\mathbf{p} = (\|\mathbf{v}\| \cos\theta) \mathbf{n} = (\|\mathbf{v}\| \cdot 1 \cdot \cos\theta) \mathbf{n} = (\|\mathbf{v}\| \|\mathbf{n}\| \cos\theta) \mathbf{n} = (\mathbf{v} \cdot \mathbf{n}) \mathbf{n}
$$

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/2b1f2e67-a067-4418-851e-a95567b237b0" alt="3차원 좌표계와 벡터" />
  <p><em></em></p>
</div>

특히 이 공식에 따르면 $k = v\cdot n$이다. 이는 $n$이 단위벡터일 때의 $v\cdot n$의 기하학적 해석을 말해준다.
이러한 $p$를 $n$에 대한 $v$의 직교투영(orthogonal projection)이라고 부르는데, 흔히 다음과 같이 표기한다.

$$
\mathbf{p} = \mathrm{proj}_{\mathbf{n}} (\mathbf{v})
$$

$v$를 하나의 힘으로 간주한다면 $p$는 힘은$v$ 만큼 방향은$n$으로 작용하는 부분이라고 할 수 있다.
마찬가지로, 벡터 $\mathbf{w}=\mathbf{perp_n}(\mathbf{v})=\mathbf{v}-\mathbf{p} $는 

## 2. 직교화

벡터들의 집합이 주어졌을 때, 만일 그 벡터들이 서로 수직이고 단위 길이이면, 오직 그럴 때에만 
그 벡터집합을 정규수직 집합이라고 부른다. 일단 벡터들이 거의 정규수직이지만 완전히 정규수직은
아닌 경우가 흔히 있는데, 그런 벡터 집합을 수직벡터 집합으로 만드는것을 직교화라고 부른다.
3차원에서 정규직규 집합으로 시작했지만 수치 정밀도 문제 때문에 집합이 점차 정규직교가 아니게 되는 경우도 생긴다.
그러한 문제중에 2차원의 벡터들과 3차원의 벡터들로만 이루어진 집합들만 다루어보겠다.

더 간단한 2차원의 경우부터 보면 벡터 집합 $ [\mathbf{v_0},\mathbf{v_0}] $을 
정규직교 집합 $[\mathbf{w_0},\mathbf{w_1}]$로 만들어 보겠다. 우선 $\mathbf{w_0} = \mathbf{v_0}$
으로 시작해서, 벡터 $\mathbf{v_1}$을 $\mathbf{w_0}$와 직교가 되도록 수정한다. 방법은 $\mathbf{v1}$에서 $\mathbf{w_0}$
방향으로 작용하는 부분을 빼내는 것이다.

$$
\mathbf{w}_1 = \mathbf{v}_1 - \mathrm{proj}_{\mathbf{w}_0} (\mathbf{v}_1)
$$

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/850a7ccd-84d7-4ff1-ad0b-d31ca7018b01" alt="3차원 좌표계와 벡터" />
  <p><em></em></p>
</div>

이제 서로 직교인 벡터들의 집합 $[\mathbf{w_0},\mathbf{w_1}]$이 만들어졌다. 마지막으로
$\mathbf{w_0}$와 $\mathbf{w_1}$을 정규화해서 단위 길이로 만들면 정규직교 집합이 완성된다.

3차원의 경우도 2차원의 경우와 같은 방식이되 단계가 좀 더 많다. 
벡터 집합 $\{\mathbf{w}_0, \mathbf{v}_1, \mathbf{w}_2\}$를 그림 1.12와 같은 정규직교 집합으로 만든다고 하자. 
우선 $\mathbf{w}_0 = \mathbf{v}_0$로 시작해서, 벡터 $\mathbf{v}_1$을 $\mathbf{w}_0$과 직교가 되도록 수정한다. 방법은 $\mathbf{v}_1$에서 $\mathbf{w}_0$의 방향으로 작용하는 부분을 빼내는 것이다.

$$
\mathbf{w}_1 = \mathbf{v}_1 - \mathrm{proj}_{\mathbf{w}_0} (\mathbf{v}_1)
$$

다음으로는 $\mathbf{v}_2$를 $\mathbf{w}_0$과 $\mathbf{w}_1$ 모두에 직교가 되게 만들어야 한다. 방법은 $\mathbf{v}_2$에서 $\mathbf{w}_0$의 방향으로 작용하는 부분과 $\mathbf{w}_1$의 방향으로 작용하는 부분을 빼는 것이다.

$$
\mathbf{w}_2 = \mathbf{v}_2 - \mathrm{proj}_{\mathbf{w}_0} (\mathbf{v}_2) - \mathrm{proj}_{\mathbf{w}_1} (\mathbf{v}_2)
$$

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/9346caed-b5ab-488e-a517-94301854aa50" alt="3차원 좌표계와 벡터" />
  <p><em></em></p>
</div>

이제 서로 직교인 벡터들의 집합 $\{\mathbf{w}_0, \mathbf{w}_1, \mathbf{w}_2\}$가 만들어졌다. 마지막으로 $\mathbf{w}_0, \mathbf{w}_1, \mathbf{w}_2$를 정규화해서 단위 길이로 만들면 정규직교 집합이 완성된다.

일반적인 경우, 즉 $n$개의 벡터들의 집합을 직교하는 경우에는 그람-슈미트 직교화(Gram-Schmidt Orthogonalization)라고 부르는 다음과 같은 절차를 따르면 된다.


1. **기본 단계**: 
    - $\mathbf{w}_0 = \mathbf{v}_0$로 설정한다.

2. **직교화 단계**:
    - $1 \leq i \leq n - 1$에 대해:
      $$
      \mathbf{w}_i = \mathbf{v}_i - \sum_{j=0}^{i-1} \mathrm{proj}_{\mathbf{w}_j} (\mathbf{v}_i)
      $$
      로 설정한다.

3. **정규화 단계**:
    $$
    \mathbf{w}_i = \frac{\mathbf{w}_i}{\|\mathbf{w}_i\|}
    $$

이 과정을 말로 설명하자면 이렇다. 입력 집합에서 벡터 $\mathbf{v}_i$를 택하고, 그 벡터에서 이미 직교 벡터 집합에 들어 있는 다른 벡터 $\{\mathbf{w}_0, \mathbf{w}_1, \dots, \mathbf{w}_{i-1}\}$들의 방향으로의 부분을 빼서 그 벡터를 $\mathbf{w}_i$와 직교가 되게 만든다. 직교 벡터 집합에 추가한다. 그런 과정을 반복해서 직교 벡터 집합을 완성한 후 그 집합의 모든 벡터를 정규화한다.

---