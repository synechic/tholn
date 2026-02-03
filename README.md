# Tholn

[![image](https://img.shields.io/pypi/v/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/l/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![image](https://img.shields.io/pypi/pyversions/tholn.svg)](https://pypi.python.org/pypi/tholn)
[![Discord](https://img.shields.io/discord/PLACEHOLDER?logo=discord&style=flat)](https://discord.com/widget?id=PLACEHOLDER)

![image](https://repository-images.githubusercontent.com/1148379555/4e948b65-d681-4593-87e5-259b2c3e013b)

## About

**Tholn** is the guardrail for the AI rush. It is designed for Staff Engineers and
Managers who are under pressure to "adopt AI" but refuse to flood their codebases
with unmaintainable garbage.

Most AI coding tools prioritize speed—generating code as fast as possible to demo
well. This leads to **"Extreme Go Horse"** development: rushing features out the
door without tests, documentation, or design, creating massive technical debt.

**Tholn rejects this.** It assumes that if you are going to use AI, you should
use it to *increase* standards, not lower them. Tholn forces AI agents to work
inside isolated containers (jails), follow strict architectural maps, and pass
rigorous tests before their code is ever allowed into your project. It turns the
AI from a chaotic coding buddy into a compliant junior engineer that follows the
rules.

## Definition

Tholn is a coined name representing the ability to stay the course under pressure.

> Tholn /θoʊln/ (THOHLN) — noun/adj.: Enduring under rule; held to course.
> Suggesting "runs that hold" regardless of the constraints.

How to read the name
- **Thol-** — evoking *thole* (to endure): the ability to withstand the chaos of
  AI iteration without breaking your architecture.
- **-n** — a terminal anchor: suggesting a "pinned" state. The workflow doesn't
  drift; it holds.

## Strategic Intent

- **Paying for Sanity:** Tholn is not a "budget" tool. It is "Resource-Allocated
  Engineering." We explicitly trade cheap, fast inference for expensive, verified
  quality. We run multiple agents (Professors, Security Analysts) to challenge
  and verify code. It costs more to run, but it saves you from fixing bugs at
  3 AM.
- **Stopping "Write Once, Read Never":** Engineers spend 80% of their time
  reading code. Unconstrained AI generates code that is hard to read. Tholn
  fixes this by using "Professor" agents to enforce documentation and
  legibility standards *before* the code leaves the container.
- **No Skipping Steps:** LLMs love to hallucinate progress. Tholn enforces a
  **Linear Workflow** (Init → Map → Phase X). The AI cannot start coding until
  the architecture map is approved. It cannot commit until the tests pass. It
  cannot skip the boring stuff.
- **Jail-Based Safety:** To prevent "it works on my machine" issues, Tholn uses
  **Docker** containers as temporary jails. The AI works inside the jail. If the
  tests don't pass *inside* the jail, the code never merges.



## Technology Stack

Tholn uses modern, robust tools to keep the AI in check and the developer in
control.

- **Interface (TUI):** Built on **[Textual](https://github.com/textualize/textual)**.
  We give you a real dashboard in the terminal—not just a scrolling chat log—so
  you can see exactly where the project stands.
- **Brain (State Engine):** Uses **[Pyoxigraph](https://github.com/oxigraph/oxigraph)**.
  We store the project state in a fast graph database. This lets us query the
  project like a database ("What requirements are missing tests?") rather than
  just guessing.
- **Translator:** Leverages **[Instructor](https://github.com/jxnl/instructor)**.
  This forces the AI to output structured data (JSON/RDF) instead of vague
  paragraphs, so our system can actually understand what the AI is planning.
- **Validator:** Uses **[NetworkX](https://networkx.org/)**. We map out your
  project's dependencies and make sure the plan makes mathematical sense before
  any code is written.
- **Jail:** **Docker** is the isolation layer. Every step happens in a clean
  room.

## Operational Model

- **Dual-Mode Control:** Designed for the workflow of a Lead Dev.
    1.  **Chat Mode:** Use the Textual interface to plan the architecture and
        give high-level orders.
    2.  **CLI Mode:** Drop down to command line script commands to re-run
        specific steps or integrate into CI.
- **Phase-Driven Gates:** Development isn't a stream of consciousness; it's a
  process. You verify the **Map** (Architecture). Then you verify the **Phase**
  (Implementation). If the Map is wrong, you don't code.
- **Refinement & Replay:** Because we store the state externally, you can "time
  travel." If the AI goes down a rabbit hole, you can rewind the state to the
  Architecture Map, tweak the requirements, and have it try again.

## Command Line Interface

The CLI is written in Python. It's the main entry point for starting sessions
and managing the workers.

```shell
pip install tholn-cli
