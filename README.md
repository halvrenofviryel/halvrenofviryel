# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model outputs as noisy cognitive measurements rather than final answers. The goal is to place a verifiable governance runtime between AI systems and real-world action: safety gates, ethics gates, telemetry, evaluation standards, state evolution, and audit-first control.

> **Latest (2026-05):** **Phionyx Core v0.5.0** is live on PyPI ([`pip install phionyx-core`](https://pypi.org/project/phionyx-core/)) alongside **5 open-source companion packages** that wire the runtime into MCP hosts, Inspect AI, LangChain / LangGraph, and the OpenAI Agents SDK. **Phionyx Evaluation Standard v0.2.0** ([Released 2026-05-24](https://github.com/halvrenofviryel/phionyx-evaluation-standard/releases/tag/v0.2.0)) ships the **Evidence-Oriented Runtime Telemetry Profile** — a vendor-neutral JSON schema for governance evidence rows. See [phionyx.ai](https://phionyx.ai) for the runtime narrative and where to start.

## Where Phionyx fits

The work organises around three audience entry points, mirrored on [phionyx.ai](https://phionyx.ai):

### Bounded Authority — for safety-first AI providers

> AI output should not directly become action. Phionyx adds deterministic gates between model output and real-world action.

Repos that implement and demonstrate the pattern:

- [**phionyx-research**](https://github.com/halvrenofviryel/phionyx-research) — the core runtime; 46-block canonical pipeline, kill switch, HITL queue, ethics gate, audit chain. `pip install phionyx-core`.
- [**phionyx-mcp-server**](https://github.com/halvrenofviryel/phionyx-mcp-server) — MCP trust boundary; descriptor signing, signed envelopes, audit chain over third-party MCP tool calls.
- [**phionyx-pipeline-mcp**](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — agent self-claim gate; verifies what the agent says it did against the repository's actual diff.
- [**hearthos**](https://github.com/halvrenofviryel/hearthos) — applied: bounded-authority household AI. Browser-only demo + policy gates. The Governance Trilogy, Book 1.

→ Read the full argument: [phionyx.ai/bounded-authority](https://phionyx.ai/bounded-authority)

### Narrative Coherence — for game AI, NPC, and storytelling systems

> When AI characters drift, the story breaks. Phionyx detects narrative drift, state incoherence, and unsafe output before the scene reaches the player.

- [**phionyx-research**](https://github.com/halvrenofviryel/phionyx-research) ships the NPC drift reference trace under [`examples/physics/`](https://github.com/halvrenofviryel/phionyx-research/blob/main/examples/physics/npc_drift_demo.py) — source-inspectable today; end-to-end runnable from the v0.6.0 classifier surface.
- [**trace.phionyx.ai/school**](https://trace.phionyx.ai/school) — School RPG demo (external surface) running the same coherence mechanism end-to-end.

→ Read the full argument: [phionyx.ai/narrative-coherence](https://phionyx.ai/narrative-coherence)

### Reviewer Evidence — for researchers and technical reviewers

> Every claim should be reproducible. Verify Phionyx through installable packages, tests, evidence rows, and public artefacts.

- [**phionyx-evaluation-standard**](https://github.com/halvrenofviryel/phionyx-evaluation-standard) — vendor-independent evaluation standard. v0.2.0 (today) ships the Evidence-Oriented Runtime Telemetry Profile + JSON Schema + worked evidence rows.
- [**phionyx-eval-inspect**](https://github.com/halvrenofviryel/phionyx-eval-inspect) — Inspect AI bridge. Runtime evidence exported into Inspect `.eval` evaluation logs. Replayable agent evaluations.
- [**phionyx_langchain_langgraph**](https://github.com/halvrenofviryel/phionyx-langchain-langgraph) — LangChain + LangGraph adapters. Every chain / tool / LLM event + supervisor handoff becomes a signed, hash-chained envelope.
- [**phionyx_openai_agents**](https://github.com/halvrenofviryel/phionyx-openai-agents) — OpenAI Agents SDK tracing bridge. Every Trace and Span becomes a signed, hash-chained envelope.

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
