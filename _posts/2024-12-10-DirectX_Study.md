---
layout: post
title: DirectX - Vertex
subtitle: Vertex, NDC Description
author: Dev Fox
categories: DirectX
tags: [DirectX,Vertex,NDC]
---

## Vertex란?

**Vertex**는 그래픽스 렌더링 파이프라인의 기본 단위로, 3D 모델링 및 렌더링의 근간을 이루는 가장 작은 단위입니다. Vertex는 3D 공간에서의 한 점을 나타내며, 다음과 같은 속성을 포함할 수 있습니다:

- **위치(Position)**: 3D 공간에서의 좌표 (x, y, z)
- **색상(Color)**: 각 Vertex에 지정된 색상 정보
- **텍스처 좌표(Texture Coordinates)**: 3D 모델과 텍스처 맵핑을 연결하기 위한 좌표
- **노멀 벡터(Normal Vector)**: 조명 계산과 표면 방향 결정에 사용

Vertex는 선(Line), 삼각형(Triangle) 등 다양한 도형을 구성하는데 사용됩니다. 예를 들어:
- **점(Point)**: 1개의 Vertex
- **선(Line)**: 2개의 Vertex
- **삼각형(Triangle)**: 3개의 Vertex

아래의 이미지는 Vertex가 그래픽스 파이프라인에서 어떻게 활용되는지를 보여줍니다.

<div style="display: flex; align-items: flex-start; width: 100%; margin: 0; padding: 0;">
  <!-- 텍스트 섹션 -->
  <div style="flex: 1; margin-right: 20px;">
    <p>
      Vertex는 Input Assembler 단계에서 사용되며, 그래픽스 파이프라인의 최종 출력물인 픽셀 데이터를 생성하는데 중요한 역할을 합니다. 
      Vertex의 수와 배치는 그래픽스 파이프라인의 렌더링 결과를 크게 좌우합니다.
    </p>
  </div>

  <!-- 이미지 섹션 -->
  <img src="https://github.com/user-attachments/assets/510fbacd-5603-4954-b060-92220a53531b" 
       alt="Geometry Shader Input Primitives" 
       style="width: 300px; height: auto; margin: 0; padding: 0; align-self: flex-start;"/>
</div>

---

### D3D::GetDC()->IASetPrimitiveTopology()

DirectX의 **IASetPrimitiveTopology** 함수는 그래픽스 파이프라인의 Input Assembler 단계에서 Primitive Topology를 설정하는 데 사용됩니다. Primitive Topology는 Vertex를 기반으로 도형을 구성하는 방식을 정의합니다.

### Primitive Topology의 종류:

1. **Point List**:
   - 각 Vertex가 독립된 점으로 렌더링됩니다.
   - 응용 분야: 파티클 시스템, 별자리 시뮬레이션

2. **Line List**:
   - 두 개의 Vertex가 하나의 선을 구성하며, 각 선은 독립적으로 렌더링됩니다.
   - 정점 수는 짝수여야 합니다.
   - 응용 분야: 그래프, 네트워크 시각화

3. **Line Strip**:
   - 첫 번째 Vertex와 그 이후의 모든 Vertex가 연결되어 하나의 연속적인 선이 생성됩니다.
   - 응용 분야: 궤적, 경로 시각화

4. **Triangle List**:
   - 각 삼각형은 세 개의 독립된 Vertex로 구성됩니다.
   - 응용 분야: 대부분의 3D 모델링 및 렌더링

5. **Triangle Strip**:
   - Vertex들이 공유되어 하나의 연속적인 삼각형 스트립을 형성합니다. 메모리 효율적.
   - 응용 분야: 테라포밍, 복잡한 표면

```cpp
D3D::GetDC()->IASetPrimitiveTopology(D3D11_PRIMITIVE_TOPOLOGY_LINELIST);
D3D::GetDC()->IASetPrimitiveTopology(D3D11_PRIMITIVE_TOPOLOGY_LINESTRIP);  
D3D::GetDC()->IASetPrimitiveTopology(D3D11_PRIMITIVE_TOPOLOGY_TRIANGLELIST);  
```

이 함수는 Vertex 데이터를 최적의 방식으로 결합하여 GPU가 효율적으로 처리할 수 있도록 돕습니다. 특히 Triangle Strip은 메모리 사용을 줄이는 동시에 성능을 극대화합니다.

---

## NDC (Normalized Device Coordinate)

**NDC**는 화면의 해상도와 무관하게 모든 그래픽 데이터를 정규화된 좌표계(-1에서 +1)로 변환하여 렌더링하는 방식입니다. 이 좌표계는 GPU가 Vertex 데이터를 화면에 정확히 매핑하는 데 필수적인 역할을 합니다.

<p style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/f92e3c26-9c80-42aa-bb3d-c49c61c4e719" alt="NDC 좌표계" style="width: 300px; height: auto; margin: 10px auto; display: block;"/>
</p>

### NDC의 주요 특징:
1. **좌표 범위**: 
   - X축: -1 (왼쪽) ~ +1 (오른쪽)
   - Y축: -1 (아래) ~ +1 (위)
   - Z축: -1 (가까운 평면) ~ +1 (먼 평면)

2. **클리핑(Clipping)**:
   - 화면 밖에 있는 데이터를 제외하여 성능을 최적화합니다.

3. **뷰포트 변환**:
   - NDC 좌표를 화면 픽셀 단위로 변환하여 정확한 화면 출력이 이루어집니다.

### NDC를 사용하는 이유:
1. **해상도 독립성**:
   - 다양한 출력 장치에서 동일한 비율과 품질로 렌더링 가능.
   - 예: 모바일과 데스크탑에서 동일한 장면 렌더링.

2. **투영 변환(Projection)**:
   - 3D 데이터를 2D 화면에 정확히 매핑하여 현실적인 렌더링 구현.

<p style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/0750c805-f041-4ceb-90c9-3c88fe915fda" alt="3D공간의 2D출력" style="width: 300px; height: auto; margin: 10px auto; display: block;"/>
</p>

### 렌더링 파이프라인에서 NDC의 역할:
1. **모델 공간 → 월드 공간**:
   - 모델의 로컬 좌표를 전역 좌표로 변환.
2. **월드 공간 → 뷰 공간**:
   - 카메라의 위치와 방향에 따라 좌표를 변환.
3. **뷰 공간 → 클립 공간**:
   - 투영 행렬을 통해 클리핑 영역으로 변환.
4. **클립 공간 → NDC**:
   - 정규화된 좌표(-1~+1)로 변환.
5. **NDC → 뷰포트 공간**:
   - 실제 화면 픽셀 좌표로 매핑.

---

### 요약

Vertex는 그래픽 데이터의 기본 구성 요소이며, Primitive Topology와 NDC 좌표계를 통해 효율적으로 처리됩니다. 이러한 개념은 DirectX의 그래픽스 파이프라인을 이해하고 활용하는 데 핵심적인 요소입니다.
