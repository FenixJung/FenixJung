# ZAP + EVOLVE · PVLSE LAB

[English](zap-evolve.md) · **한국어** · [처음으로](../HOW-I-BUILD.ko.md)

**무엇인가:** 제 오디오 plugin 스타트업 PVLSE LAB([pvlselab.com](https://pvlselab.com))의 첫 제품입니다. 3단계(ZAP → EVOLVE → ASCEND), 노브 3개(LEVEL, ZAP, TONE), 3단 stage 스위치를 가진 기타 distortion plugin입니다. macOS는 VST3, AU, Standalone, Windows는 VST3, Standalone. C++20과 JUCE로 만들었습니다.

**제 역할:** 창업자. Claude Code에게 지시해서 전부 만들었고, 코드는 직접 쓰지 않았습니다.

**상태:** plugin은 작동하고 소리가 납니다. 최종 사운드 디자인과 튜닝은 진행 중입니다.

## 단계별 과정

모든 프로젝트처럼 ZAP + EVOLVE도 제 작업 순서([How I Build 참고](../HOW-I-BUILD.ko.md))를 따랐고, Jira로 관리했습니다.

| 단계 | 이 프로젝트에서 |
|---|---|
| **기획:** 문제 찾기 → 아이디에이션 → 리서치 | 단계별로 의도한 톤과 참고 아티스트를 적은 founder brief. 잘 알려진 distortion 회로 12개, 디지털 distortion 기법(aliasing을 피하는 방법 포함), 참고 아티스트 6명의 장비와 톤 리서치. |
| **기획:** 앱 구상 → 로직 → 기능 | 3단계(ZAP → EVOLVE → ASCEND), 노브 3개(LEVEL, ZAP, TONE), 3단 stage 스위치. 각 단계의 v0.1 설계와 측정 결과. spec과 단계별 prompt, 저장된 세션이 계속 작동하도록 parameter ID 고정. |
| **디자인:** 아이디에이션 → 리서치 → lo-fi → hi-fi | 페달 스타일 UI: 노브는 드래그, stage는 클릭으로 바꾸고, 풋스위치는 bypass. UI 이미지 레이어는 PVLSE LAB 웹사이트 히어로 이미지에서 가져왔습니다. |
| **개발:** 기능 구현 | Claude Code에게 지시해서 전부 만들었습니다(C++20, JUCE). macOS는 VST3, AU, Standalone, Windows는 VST3, Standalone. |
| **테스트,** 전 과정 | DAW 없이 소리 변화를 듣는 ZapRender, UI를 이미지로 검토하는 ZapSnapshot, 빌드마다 macOS와 Windows에서 pluginval(strictness 10), AU 버전은 auval. |
| **완성:** 모든 테스트 통과 | 아직입니다. plugin은 작동하고 소리가 나지만, 최종 사운드 디자인과 튜닝이 진행 중입니다. |

## 네 가지 관점

| 관점 | 보여주는 것 |
|---|---|
| **프로젝트 관리** | PVLSE LAB을 창업하고 ZAP + EVOLVE를 Jira 프로젝트로 한 단계씩 진행. 범위는 founder brief로 정하고, 이 brief가 항상 최우선 기준입니다. 고정 규칙(brief 우선, parameter ID 변경 금지)과 정직한 상태 관리: 작동은 하고, 튜닝은 진행 중. |
| **UX 디자인** | 기타리스트에게 익숙한 페달 스타일 인터페이스: 노브 3개, 3단 stage 스위치, bypass 풋스위치. UI 변경은 ZapSnapshot 이미지로 검토합니다. |
| **마케팅** | PVLSE LAB 브랜드와 [pvlselab.com](https://pvlselab.com). 사이트에서 ZAP + EVOLVE를 개발 중 제품으로 소개하고 사운드 콘셉트 미리듣기를 제공합니다. 제품의 톤은 참고 아티스트로 정의하고, plugin UI는 웹사이트 히어로 이미지를 써서 제품과 브랜드가 같은 모습입니다. |
| **IT / 소프트웨어** | C++20, JUCE 9.0.4, CMake, Ninja. GitHub Actions로 macOS와 Windows용 VST3, AU, Standalone 빌드, pluginval(strictness 10)과 auval로 검사. aliasing 회피 같은 DSP 기법 리서치. |

## 자세히

### 1. 코드보다 brief와 리서치가 먼저

프로젝트는 다섯 개의 디자인 문서로 시작합니다. 소리를 바꾸기 전에는 이 문서들을 먼저 읽습니다.

| 문서 | 내용 |
|---|---|
| Founder brief | 단계별로 의도한 톤과 참고 아티스트. 가장 우선하는 기준입니다. |
| 회로 리서치 | 잘 알려진 distortion 회로 12개 분석 |
| DSP 리서치 | 디지털 distortion 기법, aliasing을 피하는 방법 포함 |
| Stage 디자인 | 각 단계의 v0.1 설계와 측정 결과 |
| 아티스트 리서치 | 참고 아티스트 6명의 장비와 톤 분석 |

### 2. 작고 테스트할 수 있는 단계

제품 아이디어를 spec과 단계별 prompt로 바꾸고, 기능마다 따로 확인할 수 있는 작은 단계로 나눴습니다.

### 3. 모든 단계를 확인할 수 있게 해주는 도구

- **ZapRender**: WAV 파일을 원하는 단계 조합으로 렌더링합니다. DAW를 열지 않고도 소리 변화를 듣고 비교할 수 있습니다.
- **ZapSnapshot**: plugin UI를 이미지로 저장합니다. host 없이도 UI 변경을 검토할 수 있습니다.

### 4. 빌드마다 자동 검사

GitHub Actions가 macOS와 Windows 버전을 함께 빌드하고, 둘 다 pluginval(strictness level 10)로 검사합니다. Mac에서는 Apple의 auval로 AU 버전을 검사합니다.

### 5. 프로젝트에 적어 둔 규칙

- 소리가 바뀔 때는 founder brief가 최우선 기준이다.
- 저장된 세션이 parameter ID에 의존하므로 ID는 절대 바꾸지 않는다.

### 6. 테스트, 발견, 수정

AI가 만든 빌드를 매번 의도한 동작과 비교해 테스트하고, 오류를 찾아 AI에게 고치게 하면서 plugin이 작동할 때까지 반복했습니다.

### 배운 것

AI는 코드를 빨리 쓰지만, 그 코드가 작동하는지는 spec과 테스트가 결정합니다. 작은 단계마다 분명하게 확인하는 방식이 plugin을 작동하게 만들었습니다.
