# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model output as a **noisy measurement, not a final answer**. The work
puts a verifiable runtime between an AI system and real-world action — and, separately, defines a
neutral way to write down what that runtime actually decided, so an outsider can check it.

## Three things I work on

These are distinct and must not be cross-attributed — each has its own home.

### 1 · phionyx-research — the deterministic runtime engine

The engine (`phionyx-core`, **v0.7.2** on PyPI): a 46-block canonical pipeline (contract v3.8.0) with a
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
- AI systems need runtime control, not only prompt-level safety.
- Safety, coherence, and telemetry should be structured before a response is released.
- Evaluation must include behavioural stability, not only benchmark performance.
- Human-facing AI should be explainable, auditable, and interruptible.

## Links

- Website: [phionyx.ai](https://phionyx.ai)
- AIREP protocol: [github.com/halvrenofviryel/ai-runtime-evidence-protocol](https://github.com/halvrenofviryel/ai-runtime-evidence-protocol)
- Trace (narrative + School RPG demo): [trace.phionyx.ai](https://trace.phionyx.ai) · [@trace_phionyx](https://x.com/trace_phionyx)
- Substack: [phionyxresearch.substack.com](https://phionyxresearch.substack.com)
- X: [@phionyx_ai](https://x.com/phionyx_ai)
- ORCID: [0009-0002-3718-4010](https://orcid.org/0009-0002-3718-4010)

---

If runtime evidence for agentic AI is a problem you have, [watch `phionyx-research`](https://github.com/halvrenofviryel/phionyx-research/subscription) to get email updates when we ship new experiments.
