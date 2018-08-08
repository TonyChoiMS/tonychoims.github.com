---
layout: post
title:  "Unreal Engine Animation에 대해서.."
date:   2018-04-05
desc: "Unreal Engine에서 사용하고 있는 Animation"
keywords: "Unreal animation, actor animation, UnrealEngine, GameProgramming"
categories: [Unreal]
tags: [Animation,Unreal,UnrealEngine]
icon: icon-html
---

# 애니메이션

## 애니메이션 몽타주
 - Asset의 일종
 - 여러개의 시퀀스를 합쳐서 재생시켜주는 기능
 - 시작 , 루프, 끝 애니메이션을 나눠서 섹션 구간별 이벤트를 발생시킬 수 있는 섹션 기능
 - 애니메이션 몽타주가 실행되기 이전의 애니메이션 포즈들을 모두 삭제 후, 애니메이션 몽타주에 저장되있는 애니메이션들을 사용한다.
 - 일정 타이밍에 소리를 출력하거나, 이펙트를 출력하는 기능
 - 커스텀 커브 기능
 - **Pawn이 애니메이션 블루프린트한테 바로 명령을 내릴 수 있다**.

 - 프로세스 : 애니메이션 몽타주 생성 -> 스켈레톤 선택 -> 몽타쥬에 원하는 애니메이션을 정의 후, 캐릭터 블루프린트에서 해당 이벤트가 발생했을 경우 skeletal mesh를 통해서 애니메이션 블루프린트를 가져와서 montage play 함수를 호출한다. -> 애니메이션 블루프린트로 가서 애니메이션 컴포넌트를 최종 애니메이션 포즈로 입력하는 사이에 Montage의 DefaultSlot을 통과하게 중간에 배치한다.

 - 캐시 포즈 새로 저장


## 함수
 - Skeletal Mesh -> Get Anim Instance : 스켈레탈 매쉬에 있는 애니메이션 블루프린트를 가져온다.
 - Get Anim Instance -> Montage Play : 생성해놓은 애니메이션 몽타주를 실행한다.
 - 본 마다 레이어로 블렌딩 -> Mesh Space Rotation : 본의 좌표 기준으로 할 것인지, 컴포넌트 스페이스 기준으로 할 것인지 정하는 옵션
 - Spawn Emitter Attached :