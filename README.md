# Ali Toygar Abak — Founder of Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build deterministic governance infrastructure for AI systems.

Phionyx treats large language model outputs as noisy cognitive measurements rather than final answers. The goal is to place a verifiable governance runtime between AI systems and end users: safety gates, ethics gates, telemetry, evaluation standards, state evolution, and audit-first control.

## Current Work

- **Phionyx Core SDK** — deterministic AI governance runtime
- **Phionyx MCP Governance Stack** — two-layer runtime evidence for AI coding agents (Claude Code, Cursor, Zed, JetBrains): outward MCP trust boundary (descriptor signing, RGE v0.2 envelope, audit chain) + inward self-claim gate (three-layer verification over the agent's own "fixed / tested / changed" declarations); both share one trace per session
- **HearthOS** — bounded-authority household AI: the operating principle from Volume I of the Governance Trilogy, demonstrated end-to-end in three browser-only modules (Diagnostic, Weekly Reset, Boundary Script) backed by an open-source TypeScript reference implementation and a free printable Starter Kit
- **Phionyx Evaluation Standard** — behavioural reliability, safety, coherence, determinism, and long-term stability evaluation
- **Governance Node Architecture** — multi-gate AI control and release model
- **Trace / Wheel & Balance** — educational and narrative ecosystem for resilience, decision-making, and non-violent RPG-based learning

## Core Principles

- LLM output is not truth; it is a signal requiring governance.
- AI systems need runtime control, not only prompt-level safety.
- Safety, coherence, and telemetry should be structured before response release.
- Evaluation must include behavioural stability, not only benchmark performance.
- Human-facing AI should be explainable, auditable, and interruptible.

## Public Repositories

- [phionyx-research](https://github.com/halvrenofviryel/phionyx-research) — deterministic AI runtime governance for LLM systems (Python; PyPI: `phionyx-core`)
- [phionyx-mcp-server](https://github.com/halvrenofviryel/phionyx-mcp-server) — MCP trust boundary governance: descriptor signing, RGE v0.2 envelope, tamper-evident audit chain (aligned with arXiv:2512.06556 threat taxonomy)
- [phionyx-pipeline-mcp](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — self-governance MCP for Claude Code: three-layer verification gate (LLM declaration → git diff → physics gate) over the agent's own "fixed / tested / changed" claims
- [phionyx-evaluation-standard](https://github.com/halvrenofviryel/phionyx-evaluation-standard) — vendor-independent evaluation standard for agentic AI runtimes
- [hearthos](https://github.com/halvrenofviryel/hearthos) — bounded-authority household AI orchestration; TypeScript reference implementation, browser-only demo, Starter Kit PDF (AGPL-3.0)

## Latest writing

- **MCP Connects Tools. Runtime Evidence Keeps Agents Accountable.** (2026-05-19) — https://x.com/phionyx_ai/status/2056811861782274094

## Links

- Website: https://phionyx.ai
- HearthOS demo: https://phionyx.ai/hearthos
- Substack: https://phionyxresearch.substack.com
- X: https://x.com/phionyx_ai
