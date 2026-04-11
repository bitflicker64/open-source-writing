## Announcement

Recently, the Apache Software Foundation (ASF) officially announced that after four years of incubation and refinement, Apache HugeGraph has officially graduated and been promoted to a Top-Level Project (TLP)!

---

As the first open-source graph database / graph computing system in China, HugeGraph officially began its Apache incubation journey in January 2022. After four years of community collaboration and patient refinement, on January 12, 2026, the graduation vote in the Apache Incubator was passed unanimously with 18 +1 binding votes and 8 +1 non-binding votes[1][2]. On the subsequent February 12, ASF officially announced the graduation notice[3]. At this point, HugeGraph officially graduated from the incubator and became an Apache Top-Level Project.

Achieving this major milestone not only means that the project fully complies with "**The Apache Way**" in terms of trademark, copyright, LICENSE compliance, community governance, and diversity, but also represents HugeGraph fully entering a new chapter of maturity, stability, and large-scale use in enterprise core business.

![](https://fastly.jsdelivr.net/gh/bucketio/img2@main/2026/03/30/1774805588945-ebc651a3-4a4e-4b4e-a0b6-601b3ed057c6.png)

## About Apache HugeGraph

`Apache HugeGraph` is an easy-to-use, high-performance full-stack graph system, covering core components such as [graph database](https://hugegraph.apache.org/docs/quickstart/hugegraph/hugegraph-server/), [graph computing](https://hugegraph.apache.org/docs/quickstart/computing/hugegraph-computer/), and [graph AI](https://hugegraph.apache.org/docs/quickstart/hugegraph-ai/). It supports [Gremlin](https://tinkerpop.apache.org/gremlin.html) and [Cypher](https://opencypher.org/) graph query languages, and provides complete tools for graph visualization, import, backup, and more, helping users easily build AI applications and products based on graph data.

It not only supports high-performance import of hundreds of billions of vertices and edges, and provides millisecond-level relational query capabilities, but also independently developed a distributed storage engine and in-memory computing framework, greatly improving the processing efficiency of massive relational data while ensuring high service availability.

Typical application scenarios of HugeGraph include deep path exploration, user profiling, knowledge graphs, community discovery, and LLM memory. Applicable business domains include attack tracing, financial risk control, social networks, and GraphRAG.

### Apache HugeGraph Core Features and Advantages

1. **Excellent horizontal scalability and high-performance read and write (Graph Database)**

   - Based on a **property graph** design, HugeGraph implements native **distributed HStore storage**, capable of accommodating **hundreds of billions of entities and relationships**. When facing high-frequency OLTP online queries, it can also maintain **millisecond-level ultra-fast read and write response**, breaking through the performance and scalability bottlenecks of traditional graph databases at massive data scale.

![](https://fastly.jsdelivr.net/gh/bucketio/img11@main/2026/03/30/1774805503449-16490bb3-61a6-45f5-a93d-992b9fc3bba2.png)

2. **Dual-engine driven OLAP (graph computing)**
   HugeGraph's graph computing module implements a distributed dual-engine complement of "in-memory + out-of-core":

   - It has Vermeer, an in-memory computing engine developed in Go, designed for daily scenarios within tens of billions of data, near real-time analysis, extremely simple deployment, and built-in Web monitoring, with 20+ classic graph algorithms supported out of the box;
   - It also has Computer, an in-memory and out-of-core combined engine that supports full graph computation at ultra-large scale (hundreds of billions), supports K8s elastic scaling and disk spilling, making HugeGraph's full graph analysis truly achieve "not only able to compute at large scale, but also able to compute quickly".

![](./Images/HugeGraph-Vermeer-Architecture-EN.png)

3. **Exploration of the Memory Layer of Agentic Graph (Graph AI)**

   - The **HugeGraph-AI** repository directly provides **GraphRAG (graph-based retrieval augmented generation)**, natural language to graph query (Text2GQL / Text2Gremlin), automated knowledge graph construction, and 20+ graph learning (GNN) algorithms. This deep integration provides large language models (LLMs) with rigorous topological context, **greatly improving the "hallucination" pain point of large models**, and lowering the engineering threshold for developers to build intelligent graph applications.
   - As the core engine of HugeGraph has matured, its ecosystem construction has also gradually improved. As the core of the ecosystem, HugeGraph-AI integrates vector search and knowledge graph technologies to build deep RAG application solutions. In order to respond to the rapid evolution of large language model (LLM) capabilities and the demands of complex reasoning, we have carried out a deep architectural refactor of HugeGraph-AI.

![](./Images/HugeGraph-LLM-RAG-Architecture-EN.png)

4. **Efficient Import and Visualization Toolchain (Toolchain)**

   - HugeGraph-Toolchain covers the complete graph technology toolchain ecosystem. It includes the **Loader** import tool, which supports high-performance online writing from multiple formats / multiple data sources, and is also compatible with mainstream relational databases, Kafka, and Flink CDC data sources. Combined with query capabilities and the Hubble visualization interface, users can more intuitively complete graph data import, modeling, and analysis.

![](./Images/HugeGraph-Visualization-2.0-EN.png)

5. **Graph Infrastructure (Overall Overview)**

   - The system supports standalone embedded / distributed clusters, and ensures **high availability and data consistency** through the Raft + RocksDB architecture. Combined with the graph computing engine and Graph AI module, it has been running stably in business systems such as **risk control / anti-fraud and real-time feature retrieval**, and has undergone **long-term validation in industrial-grade scenarios**.

![](./Images/HugeGraph-Architecture-Overview-EN.png)

## From 2016 to 2026: HugeGraph's Evolution Path

![](./Images/HugeGraph-History-Timeline-EN.png)

1. **Project Origin (2016 - 2021)**
   HugeGraph was born in 2016 and was initially independently developed to solve data analysis pain points in complex security scenarios. Before being donated to the Apache Foundation, it was the first open-source graph database on GitHub in China. After several years of community refinement, multiple early versions such as 0.5 to 0.12 were released during this period (by the end of 2021).

2. **Entering the Apache Incubator (2022)**
   On January 23, 2022, HugeGraph, as a high-performance scalable graph database + graph computing engine, officially entered the Apache Software Foundation (ASF) incubator, beginning its global open-source journey toward community diversity + university participation.

3. **Incubation Iteration and Ecosystem Expansion (2023 - 2025)**
   During incubation, the HugeGraph community maintained steady major version iteration, completing the transformation from a single graph database into a "**full-stack graph system**":

   - **Version 1.0.0 (February 22, 2023)**: This was the **first official Apache release version** after entering the incubator. This release was contributed to by 30+ contributors with more than 270 pull requests, added 16+ graph algorithms, and comprehensively upgraded the overall technology stack; it also officially released the new Computer repository for graph computing OLAP computation engine, replacing Spark GraphX and supporting full graph computation for billions to hundreds of billions of graph data.
   - **Version 1.2.0 (December 28, 2023)**: Introduced slow query recording / visual documentation, several major performance improvements in core storage + computing, added big data Spark ecosystem support, and merged multiple toolchain components into the toolchain repository for unified management.
   - **Version 1.3.0 (April 1, 2024)**: Added the HugeGraph-AI repository and released its first official version, including the python client and modules such as graph extraction / GNN; greatly improved the Docker deployment experience and provided OpenTelemetry distributed tracing support.
   - **Version 1.5.0 (December 10, 2024)**: As production data volume exceeded hundreds of billions, the previously used `Cassandra/HBase/TiKV` storage layers encountered many performance and maintenance bottlenecks. After two years of refinement, the community released **HStore**, a distributed storage foundation implemented based on `Raft + RocksDB`; it also greatly improved the LLM submodule in the AI repository, supporting lightweight GraphRAG, Text2GQL, and 21 graph machine learning algorithms for practical deployment.
   - **Version 1.7.0 (November 28, 2025)**: Released a new in-memory graph computing engine Vermeer module for small and medium-scale computing scenarios; the computing layer added **in-heap / out-of-heap memory management modules**. This module implements pooled allocation of out-of-heap memory, attempting to solve the industry challenge of OOM in complex graph queries; the Graph AI module, through operator refactoring and the adoption of a brand-new C++ scheduling framework, makes the new architecture more flexible in adapting to the development of Agentic Graph[4].

## Open Source Story

### 1. Diversified Development

Before joining the Apache Foundation, the HugeGraph community mainly had participation from domestic contributors, and most developers were from the same company, making diversity relatively limited. After joining ASF, many overseas and contributors from different organizations began to emerge, bringing more opportunities for communication and collaboration with other communities, and helping the project embrace the "Community Over Code" culture.

However, we also recognize that building a truly global and diverse open-source community is an ongoing process. We still welcome and encourage more contributors from different countries, backgrounds, and organizations to join and participate in shaping the future of HugeGraph together.

![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2026/03/30/1774806361612-3d019ddc-7c6f-411b-a9d8-ae30f0f93dc6.png)

In addition, besides supporting common Flink/Spark/Hadoop ecosystems, we have also actively collaborated with other open-source communities.

- HugeGraph has been integrated as a connector into Apache SeaTunnel and Apache TinkerPop; it has introduced Apache Fory for serialization and off-heap memory management; and actively promotes support for Apache GraphAR graph binary format.
- We also maintain good technical cooperation with open-source projects such as RocksDB / ToplingDB (storage engines), CGraph (graph orchestration), and JRaft (consensus algorithm). We not only use these open-source technologies, but also actively give back to these communities through submitting PRs and providing technical feedback.

### 2. University x Open Source Journey

Since joining Apache incubation, HugeGraph has, for many consecutive years, been selected as an organization project for **GSoC (Google Summer of Code) and OSPP / GLCC** (Open Source Summer / CCF). Dozens of university students from around the world have gained rich open source experience and generous rewards by participating in the development of core functional modules.

![](./Images/HugeGraph-OSPP_EN.png)

Among them, some students with outstanding contributions and deeper accumulation were later nominated as Apache Committers and even became members of the PMC (project core), and also obtained opportunities such as internships at major companies. In the articles that follow, we will gradually update the related experiences and sharing of these students, so that each student can show their own style.

## Technical Roadmap: Graph Infrastructure for the AI Era

With the resurgence of Graph + AI, HugeGraph's development roadmap is focused on three core technical directions:

- **Strong horizontal scalability**: Early graph systems were mostly based on standalone or in-memory architectures. When business vertex and edge data reaches tens of billions or even hundreds of billions, relying on vertical scaling easily hits physical limits. HugeGraph, from its early multi-storage backend support to the latest distributed **HStore**, enables horizontal elastic scaling, stably handling high-frequency concurrent read and write pressure.

- **Native AI integration**: In the wave of LLMs, HugeGraph provides native AI integration capabilities. The independent hugegraph-ai module not only integrates 21 graph learning algorithms, but also supports **MCP + GraphRAG**, directly providing precise graph context for large models and reducing hallucination issues.

- **Low migration barrier**: HugeGraph provides a high-performance data import tool (Loader), which can connect to multiple data sources such as local files, HDFS, Kafka, and Flink CDC. It also supports the SeaTunnel connector for data transformation ecosystem reuse. At the same time, it **supports both Gremlin and Cypher query languages**, making it straightforward for existing graph users to migrate.

- **Fully open and neutral**: As an **Apache Top-Level Project**, HugeGraph maintains 100% open source across the full stack — from graph storage → graph computing → graph visualization / toolchain → graph AI — allowing users to avoid ecosystem lock-in.

![](./Images/HugrGraph-VS-Neo4j.png)

## Setting Sail for the Future

![](./Images/HugeGraph-Cooperation-EN.png)

After years of refinement and four years of Apache incubation, HugeGraph's core graph storage and graph computing engines, along with its distributed foundation, have become stable and reliable. Graduation from the foundation marks the beginning of a new phase of exploration.

The community will continue to deepen the integration of graph and AI ecosystems, strengthen the distributed capabilities of the graph engine, and further promote the combination of graph and LLM to provide stronger support for Agentic evolution.

We extend an open invitation to universities, research teams, and enterprise developers:

1. **For universities and laboratories**: If you lack an industrial-grade data foundation to validate graph algorithms or Graph + LLM research, HugeGraph provides an out-of-the-box graph data platform. Academic teams are welcome to conduct research based on HugeGraph, and even lead the evolution of core modules such as HugeGraph-AI and memory management. Research outcomes can directly reach enterprise users worldwide, enabling high-quality publications (such as `VLDB/SIGMOD`) while contributing to the Apache open-source ecosystem.

2. **For enterprise and individual developers**: HugeGraph is a fully open-source project driven 100% by the Apache Foundation and its community. The project is currently transitioning from a "distributed graph system" to an "intelligent graph service". By joining the community, you can build upon existing work, lead the development of core features, and grow into an Apache Committer or PMC member, contributing to next-generation graph technology.

### Acknowledgements

Every step forward of the community is inseparable from the collective efforts of developers around the world. Whether it is **submitting code**, **reporting issues**, **contributing documentation**, or **participating in discussions**, all have been crucial to HugeGraph's successful promotion to a Top-Level Project.

Special thanks to the ASF mentor team, all IPMC/PPMC members who participated or provided suggestions, and all Committers and Contributors who have long supported the community. (The figure below shows the complete list of GitHub contributors during the incubation period.)

![](https://fastly.jsdelivr.net/gh/bucketio/img9@main/2026/03/30/1774806815020-dbed4b04-5f8a-42d6-bec3-ba527e91df0b.png)

### Messages from the Industry

---

Congratulations to HugeGraph on officially being promoted to an Apache Top-Level Project! As the first open-source graph database / graph system in China, HugeGraph has, during nearly three years of incubation, rooted itself in mainstream fields such as graph computing, big data, and AI, creating its own value.

Working closely with the community and universities, exploring new approaches, cultivating newcomers, and growing together with the next generation. I am honored to have had the opportunity to collaborate with the HugeGraph team, learning from each other through teaching and practice. Wishing HugeGraph continuous iteration and optimization, better implementation, and empowerment of the industry ecosystem.

—— **Chunel Feng**, Founder of the open-source project CGraph

---

Upon learning that Apache HugeGraph has officially graduated from the Apache Incubator and become a Top-Level Project (TLP), as a PPMC member of Apache GeaFlow (Incubating), I would like to extend the most sincere congratulations to HugeGraph on behalf of the Apache GeaFlow community 🎉!

The graduation of HugeGraph not only demonstrates the core graph technologies of high-performance graph databases, but also brings confidence to the entire graph open source ecosystem. At the same time, I believe that in the AI era, graphs can bring more possibilities to AI. I hope to have the opportunity to engage in in-depth exchanges with the HugeGraph community and jointly promote the implementation of graph domain and Graph + AI applications. Once again, congratulations to HugeGraph on its successful graduation!

—— **Zhou Qiang**, Apache GeaFlow PPMC / Core Author

---

Congratulations to Apache HugeGraph on successfully graduating from the incubator and becoming an Apache Top-Level Project! As an important open-source project in the field of graph technology, HugeGraph has made impressive progress in technical capabilities, product evolution, and community development, fully demonstrating the development potential of high-quality open-source infrastructure software.

Since incubation, the project has continuously iterated, and the community has grown steadily, always adhering to the Apache culture of open collaboration and community governance. Today's graduation is an important milestone and also the beginning of a new journey. We look forward to HugeGraph continuously improving its ecosystem and expanding its influence after becoming a top-level project, creating value for more developers and enterprise users worldwide.

—— **Yang Chaokun**, Apache Fory PMC Chair

---

Congratulations to HugeGraph on successfully graduating from the Apache Incubator! Graph systems are important infrastructure for understanding complex relational data and are playing an increasingly important role in scenarios such as knowledge graphs, risk control analysis, and intelligent applications.

By providing high-performance graph storage and query capabilities under a distributed architecture, HugeGraph offers a reliable platform for processing massive relational data. It is great to see HugeGraph continuously improving its technical system and building an active open-source community during incubation. Wishing the project continued growth and broader impact in the field of graph data technology in the future!

### Get Involved in HugeGraph

> If you are interested in graph technology / AI / distributed systems / databases, or would like to contribute to the open source community, you are very welcome to join us!

- **Contribute code**: Visit the [HugeGraph GitHub repository](https://github.com/apache/hugegraph), take the first step by submitting a PR, and participate in the development of graph system features.
- **Report issues and improvement suggestions**: Submit an [Issue](https://github.com/apache/hugegraph/issues) on GitHub to help us identify problems and improve performance.
- **Contribute documentation and tutorials**: Any improvements in documentation will have a positive impact on community members. You are welcome to help with documentation translation, formatting, and more.

**HugeGraph** looks forward to more developers, enterprises, and students joining. Let's work together to advance graph technology and explore the infinite possibilities of graph data.

## References

1. https://lists.apache.org/thread/djkxttgpj08v74r8rqdv3np856g3krlr  
   *(vote process)*

2. https://lists.apache.org/thread/1717m9n576mvvndhzhcjph0n8z10xjn5  
   *(vote result)*

3. https://news.apache.org/foundation/entry/the-apache-software-foundation-announces-new-top-level-project-3

4. https://hugegraph.apache.org/blog/2025/10/29/agentic-graphrag/

5. [Unanimous approval! China's first open-source graph database HugeGraph successfully enters the Apache Incubator](https://mp.weixin.qq.com/s?__biz=MzU5ODY4OTgyNg==&mid=2247483964&idx=1&sn=59d2afebbbccd1715c27ffe4bb03bb0d&scene=21#wechat_redirect)