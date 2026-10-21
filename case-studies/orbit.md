# ORBIT (in design)

**English** · [한국어](orbit.ko.md) · [Back to overview](../HOW-I-BUILD.md)

**What it is:** a macOS menu-bar app that applies one EQ (5 bands and presets) and virtual 7.1 spatial sound to every app, on any headphones. It includes Device Tune and leaves Dolby Atmos sources alone.

**My role:** I'm designing it by directing Claude, the same way I build everything else. Started in October 2026.

**Status:** pre-production. Nothing is built yet; Alpha is next.

## Design before code

- **App structure v0.4,** with 23 recorded design decisions.
- **Wireframes** for the app.
- **Three usability-testing rounds,** each with fixed questions and pass criteria. The results moved the design from v0.2 to v0.4.
- **Tracked in Jira.**
- **Planned stack:** Swift 6 + SwiftUI, a C++20 real-time audio core, and Core Audio process taps.

## Why it's here

It shows the same loop before any code exists: decide, test against fixed criteria, change the design, and record why.
