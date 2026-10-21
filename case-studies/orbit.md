# ORBIT · macOS audio app

**English** · [한국어](orbit.ko.md) · [Back to overview](../HOW-I-BUILD.md)

## Summary

ORBIT is a macOS menu-bar app that adds the EQ macOS doesn't have, for every app.

**The core app:**
- **EQ for any source.** macOS has no built-in system-wide EQ. ORBIT takes the sound from any app, such as Spotify or Apple Music, whether it's stereo or Dolby Atmos, applies EQ, and lets you customize it to sound the way you want.
- **Atmos, automatically.** With Atmos earphones or a headset, ORBIT detects whether Apple Music is sending Dolby Atmos or stereo, and plays the Atmos channels through your earphones or headset on its own.

**Also in the design:**
- **EQ details:** five bands (125 Hz, 250 Hz, 1 kHz, 4 kHz, 8 kHz) plus Bass Boost, with Flat, Bass, Warm, Bright and Vocal presets.
- **Virtual 7.1 spatial sound** for headphones that have none (for example an Xbox headset), with Game, Movie, Music and Voice modes.
- **Device Tune** corrects each headphone first, so a preset sounds the same on every device.

**Signal chain:** Device Tune → EQ → Spatial → Auto level + Limiter (≤ 0 dBFS). The Mac volume stays the master, and ORBIT never makes anything louder than the source.

**Planned stack:** Swift 6 + SwiftUI menu bar, a C++20 real-time audio core, Core Audio process taps. No network access, no analytics.

**My role:** I run ORBIT like a real software product and design it by directing Claude.

![ORBIT Spatial: seven virtual speakers around the listener](images/orbit-spatial.svg)

## How I build it: step by step, tracked in Jira

I created a Jira project for ORBIT and follow a standard software development process, one step at a time, in order. Testing runs regularly through every step, and the app is finished only when everything passes.

![How I build an app, and where ORBIT is now](images/orbit-process.svg)

| Stage | Steps | ORBIT now |
|---|---|---|
| 1. Plan the app | Find the problem → ideate → research → work out how the whole app works → build the logic → build the functions framework | Problem, ideation, research and app concept done (app structure v0.4, 23 recorded decisions). Logic and functions nearly done. |
| 2. Design | Ideate → research → lo-fi → hi-fi | Lo-fi wireframes done. Hi-fi next. |
| 3. Build | Functionality | Next |
| 4. Finish | Every test passes | Last |
| Throughout | Regular testing | Usability rounds with fixed questions and pass criteria moved the design from v0.2 to v0.4; testing is nearly finished. |

![ORBIT menu-bar panel, drawn from the lo-fi wireframes](images/orbit-panel-lofi.svg)

### An open problem, written down

The automatic Atmos switch depends on knowing what Apple Music is sending, and there is no public API for it. Candidate signals: the Music app's output channel count and format, the system renderer path, and now-playing metadata. If none of them works, the fallback is a per-app rule.

## How it will be evaluated

- Usability rounds with fixed questions and pass criteria, run regularly.
- End-to-end latency measured on both headphones before the engine design is locked.
- Blind, level-matched A/B listening tests for the spatial modes (Beta exit).
- An acceptance test against written criteria before the release.
