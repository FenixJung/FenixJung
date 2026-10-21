# Hi, I'm Fenix Jung

**English** · [한국어](README.ko.md)

I build products by directing AI. I run every app and website as a Jira project with a stage-gated lifecycle: **Discovery** (problem definition, research) → **Definition** (ideation, product concept, user flows and business logic, functional requirements) → **Design** (UX research, ideation, lo-fi wireframes, usability testing, hi-fi) → **Build** (incremental delivery) → **Release** (acceptance testing, launch, iteration). Every stage has deliverables and exit criteria, QA runs continuously, and the roadmap and backlog live in Jira.

Business Administration student at Douglas College (Vancouver, BC). Each project below is shown through project management, UX design, marketing and IT / software.

[pvlselab.com](https://pvlselab.com) · [completeelixir.com](https://completeelixir.com) · [LinkedIn](https://www.linkedin.com/in/fenixjung)

> The source code for these projects is private. **[How I Build](HOW-I-BUILD.md)** shows the process behind each one, and I'm happy to walk through any of them.

## Projects

### ZAP + EVOLVE · PVLSE LAB
The first product of my audio plugin startup: a three-stage distortion VST plugin (C++/JUCE), built by directing Claude Code.
- Turned product ideas into specifications and step-by-step prompts, broken into small, testable steps.
- Tested each AI-generated build against the intended behavior and iterated until the plugin worked.
- Automated macOS and Windows builds with GitHub Actions, with pluginval checks on every build.

[Case study →](case-studies/zap-evolve.md)

### Complete Elixir online store
[completeelixir.com](https://completeelixir.com), built end to end by directing AI.
- Competitive analysis, design research, problem finding, and a mobile-first design.
- Product videos, photos, and captions produced by AI under my direction.
- Flagged every issue, had the AI fix it, and tested all functions before launch.

[Case study →](case-studies/complete-elixir-store.md)

### ORBIT · macOS audio app
macOS has no built-in system-wide EQ. ORBIT adds one for every app, such as Spotify or Apple Music, in stereo or Dolby Atmos, and plays Apple Music's Atmos channels through Atmos earphones or headsets automatically.
- Now: app concept done, logic and functions nearly done, lo-fi wireframes done; usability testing (fixed questions and pass criteria, v0.2 → v0.4) nearly finished.
- Planned stack: Swift 6 + SwiftUI, a C++20 real-time audio core, and Core Audio process taps.

[Case study →](case-studies/orbit.md)

## Skills

- **Audio engineering:** sound design, mixing and mastering; audio QA.
- **UX design:** user research, usability testing, wireframes and prototypes.
- **Project management:** requirements, Agile, Jira, cross-functional coordination.
- **Building with AI:** I plan the product, make the decisions, write the concept and spec, and direct the design (lo-fi to hi-fi, visuals, product videos, photos and captions). Claude Code and Claude build it, and I test and document every step. On ORBIT, for example, 23 design decisions are recorded in the app structure.
