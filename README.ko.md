# 안녕하세요, Fenix Jung입니다

[English](README.md) · **한국어**

저는 AI에게 지시해서 제품을 만듭니다. spec을 쓰고, 작고 테스트할 수 있는 단계로 나누고, Claude Code나 다른 AI 도구가 한 단계씩 만들게 한 뒤, 모든 빌드를 테스트하고 작동 방식을 문서로 남깁니다.

Douglas College 경영학(Business Administration) 재학 중이고 (Vancouver, BC), 프로젝트 관리와 QA 경력이 5년 넘게 있습니다.

[pvlselab.com](https://pvlselab.com) · [completeelixir.com](https://completeelixir.com) · [LinkedIn](https://www.linkedin.com/in/fenixjung)

> 프로젝트 소스 코드는 공개하지 않습니다. 각 프로젝트를 만든 과정은 **[How I Build](HOW-I-BUILD.ko.md)**에 있고, 자세한 설명이 필요하면 언제든 직접 보여드릴 수 있습니다.

## 프로젝트

### ZAP + EVOLVE · PVLSE LAB
제 오디오 plugin 스타트업의 첫 제품입니다. Claude Code에게 지시해서 만든 3단계 distortion VST plugin(C++/JUCE).
- 제품 아이디어를 spec과 단계별 prompt로 바꾸고, 작고 테스트할 수 있는 단계로 나눴습니다.
- AI가 만든 빌드를 매번 의도한 동작과 비교해 테스트하고, plugin이 작동할 때까지 반복했습니다.
- GitHub Actions로 macOS와 Windows 빌드를 자동화하고, 빌드마다 pluginval로 검사합니다.

[Case study →](case-studies/zap-evolve.ko.md)

### Complete Elixir 온라인 스토어
[completeelixir.com](https://completeelixir.com). AI에게 지시해서 처음부터 끝까지 만들었습니다.
- 경쟁사 분석, 디자인 리서치, 문제 찾기, mobile-first 디자인.
- 제품 영상, 사진, 캡션을 AI에게 지시해서 제작.
- 문제를 하나하나 짚어 AI에게 고치게 하고, 출시 전에 모든 기능을 테스트했습니다.

[Case study →](case-studies/complete-elixir-store.ko.md)

### ORBIT · macOS 오디오 앱
macOS에는 시스템 전체 기본 EQ가 없습니다. ORBIT는 Spotify, Apple Music 같은 모든 앱에 스테레오든 Dolby Atmos든 EQ를 적용하고, Atmos 이어폰이나 헤드셋이 있으면 Apple Music의 Atmos 채널을 자동으로 들려줍니다.
- Jira 프로젝트로 한 단계씩 만듭니다: 앱 기획(문제 → 아이디에이션 → 리서치 → 앱 구상 → 로직 → 기능), 디자인(아이디에이션 → 리서치 → lo-fi → hi-fi), 기능 구현. 테스트는 전 과정에서 계속합니다.
- 지금: 앱 구상 완료, 로직과 기능 거의 완료, lo-fi 와이어프레임 완료, usability test(정해진 질문과 통과 기준, v0.2 → v0.4) 거의 완료.
- 예정 스택: Swift 6 + SwiftUI, C++20 실시간 오디오 코어, Core Audio process taps.

[Case study →](case-studies/orbit.ko.md)

## 경력

Electronic Arts FIFA 오디오 QA · Complete Elixir 프로젝트 관리 · MicroPay UX 리서치
