---
layout: post
title: Vector - Part2 단위벡터
subtitle: Vector Description
author: Dev Fox
categories: Book, math
tags: [DirectX,Vector]
---

# 벡터 대수

[저번 포스팅](https://dev-foxx.github.io/posts/DirectX_Part1-Vector/) 에서는 벡터의 간단한 정의와 좌표계, 기본적인 연산방법에 대해서 알아봤다.<br>

---
## 1. 길이와 단위벡터

한 벡터의 크기는 해당 지향 선분의 길이이다. 즉, 벡터를 표기하는 그래프의 길이가 길 수록 벡터의 크기도 크다고 볼 수 있다. <br>
벡터의 크기는 이중 수직선으로 표기하며(||x||는 x의 크기이다.) 이번에도 기호를 사용해서 크기를 구해보자.
3차원 벡터의 크기는 피타고라스의 정리를 두 번 적용해서 계산할 수 있다.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/9c99c068-71fa-4f08-93f5-c292126e447a" alt="3차원 좌표계와 벡터" />
  <p><em>피타고라스의 정리를 두번 적용하면 3차원 벡터의 길이를 구할 수 있다.</em></p>
</div>



위 그림의 이미지에 우선 두 변이 x와 z이고 빗변이 a인 삼각형을 보자, 피타고라스의 정리에 따르면 a의 길이를 구하는 공식은 다음과 같다. $a=\sqrt{x^2+z^2} $
이제 빗변이$\\|\mathbf{u}\\|$인 삼각형을 보자

$$
 \|\mathbf{u}\| =\sqrt{y^2+(\sqrt{x^2+z^2})^2} = \sqrt{x^2 + y^2 + z^2},\tag{1} 
$$

벡터를 순수하게 방향을 나타내는 용도로 사용하는 경우에는 벡터의 길이가 중요하지 않을 수 있다.
그런 방향 전용 벡터에서는 벡터의 길이를 정확히 단위 길이, 즉 1로 맞추어 두는것이 편하며, 벡터의 길이를 단위 길이 즉, 1로 만들어 단위 벡터(unit vector)로 만드는 것을 가리켜 **벡터의 정규화(normalization)** 라고 부른다.

$$
\hat{\mathbf{u}} = \frac{\mathbf{u}}{\|\mathbf{u}\|} = \left( \frac{x}{\|\mathbf{u}\|}, \frac{y}{\|\mathbf{u}\|}, \frac{z}{\|\mathbf{u}\|} \right) \tag{2}
$$

이 공식이 맞는지를 단위벡터 $\hat{\mathbf{u}}$의 길이를 계산해서 확인해보자.

$$
\|\hat{\mathbf{u}}\| = \sqrt{\left(\frac{x}{\|\mathbf{u}\|}\right)^2 + \left(\frac{y}{\|\mathbf{u}\|}\right)^2 + \left(\frac{z}{\|\mathbf{u}\|}\right)^2}
= \sqrt{\frac{x^2 + y^2 + z^2}{\|\mathbf{u}\|^2}}
= \sqrt{\frac{\|\mathbf{u}\|^2}{\|\mathbf{u}\|^2}}
= 1
$$

따라서 $\hat{\mathbf{u}}$ 는 실제로 단위 벡터이다.

---
### 예 1

벡터 $ v=(-1,3,4)$ 를 정규화해 보자. 
$ \|\mathbf{v}\|=\sqrt{(-1)^2+3^2+4^2} = \sqrt{26} $ 이다. 따라서 $\hat{v} = \frac{\mathbf{v}}{\|\mathbf{v}\|} = (-\frac{\mathbf{1}}{\mathbf{26}}+\frac{\mathbf{9}}{\mathbf{26}}+\frac{\mathbf{16}}{\mathbf{26}})$ 이다. 
$\hat{v}$ 가 실제로 단위벡터인지를 그 길이를 계산해서 확인해보면 다음과 같다,

$$
\hat{v} = \frac{\mathbf{v}}{\|\mathbf{v}\|} = (-\frac{\mathbf{1}}{\mathbf{26}}+\frac{\mathbf{9}}{\mathbf{26}}+\frac{\mathbf{16}}{\mathbf{26}}) = \sqrt{1}=1 \tag{3}
$$

