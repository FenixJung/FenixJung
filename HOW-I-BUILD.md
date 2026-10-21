# How I Build

**English** · [한국어](HOW-I-BUILD.ko.md)

I build products by directing AI. I don't write the code myself. I write the spec, break the work into small steps that can each be checked, have the AI (Claude Code and Claude) build one step at a time, and test every result against what I asked for. When something is wrong, I name it, have the AI fix it, and turn the mistake into a rule so it doesn't come back.

This page shows the process, not the products. The source code stays private.

## The loop

1. **Brief and research first.** Before anything is built, I write down what the product should do and feel like, and research the field: competitors, reference products, techniques.
2. **Spec in small, testable steps.** Every step has a clear check: a sound to render, a screen to measure, a test to pass.
3. **The AI builds one step at a time,** and I check each result.
4. **Test every build.** Automated checks wherever possible (plugin validation on every build, accessibility scans across every page), and my own review for the rest.
5. **Turn every mistake into a rule.** Each issue gets a note: what was wrong, why it was missed, and what to do next time. The notes become a checklist for the next round.

## Case studies

| Project | What it shows |
|---|---|
| [ZAP + EVOLVE · PVLSE LAB](case-studies/zap-evolve.md) | A working VST plugin built by directing Claude Code: research docs first, a staged spec, test tools, automated macOS and Windows builds |
| [Complete Elixir store](case-studies/complete-elixir-store.md) | A live Shopify store built and refined by directing AI: a brand color audit, measured layouts, accessibility scans, a 32-entry mistake log |
| [ORBIT (in design)](case-studies/orbit.md) | A macOS audio app taken from v0.2 to v0.4 through three usability-testing rounds, before any code |

## About me

Fenix Jung · Business Administration student at Douglas College (Vancouver, BC) · 5+ years of project management and QA at Electronic Arts and Complete Elixir

[pvlselab.com](https://pvlselab.com) · [completeelixir.com](https://completeelixir.com) · [Profile](README.md)
