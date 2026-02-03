# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/PLACEHOLDER?logo=discord&style=flat)](https://discord.com/widget?id=PLACEHOLDER)

![image](https://repository-images.githubusercontent.com/1148379555/4e948b65-d681-4593-87e5-259b2c3e013b)

## About

**Tholn** is a governance and execution engine focused specifically on the
**software development and architectural phases** of engineering. It bridges the
gap between high-level system design and the concrete implementation details
required to build it, ensuring that architectural intent is not lost in
translation during the coding process.

In an era defined by **generative hype**, it is easy to succumb to "Go Horse"
development practices—where speed is prioritized over sanity, and code is
generated faster than it can be understood. **Tholn rejects this chaotic
acceleration.** It is built to harness the creative power of Large Language
Models (LLMs) while strictly constraining their execution within professional
engineering boundaries.

By decoupling workflow state from agent inference and enforcing work within
**ephemeral, hermetic Docker containers**, Tholn turns probabilistic code
generation into a **deterministic manufacturing layer**. It ensures that every
architectural decision is mapped, every line of code is tested, and the
resulting software is as legible as it is functional.

## Definition

True to the rigorous style of the ecosystem, Tholn is a coined name shaped from
archaic roots, representing the concept of endurance through structure.

> Tholn /θoʊln/ (THOHLN) — noun/adj.: Enduring under rule; held to course.
> Suggesting "runs that hold" under constraints.

How to read the name
- **Thol-** — phonetic root evoking *thole* (to endure, to stay): the capacity
  to withstand the entropy of high-velocity iteration without architectural
  drift.
- **-n** — a terminal anchor: suggesting a "pinned" state. The workflow is not
  inferred; it is held.

The name attempts to express
- **Institutional Continuity:** Preserving the project's "mental model" against
  the transience of LLM context windows.
- **Governed Autonomy:** Agents execute freely within the container, but the
  pipeline is immutable.
- **Anti-WORM:** A rejection of "Write Once, Read Never" code in favor of
  legibility and auditability.



### Strategic Intent

- **Externalized State Management:** Staff engineers know that LLMs cannot
  reliably maintain the state of a complex DAG (Directed Acyclic Graph). Tholn
  removes this burden entirely. **The workflow state is stored and managed by
  the system engine.** Agents are stateless workers invoked to transition the
  system from Step A to Step B, eliminating "meta-prompting" drift.
- **Hermetic Execution Environments:** To prevent dependency hallucination and
  environment leakage, **Tholn mandates local Docker isolation**. Agents operate
  within transient "jails" that mirror production constraints. If the refined
  change set cannot pass its own tests within the jail, it is rejected before
  reaching the host.
- **Codified Continuity:** Tholn introduces **Centralized Artifacts**—a
  registry of templates, ADRs (Architectural Decision Records), and linting
  rules. Agents are forced to reference these artifacts, ensuring that
  generated code adheres to the organization's specific dialect and standards,
  rather than the generic training data of the model.

### Operational Model

- **Dual-Interface Session Drive:** Designed for the workflow of senior
  integrators. Use the **chat interface** for high-level architectural mapping,
  then drop to **CLI commands** for granular inspection and step re-execution.
- **Phase-Driven Topology (Init → Map → Phase X):** Development is treated as a
  finite state machine. Tholn enforces a strict progression where architectural
  mapping must be validated before implementation phases begin.
- **The "Anti-WORM" Mandate:** To combat technical debt, Tholn instantiates
  specialized adversarial roles—**Professors** (Documentation/Clarity),
  **Security Analysts** (Vulnerability checks), and **Managers** (Scope/drift
  checks). These agents do not write code; they block it.
- **Refinement & Replay:** Because execution is containerized and state is
  external, Tholn allows for **retroactive refactoring**. You can "rewind" the
  state to the architectural map, modify the map, and replay the phases to
  align documentation and tests with new requirements.

### Why this works for teams

- **Auditability:** Every step of the agent's work is recorded, tested, and
  contained. There are no "magic fixes" that appear without a trace.
- **Standardization:** It forces the AI to behave like a compliant member of the
  engineering team, respecting existing patterns rather than reinventing them.
- **Risk Mitigation:** By enforcing TDD/BDD cycles inside the container, the
  risk of introducing regression is checked at the moment of generation, not in
  CI hours later.

## Command Line Interface

The current command line is written in Python to ensure broad compatibility with
engineering toolchains. It serves as the primary entry point for orchestrating
the session state and containerized workers.

```shell
pip install tholn-cli
```
