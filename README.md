# Ali Toygar Abak — Phionyx Research

[![ORCID](https://img.shields.io/badge/ORCID-0009--0002--3718--4010-A6CE39?logo=orcid&logoColor=white)](https://orcid.org/0009-0002-3718-4010)
[![PyPI: phionyx-core](https://img.shields.io/pypi/v/phionyx-core?label=phionyx-core&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/phionyx-core/)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20027534-1682D4)](https://doi.org/10.5281/zenodo.20027534)
[![Measurement Axioms DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.21763430-1682D4)](https://doi.org/10.5281/zenodo.21763430)
[![Substack](https://img.shields.io/badge/Substack-Deterministic_AI_Engineering-FF6719?logo=substack&logoColor=white)](https://phionyxresearch.substack.com)
[![X: @phionyx_ai](https://img.shields.io/badge/X-%40phionyx__ai-000000?logo=x&logoColor=white)](https://x.com/phionyx_ai)

I build runtime governance and evidence infrastructure for agentic AI —
deterministic control paths, measurement discipline, decision evidence, and
auditable execution boundaries.

Phionyx treats large language model output as a **noisy measurement, not a
final answer**. The work puts a governed runtime between an AI system and
real-world action — and, separately, defines a neutral way to write down what
that runtime actually decided, so an outsider can check it. A governed action
carries **policy + a state transition + an abstain / block / rewrite decision +
a replayable evidence record** in one inspectable trace. An optional
[self-claim gate](https://github.com/halvrenofviryel/phionyx-pipeline-mcp)
checks development-agent claims against repository evidence, and a runnable
[control-hardening demo](https://github.com/halvrenofviryel/phionyx-research/tree/main/tools/offagent/demo)
shows what holds, what fails closed, and what stays a documented gap. This sits
**alongside** the emerging agent-governance tooling rather than against it — a
capability boundary, not containment.

## The research programme

Four research lines, each with its own artefact and its own claim boundary:

| Research line | Primary artefact | Public status |
|---|---|---|
| **Runtime governance** | [phionyx-research](https://github.com/halvrenofviryel/phionyx-research) (`pip install phionyx-core`) | implemented / experimental runtime |
| **Runtime evidence** | [ai-runtime-evidence-protocol](https://github.com/halvrenofviryel/ai-runtime-evidence-protocol) (AIREP) | proposed experimental format |
| **Measurement discipline** | [measurement-axioms](https://github.com/halvrenofviryel/measurement-axioms) | published normative research artefact |
| **Persistent causal traces** | [resonatus-ontology](https://github.com/halvrenofviryel/resonatus-ontology) | OWL 2 DL / SHACL ontology artefact |

**Runtime governance** — a canonical pipeline with a state vector, kill switch,
human-in-the-loop queue, ethics and safety gates, and a hash-chained audit
trail (optionally Ed25519-signed). Its founding axiom: **LLM output is a sensor
reading**, governed before it becomes action — not an oracle to be trusted.

**Runtime evidence (AIREP)** — a neutral, vendor- and model-independent record
format: one hash-chained, canonical-JSON record per AI runtime decision — what
was decided, on what basis, and, distinctively, **what the evidence does not
cover**. Checkable offline by two cross-language first-party verifier
implementations (Python + Node) that agree byte-for-byte; it depends on no
Phionyx code. **Experimental** — a proposed open format, not a ratified
standard. Phionyx currently emits RGE records; **no current RGE→AIREP
conformance claim is made** — RGE is being developed toward AIREP
interoperability.

**Measurement discipline** — the doctrine the rest of this is held to: *a
governance system that returned `safe` may have checked nothing.* A governance
verdict is a measurement of a claim about a system, and a measurement that was
not taken must not be reported as one that passed. Seven axioms, a six-value
verdict algebra (`PASS · FAIL · NOT_MEASURED · INCONCLUSIVE · ERROR ·
NOT_APPLICABLE`), and two prohibitions: **an absence is not a result**, and **a
proxy is not the thing**. The release includes an audit of **my own** runtime
against it — none of its findings pass, one was contributed by an outside
reader, and it is documented rather than quietly corrected. No conformance
claim is made about any implementation, mine included.
[CDE-12](https://doi.org/10.5281/zenodo.21631868) is the companion instrument:
criteria for what a system can and cannot *record* about a control decision and
its fate.

**Persistent causal traces** — [Resonatus](https://github.com/halvrenofviryel/resonatus-ontology),
an OWL 2 DL ontology with a SHACL validation profile for processes whose causal
history must remain inspectable over time: [w3id.org/resonatus](https://w3id.org/resonatus).
An ontological model with verification artefacts — it makes no physical or
empirical claim.

## Reviewer evidence — how we try to break our own claims

[**phionyx-conformance**](https://github.com/halvrenofviryel/phionyx-conformance)
runs executable scenarios against our own released tooling and publishes the
results, including the failures: every current scenario finds a real gap, each
result is a frozen machine-readable record, and nothing in it has been
independently reproduced yet — it says so itself. `measurement-axioms` states
what should be measured; AIREP states how a decision should be recorded; this
repository is the standing attempt to falsify our own claims with published
method.

## Adapters & tools

Bridges that export the same runtime evidence into common stacks — each records
events as hash-chained envelopes, optionally Ed25519-signed:

- [phionyx-mcp-server](https://github.com/halvrenofviryel/phionyx-mcp-server) — MCP trust boundary: descriptor hash pinning + an audit chain over third-party MCP tool calls
- [phionyx-pipeline-mcp](https://github.com/halvrenofviryel/phionyx-pipeline-mcp) — the self-claim gate: verifies an agent's own change/test claims against git-diff truth
- [phionyx-eval-inspect](https://github.com/halvrenofviryel/phionyx-eval-inspect) (Inspect AI `.eval` logs) · [phionyx-langchain-langgraph](https://github.com/halvrenofviryel/phionyx-langchain-langgraph) · [phionyx-openai-agents](https://github.com/halvrenofviryel/phionyx-openai-agents) · [phionyx-eval](https://github.com/halvrenofviryel/phionyx-eval) · [phionyx-letta](https://github.com/halvrenofviryel/phionyx-letta) · [phionyx-compliance](https://github.com/halvrenofviryel/phionyx-compliance)

## Reference applications & demonstrations

- [**hearthos**](https://github.com/halvrenofviryel/hearthos) — bounded-authority household AI: a browser demo with policy gates over every suggested action. A reference application, not a product.
- [**trace.phionyx.ai**](https://trace.phionyx.ai) — narrative-coherence for game/NPC and storytelling systems: detects character drift and incoherent state before a scene reaches the player.

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
- Resonatus ontology: [w3id.org/resonatus](https://w3id.org/resonatus) · [DOI](https://doi.org/10.5281/zenodo.21939903)
- Trace (narrative + School RPG demo): [trace.phionyx.ai](https://trace.phionyx.ai) · [@trace_phionyx](https://x.com/trace_phionyx)
- Substack: [phionyxresearch.substack.com](https://phionyxresearch.substack.com)
- X: [@phionyx_ai](https://x.com/phionyx_ai)
- ORCID: [0009-0002-3718-4010](https://orcid.org/0009-0002-3718-4010)

---

If runtime evidence for agentic AI is a problem you have, [watch `phionyx-research`](https://github.com/halvrenofviryel/phionyx-research/subscription) to get email updates when we ship new experiments.
