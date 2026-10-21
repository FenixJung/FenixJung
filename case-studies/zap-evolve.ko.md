# ZAP + EVOLVE · PVLSE LAB

[English](zap-evolve.md) · **한국어** · [처음으로](../HOW-I-BUILD.ko.md)

**무엇인가:** 제 오디오 plugin 스타트업 PVLSE LAB([pvlselab.com](https://pvlselab.com))의 첫 제품입니다. 3단계(ZAP → EVOLVE → ASCEND), 노브 3개(LEVEL, ZAP, TONE), 3단 stage 스위치를 가진 기타 distortion plugin입니다. macOS는 VST3, AU, Standalone, Windows는 VST3, Standalone. C++20과 JUCE로 만들었습니다.

**제 역할:** 창업자. Claude Code에게 지시해서 전부 만들었고, 코드는 직접 쓰지 않았습니다.

**상태:** plugin은 작동하고 소리가 납니다. 최종 사운드 디자인과 튜닝은 진행 중입니다.

## 1. 코드보다 brief와 리서치가 먼저

프로젝트는 다섯 개의 디자인 문서로 시작합니다. 소리를 바꾸기 전에는 이 문서들을 먼저 읽습니다.

| 문서 | 내용 |
|---|---|
| Founder brief | 단계별로 의도한 톤과 참고 아티스트. 가장 우선하는 기준입니다. |
| 회로 리서치 | 잘 알려진 distortion 회로 12개 분석 |
| DSP 리서치 | 디지털 distortion 기법, aliasing을 피하는 방법 포함 |
| Stage 디자인 | 각 단계의 v0.1 설계와 측정 결과 |
| 아티스트 리서치 | 참고 아티스트 6명의 장비와 톤 분석 |

## 2. 작고 테스트할 수 있는 단계

제품 아이디어를 spec과 단계별 prompt로 바꾸고, 기능마다 따로 확인할 수 있는 작은 단계로 나눴습니다.

## 3. 모든 단계를 확인할 수 있게 해주는 도구

- **ZapRender**: WAV 파일을 원하는 단계 조합으로 렌더링합니다. DAW를 열지 않고도 소리 변화를 듣고 비교할 수 있습니다.
- **ZapSnapshot**: plugin UI를 이미지로 저장합니다. host 없이도 UI 변경을 검토할 수 있습니다.

## 4. 빌드마다 자동 검사

GitHub Actions가 macOS와 Windows 버전을 함께 빌드하고, 둘 다 pluginval(strictness level 10)로 검사합니다. Mac에서는 Apple의 auval로 AU 버전을 검사합니다.

## 5. 프로젝트에 적어 둔 규칙

- 소리가 바뀔 때는 founder brief가 최우선 기준이다.
- 저장된 세션이 parameter ID에 의존하므로 ID는 절대 바꾸지 않는다.

## 6. 테스트, 발견, 수정

AI가 만든 빌드를 매번 의도한 동작과 비교해 테스트하고, 오류를 찾아 AI에게 고치게 하면서 plugin이 작동할 때까지 반복했습니다.

## 배운 것

AI는 코드를 빨리 쓰지만, 그 코드가 작동하는지는 spec과 테스트가 결정합니다. 작은 단계마다 분명하게 확인하는 방식이 plugin을 작동하게 만들었습니다.
