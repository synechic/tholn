# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/PLACEHOLDER?logo=discord&style=flat)](https://discord.com/widget?id=PLACEHOLDER)

![image](https://repository-images.githubusercontent.com/1148379555/4e948b65-d681-4593-87e5-259b2c3e013b)

## About

**Tholn** is a governance and execution engine designed to withstand the entropy
of modern AI hype. In an era where generative tools often encourage **"Extreme Go
Horse" (XGH)** development—prioritizing raw speed over sanity, and generating code
faster than it can be understood—Tholn serves as a necessary architectural brake
and alignment system. It rejects chaotic acceleration in favor of **measured,
verifiable execution**.

**Tholn** focuses specifically on the **software development and architectural
phases** of engineering. It bridges the gap between high-level system design and
the concrete implementation details required to build it. By enforcing a strict
**Init → Map → Phase X** topology, Tholn ensures that architectural intent is
not lost in translation during the coding process.

To achieve this, Tholn decouples **workflow state** from **agent inference**. It
manages the process timeline externally, preventing agents from skipping steps or
hallucinating progress. Execution is currently offloaded to **ephemeral
containers (initially Docker)**, turning probabilistic code generation into a
**deterministic manufacturing layer** where every commit is the result of a
linear, validated sequence.

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
- **Legibility:** Prioritizing long-term maintenance over immediate generation speed.



### Strategic Intent

- **The "Anti-WORN" Mandate:** In traditional software development, engineers
  spend **60-80% of their time reading code**, not writing it. The introduction
  of unconstrained AI generation threatens to worsen this ratio by flooding
  repositories with opaque, idiosyncratic, **Write Once, Read Never (WORN)**
  logic. Tholn inverts this risk. By outsourcing the *labor* of writing to AI,
  we should be able to enforce *stricter* standardization, not less. Tholn
  provides the tooling to do so, using **Professors** (documentation agents) and
  **Managers** (review agents) to ensure code is legible before it is committed.
- **Linear Process Enforcement:** Staff engineers know that LLMs struggle with
  long-horizon planning. Tholn solves this by enforcing **linear progression**.
  The system tracks exactly which phase the project is in (Init, Map, or specific
  Implementation Phases). Agents cannot "jump ahead" to implementation without a
  validated Map, nor can they commit code without passing the current phase's
  gates. This ensures that progress is actual, not just simulated.
- **Isolated Execution Strategy:** To prevent dependency hallucination and
  environment leakage, **Tholn leverages containerization** for agent work.
  Currently utilizing **Docker** as the primary driver, this approach ensures
  that agents operate in "jails" that mirror production constraints. If the
  change set cannot pass its own tests within the isolation layer, it is never
  merged.
- **Codified Continuity:** Tholn introduces **Centralized Artifacts**—a
  registry of templates, ADRs (Architectural Decision Records), and linting
  rules. Agents are forced to reference these artifacts, ensuring that
  generated code adheres to the organization's specific dialect and standards,
  rather than the generic training data of the model.

### Operational Model

- **Dual-Interface Session Drive:** Designed for the workflow of senior
  integrators. Use the **chat interface** for high-level architectural mapping,
  then drop to **CLI commands** for granular inspection and step re-execution.
- **Phase-Driven Topology:** Development is treated as a finite state machine.
  Tholn enforces a strict progression where architectural mapping must be
  validated before implementation phases begin.
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
