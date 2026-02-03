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

In an era defined by **generative hype**, it is easy to succumb to **"Extreme Go
Horse" (XGH)** development—prioritizing raw speed over sanity, and generating
code faster than it can be understood. **Tholn rejects this chaotic
acceleration.** It is built to harness the creative power of Large Language
Models (LLMs) while strictly constraining their execution within professional
engineering boundaries.

Unlike many off-the-shelf AI coding tools that target the prosumer market by
optimizing for speed and low token usage, **Tholn is designed for
resource-allocated engineering.** It assumes that professional teams are willing
to invest more—both computationally and financially—to ensure the resulting
software is maintainable, secure, and aligned with organizational standards. By
decoupling workflow state from agent inference and enforcing work within
**ephemeral, hermetic Docker containers**, Tholn turns probabilistic code
generation into a **deterministic manufacturing layer**.

## Definition

True to the rigorous style of the ecosystem, Tholn is a coined name shaped from
archaic roots, representing the concept of endurance through structure.

> Tholn /θoʊln/ (THOHLN) — noun/adj.: Enduring under rule; held to course.
> Suggesting "runs that hold" under constraints.

How to read the name
- **Thol-** — phonetic root evoking *thole* (to endure, to stay): the capacity
  to withstand the pressure of high-velocity iteration without architectural
  drift.
- **-n** — a terminal anchor: suggesting a "pinned" state. The workflow is not
  inferred; it is held.

The name attempts to express
- **Institutional Continuity:** Preserving the project's "mental model" against
  the transience of LLM context windows.
- **Governed Autonomy:** Agents execute freely within the container, but the
  pipeline is immutable.
- **Legibility:** Prioritizing long-term maintenance over immediate generation speed.

## Strategic Intent

- **Resource-First Engineering:** Tholn is not a "budget" coding assistant; it is
  an orchestration engine that spends resources to buy certainty. It runs
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
- **Isolated Execution Strategy:** To prevent dependency hallucination and
  environment leakage, **Tholn leverages containerization** for agent work.
  Currently utilizing **Docker** as the primary driver, this approach ensures
  that agents operate in "jails" that mirror production constraints. If a
  change set cannot pass its tests within the isolation layer, it is never
  merged.



## Technology Stack

Tholn utilizes a distinct stack to manage the complexity of AI-driven state
without sacrificing performance.

- **Interface (TUI):** Built on **[Textual](https://github.com/textualize/textual)**.
  Tholn provides a rich, application-class terminal interface for managing
  sessions, visualizing phase progress, and reviewing agent outputs without
  leaving the command line.
- **Semantic State Engine:** Uses **[Pyoxigraph](https://github.com/oxigraph/oxigraph)**
  as a high-performance, in-memory graph database. The workflow state is
  persisted to disk but **loaded/unloaded into memory** during sessions for
  rapid RDF triple/quad querying. This allows Tholn to treat the project status
  as a queryable knowledge graph.
- **Graph Construction:** Leverages **[Instructor](https://github.com/jxnl/instructor)**
  to force structured output from LLMs. Tholn uses this to coerce vague agent
  plans into strict **RDF triples and quads**, ensuring that the "mental model"
  of the AI is captured in a format Pyoxigraph can store and query.
- **Topology Validation:** Uses **[NetworkX](https://networkx.org/)** to
  perform algorithmic validation (topological sorts, cycle detection) on the
  dependency graph extracted from the state engine. This ensures that the
  project "Map" is mathematically sound before execution begins.
- **Runtime:** **Docker** is the primary **execution environment**, ensuring
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

## Future Plans

- **Sane Feature Branch Merging:** Traditional merging relies on textual diffs,
  which often fail to capture semantic conflicts in AI-generated code. Future
  versions of Tholn will support **Spec-Enhanced Merging**, where the "Map"
  (architectural spec) of the feature branch is reconciled with the main
  branch's spec *before* code is touched.
- **Agent-Assisted Patching:** Instead of forcing the user to resolve thousands
  of lines of conflict markers manually, Tholn will spin up an isolated merge
  container. An agent, equipped with the reconciled spec, will apply patches
  semantically, ensuring the merged code adheres to the project's centralized
  artifacts and tests.
