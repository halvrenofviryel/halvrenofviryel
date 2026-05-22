# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model outputs as noisy cognitive measurements rather than final answers. The goal is to place a verifiable governance runtime between AI systems and end users: safety gates, ethics gates, telemetry, evaluation standards, state evolution, and audit-first control.

> **Latest (2026-05):** Phionyx Core **v0.4.0** is live on PyPI alongside three open-source MCP companion packages — `phionyx-mcp-server` (MCP trust boundary), `phionyx-pipeline-mcp` (agent self-claim gate), and `phionyx-eval-inspect` (Inspect AI bridge). They share one trace per session. See [phionyx.ai/runtime-evidence](https://phionyx.ai/runtime-evidence) for the argument and `pip install phionyx-core==0.4.0` to try it.

## Current Work

- **Phionyx Core SDK** — deterministic AI governance runtime (v0.4.0 live on PyPI)
- **Phionyx MCP Governance Stack** — three-layer runtime evidence for AI coding agents (Claude Code, Cursor, Zed, JetBrains): outward MCP trust boundary (descriptor signing, RGE v0.2 envelope, audit chain) + inward self-claim gate (three-layer verification over the agent's own "fixed / tested / changed" declarations) + Inspect AI interoperability bridge (envelope chain → viewable `.eval` log); all share one trace per session
- **HearthOS** — bounded-authority household AI: the operating principle from Volume I of the Governance Trilogy, demonstrated end-to-end in three browser-only modules (Diagnostic, Weekly Reset, Boundary Script) backed by an open-source TypeScript reference implementation and a free printable Starter Kit
- **Phionyx Evaluation Standard** — behavioural reliability, safety, coherence, determinism, and long-term stability evaluation
- **Governance Node Architecture** — multi-gate AI control and release model
- **Trace / Wheel & Balance** — educational and narrative ecosystem for resilience, decision-making, and non-violent RPG-based learning ([trace.phionyx.ai](https://trace.phionyx.ai) · [@trace_phionyx](https://x.com/trace_phionyx))

## Core Principles

- LLM output is not truth; it is a signal requiring governance.
- AI systems need runtime control, not only prompt-level safety.
- Safety, coherence, and telemetry should be structured before response release.
- Evaluation must include behavioural stability, not only benchmark performance.
- Human-facing AI should be explainable, auditable, and interruptible.

## Public Repositories

- [phionyx-research](https://github.com/halvrenofviryel/phionyx-research) — runtime evidence layer for agentic AI (Python; PyPI: `phionyx-core`)
- [phionyx-mcp-server](https://github.com/halvrenofviryel/phionyx-mcp-server) — MCP trust boundary: descriptor signing, signed envelopes, audit chain over third-party MCP tool calls (aligned with arXiv:2512.06556 threat taxonomy)
- [phionyx-pipeline-mcp](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — agent self-claim gate: verifies what the agent says it did against the repository's actual diff
- [phionyx-eval-inspect](https://github.com/halvrenofviryel/phionyx-eval-inspect) — Inspect AI bridge: Phionyx runtime evidence exported into [Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai) `.eval` evaluation logs (interop-only, no AISI endorsement claim)
- [phionyx-evaluation-standard](https://github.com/halvrenofviryel/phionyx-evaluation-standard) — vendor-independent evaluation standard for agentic AI runtimes
- [hearthos](https://github.com/halvrenofviryel/hearthos) — bounded-authority household AI orchestration; TypeScript reference implementation, browser-only demo, Starter Kit PDF (AGPL-3.0)

## Latest writing

- **A model saying "fixed" is not evidence** (2026-05-22 · X Article) — https://x.com/phionyx_ai/status/2057860001117454685
- **Persistent Worlds Need Deterministic Governance** (2026-05-22 · Substack post 5) — https://phionyxresearch.substack.com/p/persistent-worlds-need-deterministic
- **MCP Connects Tools. Runtime Evidence Keeps Agents Accountable.** (2026-05-19 · X Article) — https://x.com/phionyx_ai/status/2056811861782274094

## Links

- Website: https://phionyx.ai · [runtime evidence campaign page](https://phionyx.ai/runtime-evidence)
- HearthOS demo: https://phionyx.ai/hearthos
- Substack: https://phionyxresearch.substack.com
- X: https://x.com/phionyx_ai

---

If runtime evidence for agentic AI is a problem you have, [watch `phionyx-research`](https://github.com/halvrenofviryel/phionyx-research/subscription) to get email updates when we ship new experiments.
