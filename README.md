# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Measurement Axioms DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.21763430-1682D4)](https://doi.org/10.5281/zenodo.21763430)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model output as a **noisy measurement, not a final answer**. The work
puts a verifiable runtime between an AI system and real-world action — and, separately, defines a
neutral way to write down what that runtime actually decided, so an outsider can check it.

Concretely, a governed action carries **policy + a state transition + an abstain / block / rewrite decision + a replayable evidence record** in one inspectable trace — and the runtime governs *its own* development the same way (a runnable [control-hardening demo](https://github.com/halvrenofviryel/phionyx-research/tree/main/tools/offagent/demo) shows what holds, what fails closed, and what stays a documented gap). This sits **alongside** the emerging agent-governance tooling — signed action receipts, agent audit/replay, enterprise control planes — rather than against it; the contribution is that combination, plus the neutral evidence format below. Cooperative-grade governance with a capability boundary, not containment.

## The doctrine the rest of this is held to

**[The Measurement Axioms](https://github.com/halvrenofviryel/measurement-axioms)** ·
v1.0, August 2026 · [10.5281/zenodo.21763430](https://doi.org/10.5281/zenodo.21763430) · CC BY 4.0

A governance system that returned `safe` may have checked nothing. A governance
verdict is a *measurement* of a claim about a system, and a measurement that was
not taken must not be reported as one that passed.

Seven axioms, five properties of a governance measurement path, and a six-value
verdict algebra — `PASS · FAIL · NOT_MEASURED · INCONCLUSIVE · ERROR ·
NOT_APPLICABLE` — with two prohibitions: **an absence is not a result**, and **a
proxy is not the thing**. Decision outcome, measurement status, enforcement
status and evidence level are four orthogonal fields, not one enum.

The release carries a normative specification (45 numbered requirements, a
record schema, a reference implementation, 314 tests, a checksum manifest) and
an audit of **my own** runtime against it: twelve findings, none with
`verification_status: pass`. One of them was contributed by an outside reader,
in the conformance probe published alongside the doctrine — it returned a
positive result having measured nothing. That is the doctrine's central failure,
produced by the artefact written to detect it, and it is documented rather than
quietly corrected.

No conformance claim is made about any implementation, mine included.

**[CDE-12 — Control-Delivery Evidence](https://doi.org/10.5281/zenodo.21631868)** ·
v0.2, July 2026 — the companion instrument. Twelve criteria and a five-value
scale for reporting what a system can and cannot *record* about a control
decision and its fate. It measures records, not behaviour, and it applies to any
runtime governance artifact, not only mine.

---

## Three things I work on

These are distinct and must not be cross-attributed — each has its own home.
The doctrine above is not a fourth item: it is what the three are measured
against, including where they fall short.

### 1 · phionyx-research — the deterministic runtime engine

The engine (`phionyx-core`, **v0.9.0** on PyPI): a 46-block canonical pipeline (contract v3.8.0) with a
state vector, kill switch, human-in-the-loop queue, ethics and safety gates, and a signed,
hash-chained audit trail. Its founding axiom is that **LLM output is a sensor reading**, governed
before it becomes action — not an oracle to be trusted.

- [**phionyx-research**](https://github.com/halvrenofviryel/phionyx-research) — the core runtime + companion adapters. `pip install phionyx-core`.
- [**phionyx-mcp-server**](https://github.com/halvrenofviryel/phionyx-mcp-server) — an MCP trust boundary: descriptor signing, signed envelopes, and an audit chain over third-party MCP tool calls.

### 2 · AIREP — the AI Runtime Evidence Protocol

A **neutral, vendor- and model-independent** record format: one signed, hash-chained, canonical-JSON
record per AI runtime decision — what was decided, on what basis, and, distinctively, **what the
evidence does not cover**. It is checkable offline by an independent verifier and depends on no
Phionyx code; Phionyx is only its reference implementation and matures by conforming to it.

- [**ai-runtime-evidence-protocol**](https://github.com/halvrenofviryel/ai-runtime-evidence-protocol) — the protocol: normative spec, JSON Schema, binding profiles, and two independent verifiers (Python + Node) that agree byte-for-byte. **Experimental** — a proposed open format, not a ratified standard.

### 3 · Self-governance — binding an AI's own claims to evidence

When an AI assistant helps write the software that governs AI assistants, its own development becomes
the test. This line binds an assistant's **self-claims ("I fixed it / I tested it"), tool calls, and
trace events** into verifiable runtime-evidence chains — gates that check what the agent says it did
against the repository's actual diff, plus a binding hook layer that makes the checks non-optional.

- [**phionyx-pipeline-mcp**](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — an MCP server that verifies an agent's own change/test claims against git-diff truth before they are trusted.
- Adapter bridges export the same runtime evidence into common stacks: [**phionyx-eval-inspect**](https://github.com/halvrenofviryel/phionyx-eval-inspect) (Inspect AI `.eval` logs), [**phionyx-langchain-langgraph**](https://github.com/halvrenofviryel/phionyx-langchain-langgraph), and [**phionyx-openai-agents**](https://github.com/halvrenofviryel/phionyx-openai-agents) — each turning chain / tool / trace events into signed, hash-chained envelopes.

## Applied

The runtime shows up in real products that put bounded authority between AI and action:

- [**hearthos**](https://github.com/halvrenofviryel/hearthos) — bounded-authority household AI: a browser-only demo with policy gates over every suggested action.
- [**trace.phionyx.ai**](https://trace.phionyx.ai) — narrative-coherence for game/NPC and storytelling systems: it detects character drift and incoherent state before a scene reaches the player.

## Core principles

- LLM output is not truth; it is a signal requiring governance.
- A governance verdict is itself a measurement, and one that was not taken must not be reported as one that passed.
- AI systems need runtime control, not only prompt-level safety.
- Safety, coherence, and telemetry should be structured before a response is released.
- Evaluation must include behavioural stability, not only benchmark performance.
- Human-facing AI should be explainable, auditable, and interruptible.

## Links

- Website: [phionyx.ai](https://phionyx.ai)
- The Measurement Axioms: [github.com/halvrenofviryel/measurement-axioms](https://github.com/halvrenofviryel/measurement-axioms) · [DOI](https://doi.org/10.5281/zenodo.21763430)
- CDE-12 (Control-Delivery Evidence): [DOI](https://doi.org/10.5281/zenodo.21631868)
- AIREP protocol: [github.com/halvrenofviryel/ai-runtime-evidence-protocol](https://github.com/halvrenofviryel/ai-runtime-evidence-protocol)
- Trace (narrative + School RPG demo): [trace.phionyx.ai](https://trace.phionyx.ai) · [@trace_phionyx](https://x.com/trace_phionyx)
- Substack: [phionyxresearch.substack.com](https://phionyxresearch.substack.com)
- X: [@phionyx_ai](https://x.com/phionyx_ai)
- ORCID: [0009-0002-3718-4010](https://orcid.org/0009-0002-3718-4010)

---

If runtime evidence for agentic AI is a problem you have, [watch `phionyx-research`](https://github.com/halvrenofviryel/phionyx-research/subscription) to get email updates when we ship new experiments.