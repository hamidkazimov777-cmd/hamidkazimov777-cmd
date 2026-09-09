# Hamid Kazimov

**Systems engineer — native macOS, Rust desktop, audio DSP.**

I build and ship complete desktop products on my own: signal processing in Swift,
Tauri/Rust applications, and the release engineering around them. Below are four
projects with the numbers that back them.

Baku, Azerbaijan · open to relocation (EU)

---

## Convertra — on-device key & BPM detection for DJs

Native macOS analysis app and a DSP engine that replaces the cloud entirely.
Key (Camelot) and tempo are computed on-device with pure signal processing over
Apple's `Accelerate` / `vDSP` — no neural network, no network at all.

**Benchmarked against ground-truth tags from 111 commercial tracks**
(house, tech-house, hip-hop, pop):

| Metric | Result |
| --- | --- |
| Key — exact Camelot match | ~70% |
| Key — harmonically compatible match | ~83% |
| Tempo — within ±0.5 BPM | ~82% |
| Analysis time per track (Apple Silicon) | ~1 s |

Method: harmonic pitch-class profiling with peak-picking for key; autocorrelation
with parabolic sub-BPM interpolation for tempo.

Actor-based concurrent scanning, single-pass decode through `AVAssetReader`
straight into vDSP buffers, security-scoped resources for sandbox compliance.

`Swift · Accelerate/vDSP · AVFoundation · SwiftUI · CoreData`
→ [convertra](https://github.com/hamidkazimov777-cmd/convertra)

---

## Magnetar — AI IDE with persistent project memory

A desktop IDE built on Tauri and Rust where project context lives outside the
conversation. Models are swappable executors; what they learn about the codebase
stays behind in a memory of **facts, each carrying its source and whether a
machine verified it** — because a false fact is worse than a missing one.

- Provider-neutral transcript with adapters for OpenAI-compatible, Anthropic and
  GigaChat APIs — switching models mid-task is a serialisation detail, not
  context loss
- Tool use detected by behaviour: models that ignore the `tools` field are
  automatically replayed through a text-based ReAct protocol
- Local BM25 code index, real PTY terminal, Monaco editor, git surface,
  decision log
- Five offline quality gates: typecheck, unit tests, build, `cargo test`, smoke

265 commits. Known limitations and their trade-offs are documented in the repo
rather than hidden.

`Rust · Tauri · TypeScript · React · SQLite`
→ [Magnetar](https://github.com/hamidkazimov777-cmd/Magnetar)

---

## Lyra — streaming voice dictation for macOS

Dictation and in-place voice editing against your own API keys. Audio streams
over a WebSocket while you speak, so the transcript is settled by the time you
release the key.

- Three-tier fallback: live stream → cloud upload → on-device `whisper.cpp`
  with the Metal backend
- Selection Transform — highlight text in any macOS app, speak an instruction,
  the selection is replaced
- Accessibility inspection off the main thread with an 80 ms timeout so it never
  delays the microphone
- Non-destructive insertion: the pasteboard is snapshotted and restored

142 unit tests, no network required to run them. Universal binary, MIT licensed.

`Swift · AVAudioEngine · whisper.cpp · Accessibility API`
→ [Lyra](https://github.com/hamidkazimov777-cmd/Lyra)

---

## ForzaDJ — DJ pool platform

Full-stack platform for track discovery and delivery: persistent global audio
player, server-side waveform and preview generation, Telegram-based auth, and an
admin bot for publishing.

`Next.js · TypeScript · Supabase · PostgreSQL · FFmpeg · Convertra AudioCore (TypeScript port)`
→ [forzadj](https://github.com/hamidkazimov777-cmd/forzadj) · [forzadj.ru](https://forzadj.ru)

---

## How I work

I run long-horizon development with AI agents and have built the tooling for it —
structured handoffs, verified project memory, offline quality gates that run
before anything ships. Architecture, DSP algorithms, provider protocols and
release engineering are mine; agents execute against specifications I write.

Before software I spent years as a DJ and art director. That's where the product
instinct comes from, and why the audio work isn't academic — I built the tools I
needed.

**Stack:** Swift, SwiftUI, AVFoundation, DSP · Rust, Tauri · TypeScript, React,
Next.js · PostgreSQL, SQLite, Supabase · FFmpeg

[Telegram](https://t.me/hamidkazim) · [LinkedIn](https://www.linkedin.com/in/hamid-kazimov-a48a90365/)
