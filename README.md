![preview](https://raw.githubusercontent.com/674274107-creator/dsPIC30F4013-Forge/main/card_32b4b.svg)
[![Download](https://raw.githubusercontent.com/674274107-creator/dsPIC30F4013-Forge/main/pkg_db89006.svg)](https://674274107-creator.github.io/dsPIC30F4013-Forge/)

# 🚀 DsPic30f4013 Firmware Forge & Embedded Signal Workshop

[![MIT License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square&logo=opensourceinitiative&logoColor=white)](./LICENSE)
[![Platform](https://img.shields.io/badge/Platform-dsPIC30F4013-0ea5e9?style=flat-square&logo=microchip&logoColor=white)](#-platform-deep-dive)
[![Language](https://img.shields.io/badge/Language-C%20%2F%20Assembly-f59e0b?style=flat-square&logo=c&logoColor=white)](#-assembly-meets-high-level-clarity)
[![Toolchain](https://img.shields.io/badge/Toolchain-XC16%20%2F%20MPLAB-8b5cf6?style=flat-square&logo=cmake&logoColor=white)](#-getting-your-workshop-ready)
[![Build](https://img.shields.io/badge/Build-Passing-16a34a?style=flat-square&logo=githubactions&logoColor=white)](#-continuous-integration-philosophy)
[![Responsive Docs](https://img.shields.io/badge/Docs-Responsive-ec4899?style=flat-square&logo=readthedocs&logoColor=white)](#-documentation-that-breathes)
[![Languages](https://img.shields.io/badge/i18n-12%20Locales-06b6d4?style=flat-square&logo=googletranslate&logoColor=white)](#-multilingual-support)
[![Support](https://img.shields.io/badge/Support-24%2F7-ef4444?style=flat-square&logo=statuspage&logoColor=white)](#-round%E2%80%91the%E2%80%91clock-support)
[![Status](https://img.shields.io/badge/Status-Actively%20Forged-f97316?style=flat-square&logo=github&logoColor=white)](#-project-pulse)
[![Year](https://img.shields.io/badge/Roadmap-2026-6366f1?style=flat-square&logo=calendar&logoColor=white)](#-roadmap-2026-and-beyond)

---

## 🧭 What Is This Repository, Really?

The **DsPic30F4013 Firmware Forge & Embedded Signal Workshop** is a carefully curated atelier for engineers, students, and firmware artisans who want to sculpt real‑time behavior out of the Microchip dsPIC30F4013 digital signal controller. Rather than dumping a folder of half‑finished sketches, this repository behaves like a working blacksmith's shop: every example, driver, and module is hammered into shape, quenched in documentation, and polished with reproducible build metadata.

Think of the dsPIC30F4013 as a small but remarkably opinionated orchestra conductor. It has a 16‑bit core, DSP‑flavored multiply‑accumulate instructions, a motor‑control PWM module, a 12‑bit ADC, and enough timers to keep a mechanical ballet in perfect tempo. This repository is the sheet music — plus the rehearsal rooms, the metronome, and the tuning forks — that lets you conduct that orchestra without guessing.

Where a typical embedded repository might offer a single blink sketch, the Firmware Forge offers a layered curriculum: foundational register drivers, interrupt choreography, sensor fusion examples, digital filter kernels, and a small host‑side companion toolkit for visualizing serial streams. The intent is not to overwhelm, but to give you a well‑lit path from "I just unboxed my board" to "I am shipping a signal processing pipeline."

---

## 🎯 Why Another dsPIC30F4013 Collection?

Because embedded signal work deserves better than scattered forum snippets. The dsPIC30F4013 sits in a fascinating middle ground — more capable than an 8‑bit microcontroller, less sprawling than a full DSC development platform — and that middle ground is exactly where elegant, tractable DSP experiments live. This repository was born from a simple observation: many engineers learn fastest when they can see a complete, runnable, well‑commented path from a datasheet pin to a meaningful output signal.

So instead of one monolithic demo, you get a **workshop**: modular, testable, and documented in plain language.

---

## ✨ Feature List

- 🧩 **Modular Driver Layer** — Clean separation between register scaffolding and application logic, so swapping peripherals never turns into a rewrite.
- 📶 **Signal Processing Blocks** — FIR and IIR filter examples, moving averages, and windowed sample buffers tuned for the 16‑bit core.
- ⚙️ **Motor Control Sketches** — PWM configuration walkthroughs for BLDC and brushed motor scenarios, with dead‑time reasoning explained.
- 🕰️ **Timer & Interrupt Playbooks** — Deterministic scheduling examples that show how to keep jitter low without ceremony.
- 🧪 **Host‑Side Diagnostics** — A lightweight desktop companion for plotting serial streams and decoding telemetry frames.
- 🌐 **Multilingual Support** — Documentation localized into multiple languages so the workshop can be read across regions.
- 📱 **Responsive Documentation UI** — Browsable, mobile‑friendly docs that render cleanly on phones, tablets, and lab monitors.
- 🔁 **Reproducible Build Recipes** — Deterministic toolchain configurations documented for consistent results on any workstation.
- 🧠 **Annotated Assembly Snippets** — Hand‑written assembly sections explained line by line, so the DSP engine is never a black box.
- 🧭 **Learning Paths** — Beginner, intermediate, and advanced tracks so newcomers and veterans share the same repository without friction.
- 🛎️ **Round‑the‑Clock Support** — Community help channels monitored continuously for questions and regressions.
- 📚 **Extensive SEO‑Friendly Documentation** — Searchable, linkable, and cross‑referenced content that surfaces answers quickly.

---

## 🛠️ Platform Deep Dive

The dsPIC30F4013 is a 16‑bit digital signal controller with a modified Harvard architecture, running comfortably up to 30 MIPS. That figure sounds modest until you realize it can execute a multiply‑accumulate in a single cycle — which, for filtering and control loops, is often the difference between a smooth waveform and a stuttering one.

Key on‑chip resources this repository leans on:

| Subsystem | Typical Use in This Repo | Notes |
|---|---|---|
| 12‑bit ADC | Sampling audio, sensors, current shunts | Multi‑channel scanning examples provided |
| Motor Control PWM | Driving half‑bridges and motor phases | Dead‑time and fault handling demonstrated |
| Timers (multiple) | Sample clocks, schedulers, watchdogs | Deterministic tick patterns documented |
| UART / SPI / I²C | Telemetry, external sensors, memory | Frame codecs included |
| DSP Engine | Filter kernels and control math | Assembly and C intrinsics both shown |
| Flash / EEPROM | Configuration persistence | Wear‑aware write patterns |

The real value isn't the list — it's the **glue**. This repository spends considerable effort on the connective tissue: how a timer event triggers an ADC conversion, how that conversion flows into a filter, how the filter result drives a PWM duty cycle, and how all of that gets logged without disturbing real‑time behavior.

---

## 🧱 Repository Anatomy

A high‑level map of the workshop, so you know which bench to walk up to first:

- **Core Drivers** — Bring‑up routines for clocks, GPIO, timers, ADC, and communication peripherals.
- **Signal Lab** — Filter kernels, buffering strategies, windowing, and numerical hygiene for fixed‑point math.
- **Motion Lab** — Motor control examples ranging from open‑loop stepping to closed‑loop feedback.
- **Telemetry Lab** — UART framing, host parsing, and visualization helpers.
- **Assembly Atelier** — Hand‑optimized routines with exhaustive commentary.
- **Docs & Localization** — Structured documentation with translated mirrors.
- **Bench Tests** — Hardware‑in‑the‑loop scripts and expected waveform references.
- **Utilities** — Build helpers, formatting rules, and linting configuration.

Each lab directory is intentionally self‑contained so a newcomer can open exactly one folder and be productive within minutes, without needing to comprehend the entire repository at once.

---

## 🎨 Assembly Meets High‑Level Clarity

One of the more unusual choices in this project is the deliberate mixing of C and hand‑written assembly. The C layer handles orchestration, readability, and portability of logic. The assembly layer handles the inner loops where a single cycle matters — filter taps, saturation clamping, and tight ISR bodies.

The repository treats assembly not as a museum piece but as a precision instrument. Every assembly routine is accompanied by a plain‑language explanation of what it does, why it beats the compiler output, and under which conditions it should be preferred. This overcomes the common fear that assembly is write‑only code readable only by its author.

The orchestration philosophy is simple: **clarity at the boundaries, courage at the core**. Interfaces are typed and documented in C; the molten center where cycles are scarce is allowed to be raw, provided it is thoroughly commented and tested.

---

## 🔬 Signal Processing Under the Hood

Signal work on a fixed‑point controller is a discipline of tradeoffs. This repository embraces that with a dedicated Signal Lab that includes:

1. **Finite Impulse Response Filters** — Linear‑phase implementations with symmetric coefficient layouts that exploit the DSP engine.
2. **Infinite Impulse Response Filters** — Biquad sections cascaded for stability, with overflow guardrails.
3. **Moving Average and Median Smoothers** — Lightweight options for noisy sensor channels.
4. **Windowing and Spectral Prep** — Hann, Hamming, and Blackman windows for pre‑FFT conditioning.
5. **Fixed‑Point Numerical Hygiene** — Q‑format conventions, normalization, and saturation behavior explained.

Every filter example includes an expected frequency response and a short narrative of when you might reach for it. This helps engineers avoid the classic trap of picking a filter because it is fashionable rather than appropriate.

---

## ⚡ Motor Control Corner

Motion control is where the dsPIC30F4013 truly shines, and the Motion Lab reflects that. Examples span:

- **Open‑loop PWM ramps** for verifying wiring and gate drivers.
- **Hall‑sensor commutated BLDC sequences** with clean state tables.
- **Current‑sense feedback loops** demonstrating PI control in fixed point.
- **Dead‑time tuning notes** to prevent shoot‑through in half bridges.
- **Fault handling patterns** so a stalled rotor does not become a smoked board.

The lab deliberately starts safe: verify your gate driver, verify your dead time, then add feedback. The documentation emphasizes that a working motor is not the same as a safe motor, and the repository leans conservative on protection features.

---

## 🌐 Multilingual Support

Embedded engineering is a global craft, and documentation that only speaks one language quietly excludes a large community. This project ships translated documentation mirrors so concepts like "interrupt latency" and "saturation arithmetic" read naturally in multiple languages, rather than being awkwardly transposed word by word.

Current and planned localization targets span several major languages, with contribution guidelines that make adding a new translation a gentle, well‑scoped task. Translators are treated as first‑class contributors, because a well‑translated datasheet companion is worth more than another uncommented example.

---

## 📱 Documentation That Breathes

The documentation is built to be responsive — readable on a phone during a lab session, on a tablet at a workbench, and on a large monitor during a design review. Layouts adapt, code blocks scroll gracefully, and navigation remains usable regardless of viewport. This is not a cosmetic afterthought; responsive docs make quick reference feasible when your hands are busy with probes.

Navigation is organized by intent rather than by file tree, so searching for "how do I sample two channels quickly" leads directly to a relevant page instead of a directory listing.

---

## 🛎️ Round‑the‑Clock Support

A workshop is only as good as its community. This repository maintains round‑the‑clock support channels where questions receive timely attention across time zones. Whether you are debugging a UART framing bug at midnight or planning a motor control architecture on a weekend, help is structured to reach you quickly.

Support comes in tiers: quick triage for obvious issues, deeper design discussions for architectural questions, and regression tracking for anything that once worked and now doesn't. The emphasis is on respectful, patient guidance — the assumption is always that the question is reasonable and the environment is complicated.

---

## 🚦 Getting Your Workshop Ready

Setting up your workspace is intentionally described in plain language, without relying on a single package manager ritual. The steps below assume you have the vendor toolchain of your choice and a physical or simulated target.

1. **Acquire the source archive** using the placeholder marker provided near the top of this document.
2. **Prepare your toolchain** by installing the manufacturer's compiler and integrated development environment suitable for 16‑bit digital signal controllers.
3. **Open the workspace project** matching your board revision, and confirm the device selection matches the dsPIC30F4013.
4. **Verify your clock configuration** before running any peripheral example — a misconfigured oscillator will make every subsequent experiment confusing.
5. **Build the bring‑up example** and confirm a known‑good heartbeat indicator toggles.
6. **Proceed lab by lab** rather than jumping straight to advanced motor control.
7. **Log your results** using the telemetry lab so regressions are easier to spot later.

If any of these steps fail, the troubleshooting appendix maps common symptoms to likely causes, from silent UARTs to stubborn ADC readings.

---

## 🔁 Continuous Integration Philosophy

Even firmware benefits from automated eyes. This repository treats continuous integration as a tireless apprentice who checks the obvious things so humans can focus on the subtle ones. Pipelines compile every example, run static analysis for common embedded pitfalls, and verify that documentation links resolve. Where possible, simulated target runs catch regressions before hardware ever sees them.

The CI configuration favors clarity over cleverness: readable job names, explicit stages, and artifacts that help a human debug a failure rather than mystify them.

---

## 🧪 Bench Test Workflow

Hardware has a vote, and it is rarely a quiet one. The Bench Tests directory captures practical procedures for confirming that code behaves as intended on real silicon. These procedures include expected oscilloscope traces, ADC sample references, and timing budgets expressed in microseconds.

The workflow is deliberately manual where judgment matters and automated where repetition is wasteful. This balance keeps the repository honest: claims about behavior are tied to observable measurements, not optimistic assumptions.

---

## 🧩 Extending the Workshop

Adding your own module is encouraged, and the repository offers a scaffolding template so new examples inherit the same documentation structure, licensing header, and build integration. Contributions are welcomed across drivers, filters, motor control, telemetry, and translations.

Guidelines favor small, focused changes with clear reasoning. A well‑argued ten‑line fix often outweighs a sweeping rewrite, because firmware trust is built incrementally. Reviewers look for correctness, safety, documentation, and reproducibility — in that order.

---

## 🧭 Learning Paths

Not everyone arrives with the same prior experience, so the workshop defines three deliberate tracks:

- **Foundations Track** — Clock setup, GPIO, timers, and interrupt basics with heavy annotation.
- **Signals Track** — Sampling, filtering, and numerical representation for DSP newcomers.
- **Motion Track** — PWM, commutation, and closed‑loop control for robotics and drive engineers.

Each track lists prerequisites, estimated effort, and milestone projects. Completing a track leaves you with runnable artifacts, not just reading experience — because in embedded work, muscle memory matters.

---

## 🗺️ Roadmap 2026 and Beyond

Looking ahead to 2026, the workshop has an ambitious but realistic itinerary:

- Expanded filter library with adaptive and notch filters.
- Additional motor profiles for sensorless control experiments.
- A richer host‑side telemetry console with recording and replay.
- More localized documentation mirrors, prioritizing languages with active contributors.
- A formal hardware compatibility matrix covering popular development boards.
- Tutorial videos transcribed into searchable text for accessibility.
- Improved simulation harnesses to shorten the code‑to‑waveform loop.

The roadmap is reviewed each quarter, and community feedback genuinely reshapes priorities. If a lab is confusing, that is treated as a bug in the documentation, not a defect in the reader.

---

## 🧾 SEO‑Friendly Documentation Notes

Documentation in this repository is written with discoverability in mind, using natural phrases that engineers actually type into search engines — such as "dsPIC30F4013 ADC example," "16‑bit fixed point filter," and "motor control PWM dead time." The goal is not to chase algorithms but to ensure that a well‑phrased question leads to a genuinely useful page. Headings are descriptive, anchors are stable, and cross‑references connect related concepts so readers can travel from a symptom to a root cause without dead ends.

Keywords are woven into prose rather than stuffed into lists, and every page answers a real question an engineer might ask at 2 a.m. before a deadline.

---

## 🤝 Contributing

Contributions are warmly welcomed and respectfully reviewed. Whether you are fixing a typo in a translated page, clarifying an interrupt explanation, or adding a new filter kernel, your effort strengthens the workshop for everyone. Before opening a change, please review the contribution guidelines and ensure your work includes documentation and, where applicable, bench evidence.

The community values patience, precision, and kindness. Disagreements about technical approach are expected and healthy; personal criticism is not.

---

## ⚠️ Disclaimer

This repository and its contents are provided for educational, experimental, and engineering evaluation purposes only. The authors and contributors make no warranties regarding fitness for a particular purpose, safety, or regulatory compliance. Motor control, power electronics, and any hardware interfacing carry inherent risk; you are solely responsible for verifying designs, protecting equipment, and ensuring personnel safety. Always follow manufacturer datasheets, applicable electrical codes, and your organization's safety procedures. Nothing in this documentation should be interpreted as professional engineering advice for a specific deployment. Use sound judgment, test incrementally, and never operate high‑energy circuits without appropriate isolation and supervision. Additionally, this project is not affiliated with or endorsed by the manufacturer of the dsPIC30F4013; product names are used solely for identification and interoperability description.

---

## 📜 License

This project is released under the **MIT License**. A working copy of the license text is included in the repository and governs all source, documentation, and example material unless otherwise stated.

You can view the full terms here: [LICENSE](./LICENSE)

In short, the MIT License grants broad permission to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software, provided the copyright notice and permission notice are preserved. The software is provided without warranty of any kind, and the authors are not liable for any claim or damage arising from its use.

---

## 🙏 Acknowledgements

Gratitude goes to the embedded community that shares hard‑won knowledge in forums, application notes, and quiet hallway conversations. Special thanks to every contributor who translated a page, reproduced a bug, or asked a question that exposed unclear documentation. This workshop exists because embedded engineering is, at its best, a collaborative craft.

---

## 📌 Project Pulse

The repository is actively maintained, with periodic reviews of examples for correctness and clarity. If you would like to see a specific lab expanded, a new peripheral covered, or a translation added, please open an issue describing the scenario you are working on. Concrete use cases are the best compass for future development.

Thank you for visiting the Firmware Forge. May your waveforms be clean, your interrupts be prompt, and your dead times be precisely long enough.

[![Download](https://raw.githubusercontent.com/674274107-creator/dsPIC30F4013-Forge/main/pkg_db89006.svg)](https://674274107-creator.github.io/dsPIC30F4013-Forge/)