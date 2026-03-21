# Nobel Khandaker, PhD

**Engineering Leader | AI Agents & Distributed Systems | 12+ Years at Microsoft + Startups**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/nobelkhandaker)
[![Blog](https://img.shields.io/badge/Blog-FF5722?style=flat&logo=blogger&logoColor=white)](https://zerodowntime.dev)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:nobel@outlook.com)

I build production AI systems at scale. My work spans multiagent orchestration, LLM infrastructure, and distributed data platforms — from PhD research in multiagent systems (AAAI, AAMAS) to shipping ML-powered products for 10M+ users at Microsoft and startups. I've built engineering teams from zero, led terabyte-scale data platform architecture, and shipped production agentic systems including autonomous tutoring agents and AI knowledge assistants.

Currently exploring **Engineering Manager** roles at frontier AI companies.

---

## Featured projects

### [Tangle](https://github.com/intuitai/tangle) — Agent workflow deadlock & livelock detection <sub>via [intuitai](https://github.com/intuitai)</sub>

Deadlock and livelock detection for multi-agent AI workflows. Monitors agent interactions in real time, detects when agents are stuck (deadlocks via Wait-For Graph cycle detection) or looping without progress (livelocks via ring-buffer pattern matching), and triggers configurable resolution actions.

- Native LangGraph integration with `@tangle_node` and `@tangle_conditional_edge` decorators
- Incremental DFS cycle detection + periodic Kahn's algorithm full scans
- Configurable resolver chain: alert, cancel, tiebreaker prompt injection, webhook escalation
- FastAPI sidecar with REST API + OpenTelemetry OTLP span parsing
- 210 tests across 16 test files with Hypothesis property tests

**Stack:** Python, LangGraph, FastAPI, Pydantic, xxhash, SQLite, OpenTelemetry

### [Reverb](https://github.com/intuitai/reverb) — Semantic response cache with knowledge-aware invalidation <sub>via [intuitai](https://github.com/intuitai)</sub>

A two-tier semantic response cache for LLM applications. Reduces redundant LLM calls by caching both exact (SHA-256, sub-ms) and semantically similar queries (embedding cosine, ~50ms), with automatic invalidation when underlying knowledge base documents change.

- Two-tier lookup: exact hash match → semantic similarity with configurable threshold
- Knowledge-aware invalidation: tracks source document lineage, CDC listeners for change detection
- Pluggable backends: embedding providers (OpenAI, Ollama), vector indices (flat, HNSW), persistence stores
- Standalone HTTP server with REST API, Docker support, and multi-stage builds
- 155 unit tests + 11 integration tests + 2 conformance suites, all race-free

**Stack:** Go, HNSW, SHA-256, cosine similarity, Docker, REST API

### [Artemis](https://github.com/nobelk/Artemis) — LLM-powered multiagent simulation framework

Production-grade framework for orchestrating collaborative AI agents with emergent behaviors. Translates PhD research in multiagent systems into modern LLM-powered agent architectures.

- Modular agent architecture with pluggable LLM backends
- Inter-agent communication with message passing
- Performance metrics, observability, and state management for multi-turn interactions

**Stack:** Python, LangChain, OpenAI API, AsyncIO

### [RAGsearch](https://github.com/nobelk/RAGsearch) — Production RAG search engine

Semantic search engine with hybrid retrieval combining dense embeddings and keyword search, multi-turn conversational interface, citation tracking, and basic adversarial query prevention.

**Stack:** Python, Ollama, Qdrant, FastAPI

---

## Infrastructure & systems libraries

| Project | Description | Language |
|---------|-------------|----------|
| [Resilience4py](https://github.com/nobelk/resilience4py) | Fault-tolerance patterns for distributed systems: circuit breaker, retry, rate limiter, bulkhead | Python |
| [geodistance](https://github.com/nobelk/geodistance) | MCP server for geographic distance calculations via Google Maps API | Python |
| [random-number-server](https://github.com/nobelk/random-number-server) | MCP server for random number generation using meteorological data | Python |
| [pyloglog](https://github.com/nobelk/pyloglog) | LogLog cardinality estimation | Python |
| [count-min-sketch](https://github.com/nobelk/count-min-sketch) | Probabilistic frequency estimation data structure | Python |
| [correlation-logger](https://github.com/nobelk/correlation-logger) | Production logging with request correlation | Python |

---

## What I bring

**AI/ML systems:** LLM agents (GPT-4, Claude), RAG pipelines, multiagent orchestration, ML model serving, vector databases, MCP servers

**Platform engineering:** Distributed systems, Spark/Databricks at terabyte scale, event-driven architecture, 99.9% SLA systems, AWS (Lambda, EC2, EKS, Bedrock), GCP

**Leadership:** Built teams from 0→12 engineers, CTO and VP-level roles, cross-functional product partnerships, hiring and mentorship, Agile at scale

**Languages:** Python, Go, C#, TypeScript, Java, SQL

---

## Research & publications

**PhD, Computer Science** — University of Nebraska–Lincoln (AI, Multiagent Systems, Distributed Systems)

- *A Wiki with Multiagent Tracking, Modeling, and Coalition Formation* — **AAAI 2010** (Top 20 AI Applications)
- *Forming and Scaffolding Human Coalitions with a Multi-Agent Framework* — **AAMAS 2007**
- *A Simulation Tool for Computer Supported Collaborative Learning* — **IEEE Transactions on Systems, Man, and Cybernetics-C (2010)**
- **Othmer Fellowship** recipient

---

## Let's connect

I'm exploring **Engineering Manager** and **Staff Engineer** roles in AI/LLM infrastructure at frontier AI companies.

Interested in: multiagent systems, LLM agent architectures, production AI infrastructure, AI safety and evaluation, engineering leadership at scale.

📧 [nobel@outlook.com](mailto:nobel@outlook.com) · 💼 [LinkedIn](https://linkedin.com/in/nobelkhandaker) · 📝 [zerodowntime.dev](https://zerodowntime.dev)
