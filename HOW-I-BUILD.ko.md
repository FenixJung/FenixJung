# How I Build

[English](HOW-I-BUILD.md) · **한국어**

저는 AI에게 지시해서 제품을 만듭니다. 코드는 직접 쓰지 않습니다. 문제를 찾고, 제품이 어떻게 작동할지 기획하고, 디자인한 뒤, AI(Claude Code, Claude)가 한 단계씩 만들게 하고, 결과가 요청한 대로인지 매번 테스트합니다.

이 페이지는 제품이 아니라 만드는 과정을 보여줍니다. 소스 코드는 공개하지 않습니다.

## 모든 앱과 웹사이트를 만드는 과정

모든 프로젝트를 Jira에서 stage-gate 방식의 lifecycle로 운영합니다. 단계마다 deliverable과 exit criteria를 정해 두고, 그 기준을 충족해야 다음 단계를 시작합니다. Roadmap, backlog, milestone은 Jira에서 관리합니다.

![모든 앱과 웹사이트를 만드는 과정](case-studies/images/process.svg)

1. **Discovery:** 문제 정의 → 리서치(사용자, 경쟁 제품, 기술).
2. **Definition:** 아이디에이션 → product concept(앱 전체가 어떻게 작동하는지) → user flow와 business logic → functional requirements와 구조.
3. **Design:** Definition이 확정되면 시작합니다. UX research → 아이디에이션 → lo-fi wireframe → usability testing → hi-fi.
4. **Build:** 테스트할 수 있는 단계로 나눠 incremental delivery.
5. **Release:** acceptance testing을 통과해야 출시(go-live)하고, 출시 후에는 피드백으로 iteration.

**QA는 마지막에만 하지 않고, 모든 단계에서 계속합니다.**

## 각 단계 안에서 일하는 방식

- **작고 테스트할 수 있는 단계.** 모든 단계에는 분명한 확인 방법이 있습니다. 들어볼 소리, 재볼 화면, 통과해야 할 테스트 같은 것입니다.
- **AI가 한 번에 한 단계씩 만들고,** 저는 결과를 하나씩 확인합니다.
- **할 수 있는 곳은 자동 검사:** 빌드마다 plugin validation, 전체 페이지 접근성 검사. 나머지는 제가 직접 검토합니다.
- **미리 계획합니다.** 프로젝트마다 다음에 할 일을 로드맵이나 백로그로 정리하고, 다음 단계로 넘어가기 전에 통과해야 할 기준을 정해 둡니다.
- **모든 실수는 규칙이 됩니다.** 문제마다 무엇이 틀렸는지, 왜 놓쳤는지, 다음에는 어떻게 할지를 적습니다. 이 기록이 다음 라운드의 체크리스트가 됩니다.

## Case studies

각 case study는 프로젝트를 위 단계에 맞춰 보여줍니다.

| 프로젝트 | 보여주는 것 |
|---|---|
| [ZAP + EVOLVE · PVLSE LAB](case-studies/zap-evolve.ko.md) | Claude Code에게 지시해서 만든, 실제로 작동하는 VST plugin. 리서치 문서 먼저, 단계별 spec, 테스트 도구, macOS와 Windows 자동 빌드 |
| [Complete Elixir 스토어](case-studies/complete-elixir-store.ko.md) | AI에게 지시해서 만들고 다듬은 실제 운영 중인 Shopify 스토어. 브랜드 색 점검, 숫자로 맞춘 레이아웃, 접근성 검사, 32개 항목의 실수 기록 |
| [ORBIT](case-studies/orbit.ko.md) | 진행 중인 macOS 오디오 앱. 앱 구상 완료, 로직과 기능 거의 완료, lo-fi 와이어프레임 완료, usability test 거의 완료 |

## 소개

Fenix Jung · Douglas College 경영학(Business Administration) 재학 (Vancouver, BC)

Audio engineering · UX design · Project management · Building with AI

[pvlselab.com](https://pvlselab.com) · [completeelixir.com](https://completeelixir.com) · [프로필](README.ko.md)
