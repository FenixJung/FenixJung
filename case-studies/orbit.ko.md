# ORBIT · macOS 오디오 앱

[English](orbit.md) · **한국어** · [처음으로](../HOW-I-BUILD.ko.md)

## 요약

ORBIT는 macOS에 없는 EQ를 모든 앱에 더해주는 macOS 메뉴 막대 앱입니다.

**기본 앱:**
- **어떤 소스든 EQ.** macOS에는 시스템 전체에 쓰는 기본 EQ가 없습니다. ORBIT는 Spotify나 Apple Music 같은 앱의 소리를 스테레오든 Dolby Atmos든 받아서 EQ를 적용하고, 원하는 대로 커스터마이즈해서 들을 수 있게 합니다.
- **Atmos는 자동으로.** Atmos 이어폰이나 헤드셋이 있으면, ORBIT가 Apple Music에서 Dolby Atmos가 들어오는지 스테레오가 들어오는지 알아서 판단하고, Atmos 채널 소리를 이어폰이나 헤드셋으로 들려줍니다.

**디자인에 함께 들어간 것:**
- **EQ 세부:** 5밴드(125 Hz, 250 Hz, 1 kHz, 4 kHz, 8 kHz)와 Bass Boost, 프리셋 Flat, Bass, Warm, Bright, Vocal.
- **가상 7.1 공간 음향:** 공간 음향이 없는 헤드폰(예: Xbox 헤드셋)용. Game, Movie, Music, Voice 모드.
- **Device Tune:** 헤드폰마다 먼저 보정해서, 같은 프리셋이 어떤 기기에서도 같은 소리를 냅니다.

**신호 흐름:** Device Tune → EQ → Spatial → Auto level + Limiter(≤ 0 dBFS). 볼륨은 항상 Mac 볼륨이 기준이고, ORBIT는 소스보다 소리를 키우지 않습니다.

**예정 스택:** Swift 6 + SwiftUI 메뉴 막대, C++20 실시간 오디오 코어, Core Audio process taps. 네트워크 접속 없음, 분석 데이터 수집 없음.

**제 역할:** ORBIT를 실제 소프트웨어 제품처럼 운영하고, Claude에게 지시해서 디자인합니다.

![ORBIT Spatial: 듣는 사람 주위의 가상 스피커 7개](images/orbit-spatial.svg)

## 만드는 방식: Jira로 관리하며 한 단계씩

ORBIT용 Jira 프로젝트를 만들고, 표준 소프트웨어 개발 과정을 순서대로 한 단계씩 따라갑니다. 테스트는 모든 단계에서 정기적으로 하고, 모든 테스트를 통과해야 앱이 완성됩니다.

![앱을 만드는 과정과 ORBIT의 현재 위치](images/orbit-process.svg)

| 단계 | 하는 일 | ORBIT 현재 |
|---|---|---|
| 1. 앱 기획 | 문제 찾기 → 아이디에이션 → 리서치 → 앱 전체가 어떻게 작동할지 구상 → 로직 만들기 → 기능 프레임워크 구축 | 문제, 아이디에이션, 리서치, 앱 구상 완료(앱 구조 v0.4, 기록된 결정 23개). 로직과 기능은 거의 완료. |
| 2. 디자인 | 아이디에이션 → 리서치 → lo-fi → hi-fi | Lo-fi 와이어프레임 완료. 다음은 hi-fi. |
| 3. 개발 | 기능 구현 | 다음 |
| 4. 완성 | 모든 테스트 통과 | 마지막 |
| 전 과정 | 정기적인 테스트 | 정해진 질문과 통과 기준으로 진행한 usability test로 디자인이 v0.2에서 v0.4로 바뀌었고, 테스트는 거의 끝났습니다. |

![lo-fi 와이어프레임을 바탕으로 그린 ORBIT 메뉴 막대 패널](images/orbit-panel-lofi.svg)

## 네 가지 관점

| 관점 | 보여주는 것 |
|---|---|
| **프로젝트 관리** | Jira 프로젝트로 한 단계씩 순서대로 진행. 앱 구조에 디자인 결정 23개를 기록. 개발 전에 종료 조건이 있는 평가 계획을 세움(예: Beta 종료 전 블라인드 A/B 청취 테스트). |
| **UX 디자인** | 정해진 질문과 통과 기준으로 진행한 usability test로 디자인을 v0.2에서 v0.4로 바꿈. 메뉴 막대 패널 lo-fi 와이어프레임. 볼륨은 항상 Mac 볼륨이 기준이고, ORBIT는 소스보다 크게 키우지 않습니다. |
| **마케팅** | 분명한 포지셔닝: macOS에 없는 EQ를 모든 앱과 모든 헤드폰에, Atmos는 자동으로. |
| **IT / 소프트웨어** | 설계된 구조: Swift 6 + SwiftUI, Core Audio process taps 위의 C++20 실시간 오디오 코어. 오디오는 lock-free ring buffer로 이동하고, 오디오 스레드가 lock을 걸거나 메모리를 할당하면 빌드가 실패하도록 설정합니다. 설정 변경은 20–50 ms에 걸쳐 바뀌어 클릭 소리가 나지 않습니다. EQ는 double precision RBJ biquad 필터, limiter로 출력은 0 dBFS 이하. ORBIT가 멈추면 macOS가 원래 소리를 스스로 다시 켭니다. |

### 적어 둔 미해결 문제

Atmos 자동 전환은 Apple Music이 무엇을 보내는지 알아야 하는데, 이를 알려주는 공개 API가 없습니다. 후보 신호는 Music 앱의 출력 채널 수와 포맷, 시스템 렌더러 경로, 재생 중 정보(now-playing metadata)입니다. 어느 것도 안 되면 앱별 규칙으로 대신합니다.

## 평가 방법

- 정해진 질문과 통과 기준으로 정기적으로 진행하는 usability test.
- 엔진 설계를 확정하기 전에 두 헤드폰에서 전체 지연 시간 측정.
- 공간 음향 모드는 음량을 맞춘 블라인드 A/B 청취 테스트 (Beta 종료 조건).
- 출시 전에 문서로 정한 기준에 따른 인수 테스트.
