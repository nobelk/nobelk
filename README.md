# Dr. Nobel Khandaker

[![Blog](https://img.shields.io/badge/Blog-zerodowntime.dev-111827?style=flat-square&logo=jekyll&logoColor=white)](https://zerodowntime.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-nobelkhandaker-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/nobelkhandaker)
[![RSS](https://img.shields.io/badge/RSS-Zero%20Downtime-EA580C?style=flat-square&logo=rss&logoColor=white)](https://zerodowntime.dev/feed.xml)
[![Distributed Systems](https://img.shields.io/badge/Distributed%20Systems-0F766E?style=flat-square)](#featured-work)
[![Multi-Agent Systems](https://img.shields.io/badge/Multi--Agent%20Systems-7C3AED?style=flat-square)](#featured-work)
[![MCP](https://img.shields.io/badge/MCP-0891B2?style=flat-square)](#featured-work)
[![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-F97316?style=flat-square)](#featured-work)

**Lead software engineer specializing in distributed systems, multi-agent runtimes, and production reliability.**

I lead the design and delivery of systems that make agent workflows behave less like demos and more like real distributed systems: observable, failure-aware, and recoverable under load. My work applies classical ideas from distributed computing to the failure modes that reappear in agent infrastructure: wait-for graphs for liveness, change-data-capture for cache correctness, Subjective Logic for trust-aware coordination, and MCP/OpenTelemetry integrations that make those ideas usable in production.

I care about runtime properties that usually get hand-waved away in agent demos: **liveness, freshness, trust, backpressure, observability, and operator control**.

## Featured Work

### [Tangle](https://github.com/nobelk/tangle)
**Deadlock and livelock detection for multi-agent workflows**

Tangle ports textbook liveness analysis into agent runtimes. It maintains a wait-for graph, detects deadlocks with incremental DFS on edge-add plus periodic full scans via Kahn's algorithm, and flags livelocks by matching repeated message digests in a ring buffer. It ships as a Python SDK, LangGraph integration, and FastAPI sidecar, with resolver chains that turn detections into recovery actions instead of passive alerts.

`Python` `LangGraph` `OpenTelemetry` `FastAPI` `98% coverage`

### [Reverb](https://github.com/nobelk/reverb)
**Semantic response cache with knowledge-aware invalidation**

Reverb is a Go library and HTTP/gRPC service for caching LLM responses without pretending TTLs solve correctness. It uses a two-tier cache for exact and semantic matches, tracks source lineage for every cached response, and invalidates entries by causality when underlying knowledge changes via webhook or NATS CDC. The result is faster systems that do not quietly serve stale answers after the source of truth has moved.

`Go` `gRPC` `HTTP` `NATS` `Redis` `BadgerDB`

### [MultiTrust](https://github.com/nobelk/multitrust)
**Trust runtime for multi-agent systems based on Subjective Logic**

MultiTrust models trust as an opinion triple of belief, disbelief, and uncertainty instead of collapsing everything into a single score. That gives downstream systems a better basis for routing, weighting, gating, and explanation. It ships as an SDK and MCP-capable trust layer, with integrations for LangGraph and OpenAI Agents, plus evidence ledgers and explainability primitives that make trust decisions auditable.

`Python` `MCP` `Subjective Logic` `LangGraph` `OpenAI Agents`

These projects share the same thesis: many "new" agent problems are old distributed systems problems with new names. The leverage comes from recognizing the isomorphism early and implementing the right runtime abstractions.

## Engineering Lens

- I design for failure first: stuck workflows, stale data, degraded agents, partial outages, and silent correctness drift.
- I prefer explicit runtime contracts over prompt folklore: typed events, deterministic invalidation paths, trust thresholds, resolver policies, and operator-visible telemetry.
- I treat observability and recovery as product features, not afterthoughts.

## Writing

I write at [**Zero Downtime**](https://zerodowntime.dev): notes on building reliable distributed systems with multiagents.

- [**Tangle: Deadlock and Livelock Detection for LangGraph Agents**](https://zerodowntime.dev/2026/04/22/tangle-deadlock-detection-for-langgraph.html) - Applying wait-for graphs and liveness monitoring to agent workflows.
- [**MultiTrust: Subjective Logic as a Runtime for Multi-Agent Trust**](https://zerodowntime.dev/2026/04/22/multitrust-subjective-logic-for-multi-agent-systems.html) - Why scalar trust scores lose the distinction between evidence and uncertainty.
- [**Reverb: A Semantic Cache That Knows When Its Answers Go Stale**](https://zerodowntime.dev/2026/04/22/reverb-semantic-cache-with-knowledge-aware-invalidation.html) - Using source lineage and CDC to invalidate cached answers by causality.
- [**Taming a Legacy Codebase with Claude: A Field Report on Refactoring, Race Conditions, and Technical Debt**](https://zerodowntime.dev/2026/04/22/taming-legacy-codebase-with-claude.html) - Practical notes on hardening production systems without stopping delivery.

## Elsewhere

- [LinkedIn](https://linkedin.com/in/nobelkhandaker)
- [GitHub](https://github.com/nobelk)
- [RSS](https://zerodowntime.dev/feed.xml)
