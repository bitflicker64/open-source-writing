# Apache HugeGraph Graduates as a Top-Level Project — A New Chapter for Open-Source Graph Tech

In 2016, engineers at Baidu had a problem. Their security and fraud detection systems were drowning in data — hundreds of billions of relationships between users, devices, transactions, and behaviors. No existing graph database could handle it. So they built one.

Ten years later, that internal tool is now an Apache Top-Level Project, fully community-owned, with contributors from across the globe.

On **February 12, 2026**, the Apache Software Foundation (ASF) officially announced that **Apache HugeGraph** had graduated from the Apache Incubator to a Top-Level Project (TLP) — after four years of incubation, 210+ contributors, and real production deployments at some of the largest internet and financial companies in the world.

This post is the story of how it got here, what it can do, and why it matters now more than ever.

---

## What Is Apache HugeGraph?

HugeGraph is a **full-stack, open-source graph system** — not just a database, but an entire ecosystem built around graph data:

- **Graph Database** — High-performance OLTP queries, millisecond-level response, supports hundreds of billions of vertices and edges
- **Graph Computing** — Distributed OLAP engine for large-scale graph analysis
- **Graph AI** — Native GraphRAG, Text2GQL, and 20+ graph machine learning algorithms

It supports both **Gremlin** and **Cypher** query languages, making migration from other graph systems straightforward. And unlike most enterprise graph solutions, the entire stack — storage, compute, visualization, AI — is **100% open source**. No "enterprise edition" gatekeeping.

---

## Core Features at a Glance

### 1. Horizontal Scalability at Massive Scale
Built on a property graph model with native distributed **HStore storage**, HugeGraph handles hundreds of billions of vertices and edges while maintaining millisecond-level query performance. For teams hitting the wall with single-machine or vertically-scaled graph databases, this is the main draw.

### 2. Dual-Engine Graph Computing
HugeGraph's compute layer is built around two complementary engines:
- **Vermeer** — A Go-based in-memory engine for near-real-time analysis on datasets up to tens of billions of nodes. Minimal deployment, built-in web monitoring, 20+ graph algorithms out of the box.
- **Computer** — A distributed engine supporting Kubernetes elastic scaling and disk spillover for full-graph computing at the hundreds-of-billions scale.

### 3. Graph AI — Built for the LLM Era
The **HugeGraph-AI** module is where things get interesting for anyone building on top of LLMs. It provides:
- **GraphRAG** — Graph-based Retrieval-Augmented Generation, giving LLMs precise topological context to reduce hallucinations
- **Text2GQL / Text2Gremlin** — Natural language to graph query translation
- **Automated knowledge graph construction**
- **MCP support** — Direct integration with agent-based workflows
- **21 graph machine learning algorithms**

As LLM applications mature, the need for structured, relationship-aware memory layers is becoming critical. HugeGraph-AI is designed to be exactly that.

### 4. Industrial-Grade Stability
The system runs on a **Raft + RocksDB** architecture for high availability and data consistency. It has been battle-tested in production at major internet companies and financial institutions — fraud detection, real-time feature recall, network security, social graph analysis — for years before this graduation.

---

## The Journey: 2016 – 2026

| Year | Milestone |
|------|-----------|
| 2016 | Born internally at Baidu for security and fraud detection |
| 2018 | Open-sourced on GitHub — first graph database from China to go open source |
| 2022 | Entered the Apache Incubator (January 23, 2022) |
| Feb 2023 | v1.0.0 — First official Apache release; introduced the `Computer` OLAP engine |
| Dec 2023 | v1.2.0 — Major storage and compute performance improvements; unified toolchain |
| Apr 2024 | v1.3.0 — Launched `HugeGraph-AI`; improved Docker deployment |
| Dec 2024 | v1.5.0 — Released **HStore** (Raft + RocksDB distributed storage), replacing third-party backends |
| Nov 2025 | v1.7.0 — Launched **Vermeer** in-memory engine; off-heap memory management for complex queries |
| Feb 2026 | **Graduated as Apache Top-Level Project** |

The graduation vote on January 12, 2026 passed unanimously in the Apache Incubator — 18 binding +1 votes and 8 non-binding +1 votes.

---

## The Open Source Story

### From a Single Company to a Global Community

Before joining Apache, nearly all HugeGraph contributors came from Baidu. That has changed dramatically. Today, over **90% of code commits come from external contributors**, spanning teams at Tencent, CVTE, Huolala (Lalamove), NetEase Games, ByteDance, ICBC, and 50+ other companies and universities.

The project has also deepened its integration with the broader Apache ecosystem — HugeGraph is now a connector in **Apache SeaTunnel** and **Apache TinkerPop**, uses **Apache Fory** for serialization, and actively collaborates with **Apache GraphAR** on graph binary format support.

> *"Since we introduced HugeGraph into our risk control system in 2021, the graph data model has been applied across the full risk lifecycle — supporting sub-100ms P99 latency for real-time anti-fraud queries."*
> — **Yang Jiaqi**, HugeGraph Committer, Big Data Architect at Huolala

> *"HugeGraph has been applied deeply in manufacturing, quality control, and education at CVTE, and we're looking forward to exploring more valuable use cases together."*
> — **Zhang Shiming**, HugeGraph PMC Member, Researcher at CVTE

### Students, Universities, and the Next Generation

HugeGraph has been a participating organization in **Google Summer of Code (GSoC)** and **OSPP** for several consecutive years. Dozens of students from universities worldwide have contributed core modules through these programs. Several have gone on to become Apache Committers and PMC members — and some have landed positions at major tech companies directly as a result.

As of early 2026, the main GitHub repository has surpassed **3,000 stars** with **210+ contributors**.

---

## Why Migrate to HugeGraph?

If your team is evaluating graph databases or considering migration from a commercial solution like Neo4j, here's the honest case for HugeGraph:

**Horizontal scalability** — Neo4j and similar systems were built for single-machine or vertically-scaled architectures. When your data reaches tens or hundreds of billions of edges, vertical scaling hits physical limits fast. HugeGraph's distributed HStore scales horizontally like adding blocks — stable under high-frequency concurrent reads and writes.

**No vendor lock-in** — Enterprise features like high availability, visualization, and cluster management are often locked behind paid tiers in commercial graph databases. HugeGraph is 100% open source across the entire stack, with no hidden enterprise edition.

**AI-native** — The hugegraph-ai module integrates natively with LLM workflows via GraphRAG and MCP. This isn't a bolt-on; it's designed from the ground up to give language models accurate graph context.

**Low migration friction** — Dual Gremlin/Cypher support means existing graph queries work without rewriting. The Loader tool connects directly to HDFS, Kafka, Flink CDC, and local files. SeaTunnel connector support makes data pipeline integration straightforward.

---

## What's Next

With the core graph storage and compute engine now stable, the community's focus is shifting to the frontier: **Graph + AI** and **large-scale complex computation**.

HugeGraph is actively inviting collaboration from:

**Universities and research labs** — If you need an industrial-grade graph platform to validate graph algorithms or Graph + LLM ideas, HugeGraph is available as a ready-to-use base. Research published using HugeGraph reaches thousands of enterprise users globally. The community welcomes teams that want to take ownership of modules like HugeGraph-AI and the memory management engine, with a direct path to publishing in venues like VLDB and SIGMOD.

**Enterprise and individual developers** — HugeGraph belongs to no single company. It's 100% community-driven under the Apache Foundation. The project is currently in transition from a "distributed graph system" to an "intelligent graph service." Contributors can take ownership of core features from day one and move quickly toward Apache Committer and PMC membership.

---

## Get Involved

If you work with graph data, build on LLMs, or just want to contribute to a serious open-source infrastructure project — this is a good time to get involved.

- **GitHub**: [apache/hugegraph](https://github.com/apache/hugegraph)
- **Documentation**: [hugegraph.apache.org](https://hugegraph.apache.org)
- **Issues & Discussions**: GitHub Issues

The community is active, the maintainers are responsive, and there are real mentorship opportunities through GSoC and OSPP for students.

---

## Voices from the Community

> *"Congratulations to Apache HugeGraph on graduating as a top-level project. Well done to everyone involved and look forward to its new chapter ahead!"*
> — **Pan Juan**, ASF Member, Apache HugeGraph Incubator Mentor

> *"HugeGraph's graduation is not just a milestone — it's recognition of community governance, engineering quality, and long-term sustainability. I hope HugeGraph continues to attract a more diverse global contributor base."*
> — **Dai Lidong**, ASF Member, Apache SeaTunnel & DolphinScheduler PMC, CTO of WhaleOps

> *"Apache HugeGraph has formed a robust and vibrant international open-source community. It has attracted a significant number of students from our university to join spontaneously."*
> — **Huang Xiangdong**, Associate Researcher, Tsinghua University School of Software, ASF Member, Apache IoTDB PMC Chair

> *"Graduating as a Top-Level Project is not the finish line — it is the starting point of long-term commitment: trust written into code, consensus written into process, responsibility written into time."*
> — **Guo Wei**, ASF Member, CEO of WhaleOps

> *"The most gratifying thing is that the PMC is no longer limited to Baidu internally — it has truly brought in developers from different companies. This cross-organizational, truly community-driven governance is the foundation of a project's lasting vitality."*
> — **Tan Zhongyi**, Former Head of Baidu Open Source, ASF Member, Apache bRPC PMC Member

---

*Apache HugeGraph is a project of the Apache Software Foundation. All trademarks are the property of their respective owners.*

*References: [Vote Process](https://lists.apache.org/thread/djkxttgpj08v74r8rqdv3np856g3krlr) · [Vote Result](https://lists.apache.org/thread/1717m9n576mvvndhzhcjph0n8z10xjn5) · [ASF Announcement](https://news.apache.org/foundation/entry/the-apache-software-foundation-announces-new-top-level-project-3) · [Agentic GraphRAG Blog](https://hugegraph.apache.org/blog/2025/10/29/agentic-graphrag/)*
