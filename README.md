# HarmoniaSuite

**HarmoniaSuite** is an open creative audio ecosystem by Chih-hao (Billy) Chen, unifying free and professional tools for modern musicians.

---

## Architecture Overview

| Component | Description | Language | Status | Repo |
|------------|--------------|-----------|---------|------|
| HarmoniaCore (Swift) | Core audio framework for Apple platforms (AVFoundation) | Swift | Active | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaCore) |
| HarmoniaPlayer (Apple) | macOS / iOS player built on the Swift version of HarmoniaCore | Swift | Active | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaPlayer) |
| HarmoniaCore (C++20) | Core audio framework for Linux (PipeWire/ALSA) | C++20 | Planned (Phase 3) | (TBD) |
| HarmoniaPlayer (Linux) | Linux desktop player (CLI/GUI) built on the C++20 HarmoniaCore | C++20 / Qt or GTK | Planned (Phase 4) | (TBD) |
| HarmoniaAudio (macOS Free) | Audio editor — metadata, lyrics, waveform editing | Swift | Deferred (Phase 5) | (TBD) |
| HarmoniaAudio Pro | Professional edition — advanced effects & non-destructive editing | Swift / C++ | Deferred (Phase 6, private) | N/A |
| HarmoniaCommunity | Open portal for plugins and presets | Web | Planned (post Audio v1) | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaCommunity) |

---

## Platform Responsibility Separation

| Layer | Apple (Swift) | Linux (C++20) |
|------|----------------|---------------|
| Core | HarmoniaCore (Swift / AVFoundation) | HarmoniaCore (C++20 / PipeWire) |
| Application | HarmoniaPlayer (macOS / iOS) | HarmoniaPlayer (Linux, planned) |

HarmoniaPlayer (Swift) is a native macOS/iOS application and will remain separate from the Linux codebase.  
The Linux implementation focuses on the Core framework first, then a minimal CLI/GUI for parity validation.
> No shared source code across platforms — only a shared, testable behavior specification and vectors.
---

## Module Dependency Relationship

HarmoniaSuite applications share a unified decoding and playback foundation through HarmoniaCore.  
This structure ensures consistent behavior across all products while allowing each to focus on its specific user workflow.

| Module | Depends on | Purpose | Playback Control |
|---------|-------------|----------|------------------|
| HarmoniaCore | – | Core framework that provides decoding, playback, and encoding logic | Yes |
| HarmoniaPlayer | HarmoniaCore | Focused on playback, playlist, and audio output | Yes |
| HarmoniaAudio | HarmoniaCore | Focused on waveform editing, metadata modification, and re-encoding | Yes (real-time preview) |

Both HarmoniaPlayer and HarmoniaAudio use the same playback engine defined in HarmoniaCore.  
HarmoniaAudio embeds this engine to allow in-place playback and region preview during editing.  
This guarantees that the sound heard during editing is identical to the exported playback result.

### Design Principles
- Single playback engine: One codebase for playback, shared between Player and Audio.  
- Real-time parity: Editing preview and final playback use the same decoding path.  
- Separation of concerns: Core handles audio logic; Player and Audio provide user interaction layers.  
- Cross-platform validation: Linux builds will replicate the same dependency structure using the C++ implementation of HarmoniaCore.

---

## Supported Audio Formats (Player perspective)

| Format | Codec | Player (macOS) | Player (iOS) | Player (Linux, planned) |
|--------|------|-----------------|--------------|-------------------------|
| MP3 | MPEG-1 Layer III | Yes | Yes | Yes |
| AAC / ALAC | MPEG-4 / Apple Lossless | Yes | Yes | Yes |
| WAV / AIFF | PCM 16–24 bit | Yes | Yes | Yes |
| FLAC | Free Lossless Audio Codec | Yes | – | Yes |
| DSD (DSF/DFF) | Direct Stream Digital | Yes | – | Yes |
| Opus (optional) | Ogg / Opus | – | – | Planned |

The iOS version supports MP3, AAC, and ALAC only, limited by Apple Music/iTunes library compatibility (no direct file access).  
The macOS Pro version adds high-resolution FLAC and DSD decoding via embedded open-source decoders (`dr_flac`, `libdsd`).

---

## Repository Layout

```
HarmoniaSuite/
├─ HarmoniaCore/                # Core framework (Apple + Linux)
│  ├─ apple-swift/
│  ├─ linux-cpp/
│  ├─ docs/api-parity.md
│  └─ test-vectors/
├─ HarmoniaPlayer/              # macOS / iOS App (SwiftUI, uses Swift Core)
└─ HarmoniaPlayer_Linux/        # (planned) Linux CLI/GUI app (Qt/GTK, uses C++ Core)
```

---

## Roadmap (Suite Level)

| Phase | Timeframe | Focus | Goal |
|-------|-----------|-------|------|
| Phase 1 | Q4 2025 | HarmoniaPlayer (macOS MVP) + Swift Core | Launch free player with MP3/AAC/ALAC |
| Phase 2 | Q1 2026 | HarmoniaPlayer (iOS) | Release iOS version |
| Phase 3 | Q2–Q3 2026 | HarmoniaCore (Linux C++20) | MVP + parity tests against Swift Core |
| Phase 4 | Q3–Q4 2026 | HarmoniaPlayer_Linux | Minimal desktop player (CLI/GUI) |
| Phase 5 | 2027 | HarmoniaAudio (macOS Free) | Metadata / lyric editing |
| Phase 6 | 2027–2028 | HarmoniaAudio Pro (macOS, private) | Advanced effects / non-destructive editing |
| Phase 7 | Post-2028 | Community Portal | Open contributions |

---

## Support

Your support helps sustain long-term open-source audio development. Every donation contributes to documentation, localization, and future accessibility efforts.

PayPal → https://paypal.me/HarmoniaSuite  
Buy Me a Coffee → https://buymeacoffee.com/harmonia.suite.project  
Contact → harmonia.audio.project@gmail.com

---

## License
MIT © 2025 Chih-hao (Billy) Chen  
Contact → harmonia.audio.project@gmail.com

## Author
Chih-hao (Billy) Chen  
GitHub: [OneOfWolvesBilly](https://github.com/OneOfWolvesBilly)
