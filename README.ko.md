# 안녕하세요, Fenix Jung입니다

[English](README.md) · **한국어**

저는 AI에게 지시해서 제품을 만듭니다. 모든 앱과 웹사이트를 Jira 프로젝트로 운영하고, stage-gate 방식의 lifecycle을 따릅니다: **Discovery**(문제 정의, 리서치) → **Definition**(아이디에이션, product concept, user flow와 business logic, functional requirements) → **Design**(UX research, 아이디에이션, lo-fi wireframe, usability testing, hi-fi) → **Build**(incremental delivery) → **Release**(acceptance testing, 출시, iteration). 단계마다 deliverable과 exit criteria가 있고, QA는 계속 진행하며, roadmap과 backlog는 Jira에서 관리합니다.

Douglas College 경영학(Business Administration) 재학 중입니다 (Vancouver, BC). 아래 프로젝트는 프로젝트 관리, UX 디자인, 마케팅, IT / 소프트웨어 관점으로 보여줍니다.

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
- 지금: 앱 구상 완료, 로직과 기능 거의 완료, lo-fi 와이어프레임 완료, usability test(정해진 질문과 통과 기준, v0.2 → v0.4) 거의 완료.
- 예정 스택: Swift 6 + SwiftUI, C++20 실시간 오디오 코어, Core Audio process taps.

[Case study →](case-studies/orbit.ko.md)

## 스킬

- **오디오 엔지니어링:** 사운드 디자인, 믹싱, 마스터링, 오디오 QA.
- **UX 디자인:** 사용자 리서치, usability test, 와이어프레임과 프로토타입.
- **프로젝트 관리:** 요구사항 정리, Agile, Jira, 여러 팀 간 조율.
- **AI로 만들기:** 제품을 기획하고, 결정을 내리고, 콘셉트와 spec을 쓰고, 디자인을 디렉팅합니다(lo-fi부터 hi-fi, 비주얼, 제품 영상, 사진, 캡션). 만드는 건 Claude Code와 Claude가 하고, 저는 모든 단계를 테스트하고 문서로 남깁니다. 예를 들어 ORBIT는 앱 구조에 디자인 결정 23개를 기록했습니다.
