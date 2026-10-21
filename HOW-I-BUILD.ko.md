# How I Build

[English](HOW-I-BUILD.md) · **한국어**

저는 AI에게 지시해서 제품을 만듭니다. 코드는 직접 쓰지 않습니다. 문제를 찾고, 제품이 어떻게 작동할지 기획하고, 디자인한 뒤, AI(Claude Code, Claude)가 한 단계씩 만들게 하고, 결과가 요청한 대로인지 매번 테스트합니다.

이 페이지는 제품이 아니라 만드는 과정을 보여줍니다. 소스 코드는 공개하지 않습니다.

## 모든 앱과 웹사이트를 만드는 과정

제가 만드는 모든 프로젝트는 같은 순서를 따르고, 모든 프로젝트를 Jira로 관리하며 한 단계씩 순서대로 진행합니다.

![모든 앱과 웹사이트를 만드는 과정](case-studies/images/process.svg)

1. **앱 기획:** 문제 찾기 → 아이디에이션 → 리서치 → 앱 전체가 어떻게 작동할지 구상 → 로직 만들기 → 기능 프레임워크 구축.
2. **디자인:** 기획이 끝나면 시작합니다. 아이디에이션 → 리서치 → lo-fi → hi-fi.
3. **개발:** 기능 구현.
4. **완성:** 모든 테스트를 통과해야 끝납니다.

**테스트는 마지막에만 하지 않고, 모든 단계에서 정기적으로 합니다.**

## 각 단계 안에서 일하는 방식

- **작고 테스트할 수 있는 단계.** 모든 단계에는 분명한 확인 방법이 있습니다. 들어볼 소리, 재볼 화면, 통과해야 할 테스트 같은 것입니다.
- **AI가 한 번에 한 단계씩 만들고,** 저는 결과를 하나씩 확인합니다.
- **할 수 있는 곳은 자동 검사:** 빌드마다 plugin validation, 전체 페이지 접근성 검사. 나머지는 제가 직접 검토합니다.
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
