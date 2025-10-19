# HarmoniaSuite

**HarmoniaSuite** is an open creative audio ecosystem by **Chih-hao (Billy) Chen**, unifying free and professional tools for modern musicians.

---

## Harmonia Player — A Modern, Extensible Alternative for High-Fidelity Audio (Current Focus)

### Mission
To forge a modern, privacy-respecting audio player, drawing inspiration from iTunes’ usability, Colibri’s performance, and foobar2000’s flexibility, creating a balanced, extensible listening experience.

### Vision
A modular, high-fidelity player designed for both casual listeners and audio engineers — crafted to feel fast, not just be fast.

| Detail | Status |
|--------|--------|
| Platforms | macOS (Free & Pro), iPhone/iPad (Free only) |
| Core Technologies | SwiftUI + AVFoundation + SwiftTaggerID3 |
| License | MIT (Free), Pro features available via App Store IAP |
| Repository | [→ View Harmonia Player Repository](https://github.com/OneOfWolvesBilly/HarmoniaPlayer) |

### Key Differentiators
- Modular Core — Separate playback, metadata, and UI layers for full extensibility  
- Instant Startup — Launches in under one second, no media library indexing  
- Precision Metadata — Full ID3v2.4 + CUE + FLAC tag parsing with Unicode lyric & artwork support  
- Smart UI — Clean, latency-free interface built natively in SwiftUI  
- Hi-Res Ready — macOS Pro version supports FLAC / APE / DSD / ALAC playback and conversion  

---

## Harmonia Player — Free vs Pro

| Feature Category | Free Edition (macOS / iOS) | Pro Edition (macOS) |
|------------------|-----------------------------|----------------------|
| Playback formats | MP3, AAC, M4A, WAV, AIFF | + FLAC, APE, ALAC, DSD (DSF/DFF), CUE |
| Audio quality | Standard system output | Bit-perfect mode, ReplayGain, auto sample-rate |
| Lyrics & Metadata | Reads ID3v1/v2, displays lyrics | Edit & save tags, embedded artwork & lyrics |
| Gapless / Crossfade | — | Yes |
| Equalizer / Effects | — | 10-band EQ, loudness, crossfade |
| Visualizer | — | Spectrum & waveform |
| Playlists | Single manual list | Multiple, smart filters, auto-save |
| Hi-Res Conversion | — | FLAC / APE / DSD → AAC / ALAC / MP3 for iPhone |
| iPhone Sync | Manual export | One-click “Send to iPhone” |
| Plugin / Extension | — | Harmonia SDK & future AUv3 host |
| Price | Free (MIT / App Store) | One-time IAP unlock |

Free for everyone — fast, clean, open-source.  
Pro for audiophiles — Hi-Res playback & transcoding precision.

Explore more details, screenshots, and technical roadmap at  
[→ Harmonia Player Repository](https://github.com/OneOfWolvesBilly/HarmoniaPlayer)

---

## Suite Components

| Component | Description | Current Status | Repo |
|------------|--------------|----------------|------|
| Harmonia Player | High-fidelity music player for macOS / iPhone / iPad | Phase 1–2 in development | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaPlayer) |
| Harmonia Audio (macOS Free Edition) | Audio editor for macOS — metadata, lyrics, and waveform editing | In planning for Phase 3 | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaAudio) |
| Harmonia Audio Pro (Private) | Professional edition — advanced effects, non-destructive editing, plugin hosting | Private repository | N/A |
| Harmonia Community | Open portal for AUv3 plugins, presets, and developer submissions | Planned after Audio v1 | [→ View Repository](https://github.com/OneOfWolvesBilly/HarmoniaCommunity) |

Windows and Linux ports will be considered later once the macOS version and community ecosystem are stable.

---

## Roadmap (Suite Level)

| Phase | Timeframe | Focus | Goal |
|--------|------------|--------|------|
| Phase 1 | Q4 2025 | Harmonia Player (macOS MVP) | Launch free macOS player with ID3 reading |
| Phase 2 | Q1 2026 | Harmonia Player (iPhone/iPad) | Release iOS version with File Sharing import |
| Phase 3 | Q2–Q4 2026 | Harmonia Audio (macOS Free Edition) | Release macOS audio editor with metadata, lyric, and waveform support |
| Phase 4 | Q1–Q2 2027 | Harmonia Audio Pro (macOS) | Add plugin engine, non-destructive editing, spectral tools |
| Phase 5 | Q3–Q4 2027 | Harmonia Suite Community | Launch plugin/preset sharing portal and documentation hub |
| Phase 6 (Community-driven) | Post-2028 | Windows / Linux Ports | Community-driven platform expansion |

Harmonia Player (Pro on macOS, Free on iOS) serves as the foundation of the entire Suite.

---

## Funding & Support

**HarmoniaSuite** is fully self-funded and developed independently.  
Every contribution helps sustain open-source development.

- macOS & iPhone test devices  
- Hosting for the Harmonia Community portal  
- Continued open-source maintenance and documentation  

💖 **Support via PayPal:** https://paypal.me/HarmoniaSuite  
☕ **Buy Me a Coffee:** https://buymeacoffee.com/harmonia.suite.project

For sponsorship or collaboration inquiries:  
harmonia.audio.project@gmail.com

---

## Licensing Model

| Tier | License | Cost | Description |
|------|----------|------|-------------|
| Core Projects (Player, Audio, Community) | MIT | Free | Fully open-source, no feature lock |
| Pro Extensions (Audio Pro, Player Pro) | Commercial (IAP) | Paid | Includes advanced editing, effects, and AUv3 hosting |

### Community Licensing Policy

The Harmonia Suite ecosystem follows a tiered licensing approach:

| Layer | License | Description |
|--------|----------|-------------|
| Platform Source Code (Player, Audio, Community) | MIT | Fully open-source and reusable |
| User-uploaded Content (lyrics, presets, themes) | CC-BY-SA 4.0 | Free to share and remix with proper attribution |
| Third-party Plugins / Extensions | Developer-chosen license | Must include a license file upon upload |
| Pro Applications (Player Pro, Audio Pro) | Commercial (IAP) | Distributed via App Store as paid products |

By contributing to Harmonia Community, users retain ownership of their uploads while granting redistribution rights under the selected open license.

---

## Philosophy
- Open Core, Not Closed Source — free foundation, commercial Pro layer  
- User-Respecting — no tracking, ads, or analytics  
- Extensible by Design — community plugins and SDKs welcome  

No analytics. No telemetry. Just your music.

---

## Author
**Chih-hao (Billy) Chen**  
GitHub: [OneOfWolvesBilly](https://github.com/OneOfWolvesBilly)  
Email: harmonia.audio.project@gmail.com
