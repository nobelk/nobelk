# Dr. Nobel Khandaker

[![Blog](https://img.shields.io/badge/Blog-outloop.blog-111827?style=flat-square&logo=jekyll&logoColor=white)](https://outloop.blog)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-nobelkhandaker-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/nobelkhandaker)
[![Bluesky](https://img.shields.io/badge/Bluesky-outloop-0285FF?style=flat-square&logo=bluesky&logoColor=white)](https://bsky.app/profile/outloop.bsky.social)
[![DEV](https://img.shields.io/badge/DEV-outloop-0A0A0A?style=flat-square&logo=devdotto&logoColor=white)](https://dev.to/outloop)
[![RSS](https://img.shields.io/badge/RSS-outloop.blog-EA580C?style=flat-square&logo=rss&logoColor=white)](https://outloop.blog/feed.xml)

[![Distributed Systems](https://img.shields.io/badge/Distributed%20Systems-0F766E?style=flat-square)](#featured-work)
[![Multi-Agent Systems](https://img.shields.io/badge/Multi--Agent%20Systems-7C3AED?style=flat-square)](#featured-work)
[![Parallel Simulation](https://img.shields.io/badge/Parallel%20Simulation-BE185D?style=flat-square)](#featured-work)
[![MCP](https://img.shields.io/badge/MCP-0891B2?style=flat-square)](#featured-work)
[![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-F97316?style=flat-square)](#featured-work)

**I design and deliver distributed systems where correctness, liveness, and observability are contractual — and I build the runtimes that enforce them.**

I am a Lead Software Engineer at [Intramotev](https://www.intramotev.com), building safety-critical services for autonomous battery-electric rail vehicles with a small engineering team — systems where fault tolerance is a requirement, not a preference. Outside of work, I build and write about the runtime infrastructure I want to exist.

That work spans two threads that reinforce each other. The first applies classical distributed-systems theory to the failure modes reappearing in agent infrastructure: wait-for graphs for liveness, change-data-capture for cache correctness, Subjective Logic for trust-aware coordination, and OpenTelemetry and MCP integrations designed for production constraints. The second builds concurrency infrastructure — most recently a parallel discrete-event simulation engine designed from first principles for free-threaded Python.

Across both, I hold the same bar: architecture chosen for its failure properties, parallelism derived from structure rather than locks, and correctness demonstrated by deterministic tests. The runtime properties I care about most are the ones that matter when systems meet real load: **liveness, freshness, trust, determinism, backpressure, and operator control**.

## Featured Work

### [llmsim](https://github.com/nobelk/llmsim)

**Parallel discrete-event simulation for the Python 3.14 concurrency era**

llmsim keeps the generator-as-process model popularized by SimPy and rebuilds everything else for free-threaded Python: a clean-break, fully typed, `__slots__`-based sequential core with three tiers of parallelism — parallel Monte Carlo replications across cores, conservative PDES with a barrier safe-window protocol and model-provided lookahead, and in-run compute offload — plus a fourth tier of reproducibility guarantees spanning all of them: same seed, same result, on every backend. Parallelism comes from share-nothing architecture with explicit, narrow communication points, never from locks bolted onto a sequential engine, and the design targets LLM- and agent-driven workloads among its first-class use cases. Full documentation lives at [outloop.blog/llmsim](https://outloop.blog/llmsim/).

`Python 3.14` `free-threading` `subinterpreters` `PDES` `deterministic parallelism`

### [Tangle](https://github.com/nobelk/tangle)

**Deadlock and livelock detection for multi-agent workflows**

Tangle ports textbook liveness analysis into agent runtimes. It maintains a wait-for graph, detects deadlocks with incremental DFS on edge-add plus periodic full scans via Kahn's algorithm, and flags livelocks by matching repeated message digests in a ring buffer. It works as an embedded Python SDK, a LangGraph integration, or a FastAPI sidecar, with resolver chains that turn detections into recovery actions.

`Python` `LangGraph` `OpenTelemetry` `FastAPI`

### [Reverb](https://github.com/nobelk/reverb)

**Semantic response cache with knowledge-aware invalidation**

Reverb is a Go library and HTTP/gRPC service for caching LLM responses without relying on TTLs alone to bound staleness. It uses a two-tier cache for exact and semantic matches, tracks source lineage for every cached response, and invalidates entries by causality when underlying knowledge changes via webhook or NATS CDC. The result is faster systems that do not quietly serve stale answers after the source of truth has moved.

`Go` `gRPC` `HTTP` `NATS` `Redis` `BadgerDB`

### [MultiTrust](https://github.com/nobelk/multitrust)

**Trust runtime for multi-agent systems based on Subjective Logic**

MultiTrust models trust as an opinion triple of belief, disbelief, and uncertainty instead of collapsing everything into a single score. That gives downstream systems a better basis for routing, weighting, gating, and explanation. It provides an SDK with first-class integrations for LangGraph and OpenAI Agents and experimental MCP support, plus evidence ledgers and explainability primitives that make trust decisions auditable.

`Python` `Subjective Logic` `LangGraph` `OpenAI Agents` `MCP`

These projects share a thesis: many "new" agent problems are old distributed-systems problems with new names. The leverage comes from recognizing the isomorphism early and implementing the right runtime abstractions — then proving they hold under failure.

## Engineering Lens

- I design for failure first: stuck workflows, stale data, degraded agents, partial outages, and silent correctness drift.
- I prefer explicit runtime contracts: typed events, deterministic invalidation paths, trust thresholds, resolver policies, and operator-visible telemetry.
- I treat determinism as a testable property — same seed, same result, regardless of how many cores the work lands on.
- I treat observability and recovery as product features, not afterthoughts.

## GitHub Activity

[![Followers](https://img.shields.io/github/followers/nobelk?style=flat-square&logo=github&label=Followers)](https://github.com/nobelk?tab=followers)
[![Stars](https://img.shields.io/github/stars/nobelk?style=flat-square&logo=github&label=Stars)](https://github.com/nobelk?tab=repositories)

[![Contribution graph](https://ghchart.rshah.org/nobelk)](https://github.com/nobelk)

## Writing

I write at [**outloop.blog**](https://outloop.blog): notes on building reliable distributed and multi-agent systems.

- [**Agentic Engineering: From Architecture Document to Delivery Plan**](https://outloop.blog/2026/04/24/agentic-project-planning-from-architecture-to-delivery.html) — Turning an architecture document into an executable, agent-driven delivery plan.
- [**Agentic Engineering: Spec-Driven Development**](https://outloop.blog/2026/04/23/spec-driven-development-with-coding-agents.html) — Decoupling the specification from the implementation so coding agents ship high-quality software.
- [**Agentic Engineering: Taming a Legacy Codebase**](https://outloop.blog/2026/04/22/taming-legacy-codebase-with-claude.html) — A field report on refactoring, race conditions, and technical debt in production systems.
- [**Reverb: A Semantic Cache That Knows When Its Answers Go Stale**](https://outloop.blog/2026/04/22/reverb-semantic-cache-with-knowledge-aware-invalidation.html) — Using source lineage and CDC to invalidate cached answers by causality.
- [**MultiTrust: Subjective Logic as a Runtime for Multi-Agent Trust**](https://outloop.blog/2026/04/22/multitrust-subjective-logic-for-multi-agent-systems.html) — Why scalar trust scores lose the distinction between evidence and uncertainty.
- [**Tangle: Deadlock and Livelock Detection for LangGraph Agents**](https://outloop.blog/2026/04/22/tangle-deadlock-detection-for-langgraph.html) — Applying wait-for graphs and liveness monitoring to agent workflows.

## Elsewhere

- [Blog — outloop.blog](https://outloop.blog)
- [LinkedIn](https://linkedin.com/in/nobelkhandaker)
- [Bluesky](https://bsky.app/profile/outloop.bsky.social)
- [DEV](https://dev.to/outloop)
- [RSS](https://outloop.blog/feed.xml)
