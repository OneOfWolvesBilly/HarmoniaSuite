# HarmoniaSuite

**HarmoniaSuite** is an open-source cross-platform audio ecosystem centered around a
platform-independent audio core and its validation applications.

The suite exists to ensure that audio playback behavior can be shared across platforms
without sharing implementation code, while enabling real-world product usage.

---

## Architecture Overview

| Component                  | Role                                                | Language   | Status                 |
| -------------------------- | --------------------------------------------------- | ---------- | ---------------------- |
| **HarmoniaCore (Swift)**   | Reference audio core implementation                 | Swift      | **Complete (Phase 1)** |
| **HarmoniaPlayer (Apple)** | Validation application embedding HarmoniaCore       | Swift      | **Active (Phase 2)**   |
| **HarmoniaCore (C++20)**   | Secondary core implementation for parity validation | C++20      | Planned (Phase 3)      |
| **Linux validation app**   | Minimal playback target for C++ core validation     | C++20 / Qt | Planned (Phase 4)      |

> The Swift implementation currently serves as the reference behavior for all future platform ports.

---

## Repositories

### Overview

* **[HarmoniaSuite](https://github.com/OneOfWolvesBilly/HarmoniaSuite)**: Architecture overview and suite-level documentation

### Core Development

* **[HarmoniaCore](https://github.com/OneOfWolvesBilly/HarmoniaCore)**: Umbrella monorepo for cross-platform architecture, specifications, and implementations

  * `HarmoniaCore-Swift/`: Reference Swift implementation (Phase 1 — Complete)
  * `HarmoniaCore-Cpp/`: C++20 implementation (Phase 3 — Planned)

### Distribution Packages

* **[HarmoniaCore-Swift](https://github.com/OneOfWolvesBilly/HarmoniaCore-Swift)**: Swift Package Manager distribution, mirrored from the HarmoniaCore monorepo

### Applications

* **[HarmoniaPlayer](https://github.com/OneOfWolvesBilly/HarmoniaPlayer)**: Apple validation application (Phase 2 — Active)

  * Depends on: `HarmoniaCore-Swift` via Swift Package Manager

---

## Platform Responsibility Separation

| Layer           | Apple (Swift)                       | Linux (C++20)                   |
| --------------- | ----------------------------------- | ------------------------------- |
| **Core**        | HarmoniaCore (Swift / AVFoundation) | HarmoniaCore (C++20 / PipeWire) |
| **Application** | HarmoniaPlayer (macOS / iOS)        | Minimal validation app          |

**Design constraint:**
No shared source code across platforms — only shared behavior specifications and executable test vectors.

---

## Purpose of the Suite

HarmoniaSuite applications exist primarily as **validation targets** to ensure that
HarmoniaCore can be embedded into real-world products, rather than as standalone product commitments.

At the same time, these applications are developed with the intention of evolving into
end-user products once the underlying core APIs and behavior contracts are sufficiently validated.

The suite enforces:

* A single, platform-agnostic audio domain model
* Explicit separation between real-time audio logic and application concerns
* Behavior specifications acting as contracts between implementations
* Continuous validation through real applications built on top of the core APIs

---

## Development Status (Constraint-Oriented)

| Phase   | Focus                   | Dependency                        |
| ------- | ----------------------- | --------------------------------- |
| Phase 1 | HarmoniaCore (Swift)    | Completed                         |
| Phase 2 | Apple validation app    | Validates Swift core APIs         |
| Phase 3 | HarmoniaCore (C++20)    | After Apple validation stabilizes |
| Phase 4 | Linux validation target | After C++ core parity is achieved |

No fixed delivery dates are committed at the suite level.
Progress is driven by validation readiness rather than timelines.

Future work may expand beyond validation targets as the core architecture stabilizes,
including more feature-complete end-user applications.

---

## Documentation

### HarmoniaCore

* Architecture & design specifications
* Ports & adapters documentation
* Behavior definitions and testing strategy

Refer to the **[HarmoniaCore](https://github.com/OneOfWolvesBilly/HarmoniaCore)** monorepo for architecture and cross-platform specifications.
The **[HarmoniaCore-Swift](https://github.com/OneOfWolvesBilly/HarmoniaCore-Swift)** repository contains the current reference implementation.

---

## Sustainability

If you find the HarmoniaSuite architecture or documentation useful, support helps sustain
long-term maintenance, testing, and cross-platform validation work.

* [☕ Buy Me a Coffee](https://buymeacoffee.com/harmonia.suite.project)
* [💖 PayPal](https://paypal.me/HarmoniaSuite)

---

## License

MIT © 2025 Chih-hao (Billy) Chen
Contact: [harmonia.audio.project@gmail.com](mailto:harmonia.audio.project@gmail.com)