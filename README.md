# HarmoniaSuite

**HarmoniaSuite** is an open-source architecture and validation overview repository for the Harmonia audio ecosystem.

The suite exists to document how HarmoniaCore, HarmoniaPlayer, and related repositories fit together, while keeping current scope, deferred work, and implementation boundaries explicit.

---

## Architecture Overview

| Component                  | Role                                                | Language   | Status                      |
| -------------------------- | --------------------------------------------------- | ---------- | --------------------------- |
| **HarmoniaCore (Swift)**   | Primary audio core implementation                   | Swift      | **Active public development** |
| **HarmoniaPlayer (Apple)** | Apple-platform application embedding HarmoniaCore   | Swift      | **Active public development** |
| **HarmoniaCore (C++20)**   | Secondary core implementation for parity validation | C++20      | Deferred / frozen           |
| **Linux validation app**   | Minimal playback target for C++ core validation     | C++20 / Qt | Deferred / frozen           |

> The Swift implementation currently serves as the active public reference. The C++20 and Linux validation path remains documented, but it is not in the active implementation scope at this time.

---

## Repositories

### Overview

* **[HarmoniaSuite](https://github.com/OneOfWolvesBilly/HarmoniaSuite)**: Architecture and validation overview repository for the Harmonia audio ecosystem

### Core Development

* **[HarmoniaCore](https://github.com/OneOfWolvesBilly/HarmoniaCore)**: Primary architecture and implementation repository for the Harmonia core

  * `HarmoniaCore-Swift/`: Active Swift implementation source
  * `HarmoniaCore-Cpp/`: Deferred / frozen C++20 implementation path

### Distribution Packages

* **[HarmoniaCore-Swift](https://github.com/OneOfWolvesBilly/HarmoniaCore-Swift)**: Swift Package Manager distribution repository, mirrored from the HarmoniaCore monorepo

### Applications

* **[HarmoniaPlayer](https://github.com/OneOfWolvesBilly/HarmoniaPlayer)**: Apple-platform music player and application-level validation target built on top of HarmoniaCore

  * Depends on: `HarmoniaCore-Swift` via Swift Package Manager

---

## Platform Responsibility Separation

| Layer           | Apple (Swift)                | Linux (C++20)                   |
| --------------- | ---------------------------- | ------------------------------- |
| **Core**        | HarmoniaCore (Swift)         | HarmoniaCore (C++20) — Deferred |
| **Application** | HarmoniaPlayer (macOS / iOS) | Minimal validation app — Deferred |

**Design constraint:**  
No shared source code across platforms — only shared behavior specifications and executable test vectors.

---

## Purpose of the Suite

HarmoniaSuite exists to keep the Harmonia ecosystem architecture, repository boundaries, and current implementation scope explicit.

Applications in the suite are used to validate how HarmoniaCore behaves in real product contexts. They are also treated as real product directions rather than disposable prototypes.

The suite enforces:

* A single, platform-agnostic audio domain model
* Explicit separation between real-time audio logic and application concerns
* Behavior specifications acting as contracts between implementations
* Continuous validation through real applications built on top of the core APIs

---

## Documentation

### HarmoniaCore

* Architecture & design specifications
* Module boundary and integration documentation
* Behavior definitions and testing strategy

Refer to the **[HarmoniaCore](https://github.com/OneOfWolvesBilly/HarmoniaCore)** monorepo for active core architecture and implementation work.  
The **[HarmoniaCore-Swift](https://github.com/OneOfWolvesBilly/HarmoniaCore-Swift)** repository provides the Swift Package Manager distribution consumed by Apple-side development.

### HarmoniaPlayer

* Apple-platform application structure
* Product-facing integration of HarmoniaCore
* Application-level validation and user-facing behavior

Refer to **[HarmoniaPlayer](https://github.com/OneOfWolvesBilly/HarmoniaPlayer)** for current Apple-side application development built on top of HarmoniaCore.

---

## Sustainability

If you find the HarmoniaSuite architecture or documentation useful, support helps sustain long-term maintenance, testing, and documentation work.

* [☕ Buy Me a Coffee](https://buymeacoffee.com/harmonia.suite.project)
* [💖 PayPal](https://paypal.me/HarmoniaSuite)

---

## License

MIT © 2025 Chih-hao (Billy) Chen  
Contact: [harmonia.audio.project@gmail.com](mailto:harmonia.audio.project@gmail.com)