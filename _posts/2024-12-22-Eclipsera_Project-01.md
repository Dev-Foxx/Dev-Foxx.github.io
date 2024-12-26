---
layout: post
title: Eclipsera Project - 01
subtitle: 새로운 프로젝트 시작
author: Dev Fox
categories: Project
tags: [Unreal, Eclipsera, Project]
top: 1
---




# Eclipsera Project RoadMap

## 1. Project Description
Eclipsera는 **언리얼 엔진**을 통해 **C++**을 활용하여 개발 중인 게임 프로젝트입니다. 이 프로젝트는 3D Action RPG 제작을 할 목적입니다.

---

## 2. Progress

### 2.1 주요 파일 및 구조
- **Eclipsera.sln**: Visual Studio를 위한 메인 솔루션 파일로, 프로젝트의 모든 소스 코드와 리소스를 관리합니다.
- **Source 디렉토리**:
  - **Private**: 핵심 로직을 포함한 비공개 코드 파일들.
    - 게임 모드, 플레이어 캐릭터, 무기 시스템 등.
  - **Public**: 외부와 상호작용 가능한 헤더 파일들.
    - 게임의 주요 기능 정의 및 유틸리티 함수 포함.

### 2.2 작업된 주요 클래스 및 파일
- **게임 플레이 로직**
  - `CGameModeBase`: 게임 모드 베이스 클래스 구현.
  - `CPlayer`: 플레이어 캐릭터 클래스.
  - `CMovementComponent`, `CStateComponent`: 캐릭터 상태와 움직임 제어.
- **애니메이션**
  - `CAnimInstance_Player`: 플레이어 캐릭터의 애니메이션 블루프린트와 연동.

- **무기 시스템**

- `CWeapon`, `CWeaponAsset`, `CWeaponStructor`: 무기 생성, 데이터 관리, 및 관련 구조체.
  - **데이터의 흐름**: `CWeaponAsset` → `CWeaponComponent` → `CWeapon`.
    - `CWeaponAsset`: *무기 데이터를 저장하는 자산 파일로, 무기 종류와 속성 등을 정의.*
    - `CWeaponComponent`: *무기 데이터를 불러와 캐릭터와 연동하며, 무기 교체 및 상태를 제어.*
    - `CWeapon`: *게임 내에서 무기의 실제 동작과 상호작용을 처리.*
    
#### 추가 설명
- **데이터 관리 구조**:
  - `CWeaponAsset`은 무기 관련 데이터를 중앙화하여 관리하며, 다른 무기 컴포넌트들이 이 데이터를 읽어 동작합니다.

  - `CWeaponComponent`는 무기의 상태를 제어하는 핵심 역할을 담당하며, `CWeapon`의 생성을 트리거합니다.
  
- **확장 가능성**: 새로운 무기 유형이나 특성을 추가하려면, `CWeaponAsset`과 관련 구조체만 수정하면 됩니다.

- **유틸리티**
  - `CLog`, `CHelpers`: 디버깅 및 보조 함수 제공.

### 2.3 세부 코드 작업 내역
- **`Eclipsera.cpp`**: 기본 게임 모듈 초기화.

- **`CGameModeBase`**:
  - `ACGameModeBase` 클래스 구현.
  - 플레이어 기본 폰 클래스를 블루프린트를 통해 설정.
  
  
- **`CPlayer`**:
  - 플레이어 캐릭터 클래스 `ACPlayer` 구현.
  - 카메라 설정 및 스켈레탈 메시 초기화.
  - `MovementComponent` `WeaponComponent` 연동
  - 액션키와 축키 바인딩
  
  
- **`CMovementComponent`**:
  - 캐릭터 움직임 제어.
  - 상태 전환 (걷기, 뛰기 등) 및 관련 속성 정의.
 
  
- **`CStateComponent`**:
  - 캐릭터 상태 관리 (Idle, Action, Equip 등).
  
- **`CWeaponComponent`**:
  - 무기 데이터 자산 로드 및 초기화.
  - 여러 무기 상태 설정.
  - 무기 생성 관리
  
- **`CAnimInstance_Player`**:
  - 애니메이션 데이터와 캐릭터/무기 컴포넌트 연동.
  
- **`CLog.cpp`**:
  - 디버깅을 위한 다양한 로그 출력 함수 구현 (정수, 문자열, 벡터 등).

- **`CHelpers`**
    - 액터와 컴포넌트 생성 매크로 구현
   
---

## 3. Workflow
- **컴포넌트 기반 설계**: 각각의 기능을 독립적인 모듈로 설계하여 유지보수 및 확장 용이.
- **C++ 중심 개발**: 성능 최적화를 위해 대부분의 로직을 C++로 구현.
- **애니메이션 및 무기 관리**: 게임플레이의 중요한 축인 애니메이션과 무기를 체계적으로 관리.


---

## 4. Tasks
- **확장 가능성**: 무기와 캐릭터 시스템의 데이터 기반 확장.
- **무기 구현 완료**: 사용할 무기 메시와 액터 정리
- **AI 구현**: 적 캐릭터 AI 추가.
- **매크로 개선**: 자주 사용하게 될 매크로 구문 작성
- **블로그 통합**: 개발 진행 상황을 정리하여 블로그에 주기적으로 게시.

---

## 5. Next Steps
- **주기적 기록**: 매 작업 후 개발 로그 작성.
- **코드 리뷰**: 정기적인 코드 리뷰로 품질 관리.

---
