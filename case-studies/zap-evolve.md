# ZAP + EVOLVE · PVLSE LAB

**English** · [한국어](zap-evolve.ko.md) · [Back to overview](../HOW-I-BUILD.md)

**What it is:** the first product of PVLSE LAB, my audio plugin startup ([pvlselab.com](https://pvlselab.com)). A guitar distortion plugin with three stages (ZAP → EVOLVE → ASCEND), three knobs (LEVEL, ZAP, TONE) and a three-position stage switch. VST3, AU and Standalone on macOS; VST3 and Standalone on Windows. C++20 with JUCE.

**My role:** founder. I built it entirely by directing Claude Code; I did not write the code.

**Status:** the plugin works and produces sound. Final sound design and tuning are still in progress.

## The process, step by step

Like every project, ZAP + EVOLVE followed my step flow ([see How I Build](../HOW-I-BUILD.md)) and was managed in Jira.

| Step | In this project |
|---|---|
| **Discovery** | A founder brief on the intended tone of each stage, with reference artists. Research on 12 well-known distortion circuits, digital distortion techniques (including how to avoid aliasing), and the gear and tone of six reference artists. |
| **Definition** | Three stages (ZAP → EVOLVE → ASCEND), three knobs (LEVEL, ZAP, TONE) and a three-position stage switch. The v0.1 design of each stage, with measurement results. Specifications and step-by-step prompts, with parameter IDs fixed so saved sessions keep working. |
| **Design** | A pedal-style UI: drag the knobs, click to change the stage, footswitch for bypass. The UI image layers come from the PVLSE LAB website hero image. |
| **Build** | Built entirely by directing Claude Code (C++20, JUCE): VST3, AU and Standalone on macOS; VST3 and Standalone on Windows. |
| **QA,** throughout | ZapRender to hear any change without a DAW, ZapSnapshot to review the UI as an image, pluginval at strictness 10 on macOS and Windows on every build, and auval for the AU version. |
| **Release** | Not yet. The plugin works and produces sound; final sound design and tuning are still in progress. |

## What's next

Final sound design and tuning, checked against the founder brief, the top-priority reference for every sound change.

## Through four lenses

| Lens | What it shows |
|---|---|
| **Project management** | Founded PVLSE LAB and ran ZAP + EVOLVE as a Jira project, step by step. Scope set by a founder brief that stays the top-priority reference. Fixed rules (brief first; parameter IDs never change) and an honest status: working, with tuning still open. |
| **UX design** | A pedal-style interface a guitarist already knows: three knobs, a three-position stage switch, a footswitch for bypass. UI changes are reviewed as images with ZapSnapshot. |
| **Marketing** | The PVLSE LAB brand and [pvlselab.com](https://pvlselab.com), where ZAP + EVOLVE is shown as in development with a sound concept preview. The product's tone is defined by reference artists, and the plugin UI uses the website's hero image, so product and brand look the same. |
| **IT / software** | C++20 with JUCE 9.0.4, CMake and Ninja. VST3, AU and Standalone builds for macOS and Windows on GitHub Actions, validated with pluginval (strictness 10) and auval. Research into DSP techniques such as avoiding aliasing. |

## In detail

### 1. Brief and research before code

The project starts with five design documents, to be read before any change to the sound:

| Document | What it covers |
|---|---|
| Founder brief | The intended tone of each stage, with reference artists. The top-priority reference. |
| Circuit research | An analysis of 12 well-known distortion circuits |
| DSP research | Digital distortion techniques, including how to avoid aliasing |
| Stage design | The v0.1 design of each stage, with measurement results |
| Artist research | Gear and tone analysis of six reference artists |

### 2. Small, testable steps

I turned product ideas into specifications and step-by-step prompts, and broke each feature into small steps that could be checked on their own.

### 3. Tools that make every step checkable

- **ZapRender** renders a WAV file through any combination of stages, so a sound change can be heard and compared without opening a DAW.
- **ZapSnapshot** saves the plugin UI as an image, so UI changes can be reviewed without a host.

### 4. Automated checks on every build

GitHub Actions builds the macOS and Windows versions together and validates both with pluginval at strictness level 10. On the Mac, Apple's auval checks the AU version.

### 5. Rules written into the project

- The founder brief comes first whenever the sound changes.
- Parameter IDs never change, because saved sessions depend on them.

### 6. Test, find, fix

I tested each AI-generated build against the intended behavior, found the errors, and had the AI fix them, iterating until the plugin worked.

### What I learned

The AI writes code quickly, but the specification and the test decide whether it works. Small steps with a clear check after each one were what got the plugin working.
