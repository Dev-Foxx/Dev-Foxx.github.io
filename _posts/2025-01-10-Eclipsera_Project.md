---
layout: post
title: Eclipsera Project
description: Eclipsera 프로젝트 정리
subtitle: 프로젝트 정리
author: Dev Fox
categories: Project, Eclipsera
tags: [Unreal, Eclipsera, Project]
---

# Eclipsera Project 정리

- 3D 애니메이션을 활용해서 수업 내용을 토대로 나만의 포트폴리오를 작업하고 있다.

# Eclipsera Project 주요 클래스

# 프로젝트 구조 및 기능 정리

## 1. Characters Folder
### - Character
- **구현된 기능**
  - 캐릭터의 디폴트 스켈레탈 메시
  - 캐릭터의 움직임 (WASD) 및 마우스 입력
  - 캐릭터의 SpringArm과 카메라 좌표 설정
- **예정된 기능**
  - 점프 애니메이션 연동

### - Enemy
  - **예정된 기능**
   - 적 AI 구현


---

## 2. Component Folder
### - WeaponComponent
- **구현된 기능**
  - 무기 장착
  - 무기 상태 변환

### - MovementComponent
- **구현된 기능**
  - 캐릭터의 걷기 및 달리기 구현

### - StateComponent
- **구현된 기능**
  - WeaponComponent와 델리게이트(EWeaponState 상태 변환값)
- **예정된 기능** 
  - 상태 변환에 따른 인게임 플레이 모션 변경


---

## 3. Weapon Folder
### - Weapon
- **구현된 기능**
  - 무기 공격 모션
- **예정된 기능**
  - 무기 충돌체 상호작용

### - Action
- **구현된 기능**
  - 공격 모션
- **예정된 기능**
  - 입력값에 따른 다른 모션
  - 무기마다 다른 애니메이션

---

## 4. Notify Folder
### - AnimNotifyState_Combo
- 연속 공격 시 입력 상태 처리

### - AnimNotifyState_Collision
- 무기 공격 시 충돌체 On/Off

### - AnimNotify_BeginAction / EndAction
- 무기 공격 시작 및 종료 처리

### - AnimNotify_BeginEquip / EndEquip
- 무기 장착 시작 및 종료 처리

