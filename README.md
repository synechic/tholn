# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/1429860101090709579?logo=discord&style=flat)](https://discord.com/widget?id=1429860101090709579)

![image](https://github.com/synechic/tholn/blob/main/assets/banner.png?raw=true)

## About

**Tholn** is a session-driven development engine that bridges the gap between
open-ended AI assistants (like Claude, OpenCode, or OpenHands) and rigid CI/CD
pipelines. **Instead of relying on agents to infer project state or manage their
own execution order, Tholn enforces a strictly defined, stateful workflow.** It
offers a full chat interface and granular CLI controls to drive development, but
offloads the actual work into **isolated execution environments**. To ensure
this isolation is absolute, **Tholn initially requires a local Docker daemon**
to contain all AI coding agents and LLM-driven processes. This ensures that
every "Init → Map → Phase X" cycle produces refined, verifiable change sets—
keeping the AI focused on coding while Tholn manages the process.

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
- **Session integrity:** A development session that doesn't drift into
  hallucination.
- **Constrained freedom:** Agents have full creative power within the container,
  but the workflow itself is immutable.
- **Legibility:** Code that is written to be read, verified, and maintained.

## What Tholn focuses on

- **Externalized State Management:** AI agents are notoriously bad at
  remembering where they are in a complex process. Tholn removes this burden
  entirely. **The workflow state is stored and managed by the system**, not the
  agent. Agents are invoked only to execute specific steps within that state,
  eliminating "meta-prompting" drift.
- **Mandatory Docker Isolation:** To guarantee that "it works on my machine" is
  a fact rather than a hope, **Tholn currently leverages Docker** as the
  primary mechanism for agent interaction. All coding, testing, and refactoring
  steps occur inside transient containers (jails), preventing environment
  leakage and ensuring dependencies are explicit.
- **Dual-Interface Session Drive:** Developers can interact via a **full chat
  interface** for high-level guidance or drop down to **individual CLI
  commands** for granular control. Both interfaces feed into the same state
  engine.
- **Phase-Driven Topology:** Work follows a strict **Init → Map → Phase X**
  progression. Tholn treats software development as a series of verified phases
  rather than a continuous stream of text, allowing for **red/green/refactor**
  cycles that are mechanically enforced.
- **The "Anti-WORM" Mandate:** Tholn is designed to prevent **Write Once, Read
  Never (WORM)** software. It instantiates specific agent roles—**Professors**
  for documentation, **Security Analysts** for auditing, and **Managers** for
  architectural review—to ensure the resulting code is sane, accessible, and
  human-maintainable.
- **Refinement & Merging:** Because execution happens in jails, Tholn produces
  clean, **atomic change sets**. It allows you to **refactor all phases back to
  a specific point**, aligning documentation and tests with code changes before
  merging them into the main branch.

### Why this shape works

- **Deterministic Workflows:** By stripping the "manager" role away from the AI
  and giving it to a stateful engine, we get consistent results.
- **Safe Exploration:** Agents can try (and fail) within a Docker container
  without polluting the host environment or the project history.
- **Thorough Validation:** Since BDD/TDD cycles are enforced by the system (not
  requested by the user), testing is an unavoidable part of the process, not an
  afterthought.

### In short

Tholn provides the fluid, conversational experience of an AI dev partner but
wraps it in a rigid, stateful harness. It mandates Docker-based isolation,
manages the workflow explicitly, and enforces professional engineering standards
to produce software that holds its course.

## Command Line Interface

The current command line is written in Python to prioritize flexibility and
modularity. It serves as the primary entry point for both the interactive chat
session and the discrete step executioners.

```shell
pip install tholn-cli
