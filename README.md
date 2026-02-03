# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/PLACEHOLDER?logo=discord&style=flat)](https://discord.com/widget?id=PLACEHOLDER)

![image](https://repository-images.githubusercontent.com/1148379555/4e948b65-d681-4593-87e5-259b2c3e013b)

## About

**Tholn** is a governance and execution engine designed to withstand the entropy
of modern AI hype. It is built for teams and individuals who view code generation
as an **investment in reliability**, not a race to the bottom on cost.

While many off-the-shelf AI coding tools target the prosumer market—optimizing for
speed and low token usage—**Tholn is designed for resource-allocated engineering.**
It assumes that professional teams are willing to spend more (computationally and
financially) on multi-agent verification loops, rigorous state tracking, and
isolated execution to ensure the resulting software is maintainable and secure.

**Tholn** bridges the gap between high-level system design and concrete
implementation. By decoupling **workflow state** from **agent inference** and
enforcing work within **ephemeral, hermetic Docker containers**, Tholn turns
probabilistic code generation into a **deterministic manufacturing layer**.

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

## Strategic Intent

- **Resource-First Engineering:** Tholn is not a "budget" coding assistant. It
  is an orchestration engine that spends resources to buy certainty. It runs
  multiple adversarial agents (Professors, Security Analysts) in parallel to
  challenge code before it is committed. We trade raw inference cost for
  reduced technical debt.
- **The "Anti-WORN" Mandate:** In traditional software development, engineers
  spend **60-80% of their time reading code**, not writing it. Unconstrained AI
  threatens to flood repos with **Write Once, Read Never (WORN)** logic. Tholn
  inverts this risk. By outsourcing the *labor* of writing to AI, we enforce
  *stricter* standardization. Tholn tooling ensures code is legible and aligned
  with centralized artifacts before any merge.
- **Linear Process Enforcement:** LLMs struggle with long-horizon planning.
  Tholn enforces **linear progression** (Init → Map → Phase X). Agents cannot
  "jump ahead" or hallucinate progress. The system tracks the state, ensuring
  every commit is the result of a validated sequence.
- **Isolated Execution:** To prevent dependency hallucination, Tholn uses
  **Docker** containers as transient "jails." If a change set cannot pass its
  tests within the isolation layer, it is never merged.

## Technology Stack

Tholn leverages a specific set of modern technologies to ensure the CLI/TUI is
responsive and the decision engine is robust.

- **Interface (TUI):** Built on **[Textual](https://github.com/textualize/textual)**.
  Tholn provides a rich, application-class terminal interface for managing
  sessions, visualizing phase progress, and reviewing agent outputs without
  leaving the command line.
- **Decision Graph:** Uses **[Pyoxigraph](https://github.com/oxigraph/oxigraph)**
  for high-performance semantic state resolution. Tholn models the project's
  "world state" as a graph, allowing for complex queries about what has been
  built versus what was planned.
- **Dependency Validation:** Uses **[NetworkX](https://networkx.org/)** to
  construct and validate the Directed Acyclic Graph (DAG) of project
  dependencies. This ensures that the "Map" phase produces a topologically valid
  execution order before agents begin coding.
- **Runtime:** **Docker** is the primary execution substrate, ensuring
  hermetic isolation for all agent actions.

## Operational Model

- **Dual-Interface Session Drive:** Designed for the workflow of senior
  integrators. Use the **Textual TUI** for high-level architectural mapping and
  session management, then drop to **CLI commands** for granular inspection.
- **Phase-Driven Topology:** Development is treated as a finite state machine.
  Tholn enforces a strict progression where architectural mapping must be
  validated via NetworkX before implementation phases begin.
- **Refinement & Replay:** Because execution is containerized and state is
  external (persisted via Pyoxigraph), Tholn allows for **retroactive
  refactoring**. You can "rewind" the state, modify the map, and replay phases
  to align documentation and tests.

## Command Line Interface

The current command line is written in Python to ensure broad compatibility with
engineering toolchains. It serves as the primary entry point for orchestrating
the session state and containerized workers.

```shell
pip install tholn-cli
```
