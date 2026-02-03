# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/PLACEHOLDER?logo=discord&style=flat)](https://discord.com/widget?id=PLACEHOLDER)

![image](https://repository-images.githubusercontent.com/1148379555/4e948b65-d681-4593-87e5-259b2c3e013b)

## About

**Tholn** is a session-driven SDLC engine designed to integrate AI-driven development
without sacrificing engineering control. **It represents a simultaneous "Shift-Left"
on risk and "Labor Abstraction" on implementation.** Instead of treating AI as a
black-box generator, Tholn embeds it into a rigorous **Agile/Lean process**, using
**isolated containers** to execute work while maintaining a **stateful,
standardized workflow**. It enables developers to leverage centralized artifacts
and continuity strategies, ensuring that AI agents don't just write code, but
adhere to the project's specific cultural and technical standards.

## Definition

True to the rigorous style of the ecosystem, Tholn is a coined name shaped from
archaic roots, representing the concept of endurance through structure.

> Tholn /θoʊln/ (THOHLN) — noun/adj.: Enduring under rule; held to course.
> Suggests "runs that hold" under constraints.

How to read the name
- **Thol-** — phonetic root evoking *thole* (to endure, to stay): the capacity
  to withstand the entropy of AI generation without breaking architectural
  coherence.
- **-n** — a terminal anchor: suggesting a "pinned" state. The workflow is not
  inferred; it is held.

The name attempts to express
- **Process Continuity:** A development lifecycle that retains context and
  standards over time.
- **Constrained Freedom:** AI agents operate with high autonomy within containers,
  but low autonomy over the process itself.
- **Legibility:** Code that is written to be read, verified, and maintained.



## What Tholn focuses on

- **Risk Shift-Left & Labor Abstraction:** Tholn operationalizes "Shift-Left" by
  forcing architectural discovery, security analysis, and feasibility checks to
  the very start of the cycle. Simultaneously, it achieves "Labor Abstraction"
  by offloading high-volume implementation steps to AI agents running in
  isolated jails.
- **Centralized Artifact Continuity:** Unlike one-off prompts, Tholn leverages a
  library of **centralized development artifacts and standards**. Agents refer
  to established patterns (templates, linting rules, ADRs), ensuring that new
  code feels familiar and maintains continuity with the existing codebase.
- **Mandatory Docker Isolation:** To guarantee that "it works on my machine" is
  a fact rather than a hope, **Tholn leverages Docker** as the primary
  mechanism for agent interaction. All coding, testing, and refactoring steps
  occur inside transient containers, preventing environment leakage.
- **Externalized State Management:** AI agents are notoriously bad at
  managing the SDLC. Tholn removes this burden entirely. **The workflow state is
  stored and managed by the system.** Agents are invoked only to execute
  specific steps within that state, eliminating drift.
- **Dual-Interface Session Drive:** Developers can interact via a **full chat
  interface** for high-level Agile guidance or drop down to **individual CLI
  commands** for granular control. Both interfaces feed into the same state
  engine.
- **The "Anti-WORM" Mandate:** Tholn is designed to prevent **Write Once, Read
  Never (WORM)** software. It instantiates specific agent roles—**Professors**
  for documentation, **Security Analysts** for auditing, and **Managers** for
  architectural review—to ensure the resulting code is sane, accessible, and
  human-maintainable.

### Why this shape works

- **Lean Execution:** By strictly ordering agents and isolating execution, Tholn
  eliminates the "waste" of hallucinated dependencies and circular debugging,
  aligning with Lean software principles.
- **Standardization as Value:** By referencing centralized artifacts, the system
  avoids the fragmentation common in AI-generated codebases.
- **Thorough Validation:** Since BDD/TDD cycles are enforced by the system (not
  requested by the user), testing is an unavoidable part of the process, not an
  afterthought.

### In short

Tholn provides the fluid, conversational experience of an AI dev partner but
wraps it in a rigid, stateful harness. It mandates Docker-based isolation,
enforces Agile/Lean standards, and prioritizes continuity and familiarity to
produce software that holds its course.

## Command Line Interface

The current command line is written in Python to prioritize flexibility and
modularity. It serves as the primary entry point for both the interactive chat
session and the discrete step executioners.

```shell
pip install tholn-cli
