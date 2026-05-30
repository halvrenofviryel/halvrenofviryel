# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model outputs as noisy measurements rather than final answers. The goal is to place a verifiable governance runtime between AI systems and real-world action: safety gates, ethics gates, telemetry, evaluation standards, state evolution, and audit-first control.

> **Currently shipping:** **Phionyx Core v0.7.2** is live on PyPI ([`pip install phionyx-core`](https://pypi.org/project/phionyx-core/)) alongside **5 open-source companion packages** that wire the runtime into MCP hosts, Inspect AI, LangChain / LangGraph, and the OpenAI Agents SDK. **Phionyx Evaluation Standard v0.2.0** ([released 2026-05-24](https://github.com/halvrenofviryel/phionyx-evaluation-standard/releases/tag/v0.2.0)) ships the **Evidence-Oriented Runtime Telemetry Profile** — a vendor-neutral JSON schema for governance evidence rows. See [phionyx.ai](https://phionyx.ai) for the runtime narrative and where to start.

## Three distinct things, three version lines

Phionyx ships three things that must not be cross-attributed — each has its own version line:

- **Engine — `phionyx-core`** (the SDK, **v0.7.2** on PyPI): the deterministic engine — 46-block canonical pipeline (contract v3.8.0), state vector, kill switch, HITL, ethics/safety gates, signed audit chain. It is the **reference implementation** that scores **L3 + D3** on the Evaluation Standard. It is *not* claim-governance-rated.
- **Gate — `phionyx-pipeline-mcp`** (stable **v0.2.0**, alpha **v0.3.0a1**): an MCP server that verifies an agent's own "I fixed / I tested / this changed" claims against git-diff truth. This is the component the **Claim-Governance ladder (CG-L0…CG-L5)** rates — stable v0.2.0 = **CG-L2**; alpha v0.3.0a1 = **CG-L3** (opt-in / default-off, already on PyPI), with the stable channel remaining CG-L2. The gate is Layer 3 of the 5-layer governance stack. `phionyx-mcp-server` (**v0.1.0**) is the outward MCP trust boundary.
- **Standard — `phionyx-evaluation-standard`** (**v0.1.1** + **v0.2.0** released; **v0.3** is a draft layer): a vendor-neutral spec defining **L0-L3** (evaluation maturity), **D0-D3** (determinism), and **CG-L0…CG-L5** (claim-governance, the v0.3 draft layer). L0-L3 / D0-D3 rate any runtime; CG-L0…CG-L5 rates the gate. `phionyx-core` is the reference implementation scoring L3 + D3.

## Where Phionyx fits

The work organises around three audience entry points, mirrored on [phionyx.ai](https://phionyx.ai):

### Bounded Authority — for safety-first AI providers

> AI output should not directly become action. Phionyx adds deterministic gates between model output and real-world action.

Repos that implement and demonstrate the pattern:

- [**phionyx-research**](https://github.com/halvrenofviryel/phionyx-research) — the core runtime (`phionyx-core`, the engine, v0.7.2); 46-block canonical pipeline, kill switch, HITL queue, ethics gate, audit chain. `pip install phionyx-core`.
- [**phionyx-mcp-server**](https://github.com/halvrenofviryel/phionyx-mcp-server) — MCP trust boundary (v0.1.0); descriptor signing, signed envelopes, audit chain over third-party MCP tool calls.
- [**phionyx-pipeline-mcp**](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — agent self-claim gate (stable v0.2.0 = CG-L2; alpha v0.3.0a1 = CG-L3); verifies what the agent says it did against the repository's actual diff. This is the component the Claim-Governance ladder rates.
- [**hearthos**](https://github.com/halvrenofviryel/hearthos) — applied: bounded-authority household AI. Browser-only demo + policy gates. The Governance Trilogy, Book 1.

→ Read the full argument: [phionyx.ai/bounded-authority](https://phionyx.ai/bounded-authority)

### Narrative Coherence — for game AI, NPC, and storytelling systems

> When AI characters drift, the story breaks. Phionyx detects narrative drift, state incoherence, and unsafe output before the scene reaches the player.

- [**phionyx-research**](https://github.com/halvrenofviryel/phionyx-research) ships the NPC drift reference trace under [`examples/physics/`](https://github.com/halvrenofviryel/phionyx-research/blob/main/examples/physics/npc_drift_demo.py) — source-inspectable today; end-to-end runnable on the current `phionyx-core` v0.7.2 classifier surface.
- [**trace.phionyx.ai/school**](https://trace.phionyx.ai/school) — School RPG demo (external surface) running the same coherence mechanism end-to-end.

→ Read the full argument: [phionyx.ai/narrative-coherence](https://phionyx.ai/narrative-coherence)

### Reviewer Evidence — for researchers and technical reviewers

> Every claim should be reproducible. Verify Phionyx through installable packages, tests, evidence rows, and public artefacts.

- [**phionyx-evaluation-standard**](https://github.com/halvrenofviryel/phionyx-evaluation-standard) — vendor-independent evaluation standard (v0.1.1 + v0.2.0 released; v0.3 draft layer). Defines **L0-L3** (evaluation maturity), **D0-D3** (determinism), and **CG-L0…CG-L5** (claim-governance, v0.3 draft). v0.2.0 ships the Evidence-Oriented Runtime Telemetry Profile + JSON Schema + worked evidence rows. `phionyx-core` is the reference implementation scoring **L3 + D3**; the CG ladder rates the **gate** `phionyx-pipeline-mcp`.
- [**phionyx-eval-inspect**](https://github.com/halvrenofviryel/phionyx-eval-inspect) — Inspect AI bridge (v0.1.0). Runtime evidence exported into Inspect `.eval` evaluation logs. Replayable agent evaluations.
- [**phionyx-langchain-langgraph**](https://github.com/halvrenofviryel/phionyx-langchain-langgraph) — LangChain + LangGraph adapters (v0.1.0a1). Every chain / tool / LLM event + supervisor handoff becomes a signed, hash-chained envelope.
- [**phionyx-openai-agents**](https://github.com/halvrenofviryel/phionyx-openai-agents) — OpenAI Agents SDK tracing bridge (v0.1.0a1). Every Trace and Span becomes a signed, hash-chained envelope.

→ Read the full Evidence Matrix: [phionyx.ai/evidence](https://phionyx.ai/evidence)

## Core principles

- LLM output is not truth; it is a signal requiring governance.
- AI systems need runtime control, not only prompt-level safety.
- Safety, coherence, and telemetry should be structured before response release.
- Evaluation must include behavioural stability, not only benchmark performance.
- Human-facing AI should be explainable, auditable, and interruptible.

## Latest writing

- **Phionyx Evaluation Standard v0.2.0 — Evidence-Oriented Runtime Telemetry Profile** (2026-05-24 · [Release](https://github.com/halvrenofviryel/phionyx-evaluation-standard/releases/tag/v0.2.0))
- **Persistent Worlds Need Deterministic Governance** (2026-05-22 · Substack post 5 · [link](https://phionyxresearch.substack.com/p/persistent-worlds-need-deterministic))
- **A model saying "fixed" is not evidence** (2026-05-22 · X Article · [link](https://x.com/phionyx_ai/status/2057860001117454685))
- **MCP Connects Tools. Runtime Evidence Keeps Agents Accountable.** (2026-05-19 · X Article · [link](https://x.com/phionyx_ai/status/2056811861782274094))
- **The Phionyx Architecture: Treating LLMs as Sensors, Not Oracles** (2026-05-09 · Substack post 4 · [link](https://phionyxresearch.substack.com/p/the-phionyx-architecture-treating))

## Links

- Website: [phionyx.ai](https://phionyx.ai) — runtime evidence, bounded authority, narrative coherence
- Trace (narrative + School RPG demo): [trace.phionyx.ai](https://trace.phionyx.ai) · [@trace_phionyx](https://x.com/trace_phionyx)
- Substack: [phionyxresearch.substack.com](https://phionyxresearch.substack.com)
- X: [@phionyx_ai](https://x.com/phionyx_ai)
- ORCID: [0009-0002-3718-4010](https://orcid.org/0009-0002-3718-4010)

---

If runtime evidence for agentic AI is a problem you have, [watch `phionyx-research`](https://github.com/halvrenofviryel/phionyx-research/subscription) to get email updates when we ship new experiments.