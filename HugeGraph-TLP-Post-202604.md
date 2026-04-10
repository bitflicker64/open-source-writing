**[公告]**

近日，Apache 软件基金会（ASF）官方宣布，历经四年孵化与打磨，Apache HugeGraph 正式毕业，晋升为顶级项目（TLP）！

---

作为国内第一个开源的图数据库 / 图计算系统， 在 2022 年 1 月，HugeGraph 正式开启了它的 Apache 孵化之旅，历经 4 年的社区共建与耐心打磨，2026 年 1 月 12 日，在 Apache 孵化器以 18 票 +1 binding 和 8 票 non-binding +1， 全票通过了它的毕业投票流程<span class="superscript">[1][2]</span>。随后的 2 月 12 日 ASF 官宣毕业通告<span class="superscript">[3]</span>，至此， HugeGraph 正式从孵化器毕业，晋升为 Apache 顶级项目。

达成这一重大里程碑，不仅标志着项目在商标、版权、LICENSE 合规性、社区治理与多样性上完全符合了 "**The Apache Way**"，更代表着 HugeGraph 全面迈入了成熟、稳定、可被企业级核心业务大规模使用的新篇章。

![](https://fastly.jsdelivr.net/gh/bucketio/img2@main/2026/03/30/1774805588945-ebc651a3-4a4e-4b4e-a0b6-601b3ed057c6.png)

Apache 通告：[The Apache Software Foundation Announces New Top-Level Project - The ASF Blog](https://news.apache.org/foundation/entry/the-apache-software-foundation-announces-new-top-level-project-3)<span class="superscript">[3]</span>

---

## 关于 Apache HugeGraph

`Apache HugeGraph` 是一款易用、高性能的全栈图系统，覆盖 [图数据库](https://hugegraph.apache.org/cn/docs/quickstart/hugegraph/hugegraph-server/)、[图计算](https://hugegraph.apache.org/cn/docs/quickstart/computing/hugegraph-computer/) 与 [图 AI](https://hugegraph.apache.org/cn/docs/quickstart/hugegraph-ai/) 与等核心组件。支持 [Gremlin](https://tinkerpop.apache.org/gremlin.html) 与 [Cypher](https://opencypher.org/) 图查询语言，提供完善的图可视化、导入、备份等工具，助力用户轻松构建基于图数据之上的 AI 应用和产品。

它不仅支持千亿级点边的高性能导入，提供毫秒级的关联查询能力，还自研了分布式存储引擎和内存计算框架，大幅提升海量关联数据的处理效率，同时保障服务高可用性。

HugeGraph 典型应用场景包括深度路径探索、用户画像、知识图谱、社群发现、大模型记忆等， 适用业务领域有如攻击溯源、金融风控、社交网络和 GraphRAG 等。

### Apache HugeGraph 核心特性与优势

1. **优秀的水平扩展与高性能读写 （图数据库）**

   - 基于**属性图**设计，HugeGraph 实现了原生**分布式 HStore 存储**， 可容纳**千亿级的实体与关系**。在面对高频的 OLTP 在线查询时，也能保持**毫秒级的极速读写响应**，突破了传统图数据库在海量数据规模下的性能与扩展瓶颈。

![](https://fastly.jsdelivr.net/gh/bucketio/img11@main/2026/03/30/1774805503449-16490bb3-61a6-45f5-a93d-992b9fc3bba2.png)

2. **双引擎驱动的 OLAP（图计算）**
   HugeGraph 图计算模块实现了 “内存 + 外存” 的分布式双引擎互补：
   - 既有基于 Go 开发的内存计算引擎 Vermeer， 面向用户百亿数据内的日常场景， 面向近实时分析， 部署极简且自带 Web 监控，开箱支持 20+ 经典图算法；
   - 还有支持超大规模（千亿）全图计算，支持 K8s 弹性扩展与磁盘溢写的内外存结合引擎 Computer；让 HugeGraph 的全图分析真正做到了 “既能算得大，更能算得快”。

![](https://fastly.jsdelivr.net/gh/bucketio/img14@main/2026/03/30/1774805779289-0511afea-a38c-423b-a07c-5b27b7d2e118.png)

3. **Agentic Graph 的记忆层探索 （图 AI）**
   - **HugeGraph-AI** 仓库直接提供 **GraphRAG（基于图的检索增强生成）**、自然语言转图查询（Text2GQL / Text2Gremlin）、自动化知识图谱构建以及 20+ 图学习（GNN）算法。这一深度融合为大语言模型（LLM）提供了严谨的拓扑上下文，**大幅改善了大模型的“幻觉”痛点**，降低了开发者构建智能图应用的工程门槛。
   - 随着 HugeGraph 核心引擎的成熟，其生态建设也逐渐完善。作为生态核心，HugeGraph-AI 融合了向量搜索（Vector Search）与知识图谱（Knowledge Graph）技术，构建了深度的 RAG 应用方案。为了应对大语言模型（LLM）能力的飞速演进与复杂推理需求，我们对 HugeGraph-AI 进行了深度架构重构。

![](https://fastly.jsdelivr.net/gh/bucketio/img8@main/2026/03/30/1774806048756-4884319f-0d8f-42ce-b9fb-6354d1a40d30.png)

4. **高效导入与可视化工具链（Toolchain）**
   - HugeGraph-Toolchain 涵盖了图技术全套工具链生态。 既有 **Loader** 导入工具可支持多格式 / 多数据源的在线高性能写入，还兼容主流关系型数据库、Kafka 及 Flink CDC 等数据源。结合查询能力和 Hubble 可视化界面，用户可以更直观地完成图数据的导入、建模与分析。

![](https://fastly.jsdelivr.net/gh/bucketio/img11@main/2026/03/30/1774805928794-10634104-e0fd-4698-a1fd-437c584e869c.png)

5. **图基础设施 （整体概览）**
   - 系统支持单机内嵌 / 分布式集群， 通过 Raft + RocksDB 架构保障 **高可用与数据一致性**。搭配图计算引擎和 Graph AI 模块，已在各大互联网企业 / 银行 **的风控 / 反作弊、实时特征召回** 等业务系统中稳定运行，经历了 **工业级场景的长期检验**。

![](https://fastly.jsdelivr.net/gh/bucketio/img1@main/2026/03/30/1774806014050-ae337ead-0785-40c6-b8d6-107cf689a1e1.png)

## 从 2016 ～ 2026：HugeGraph 的演进路径

![](https://fastly.jsdelivr.net/gh/bucketio/img8@main/2026/03/30/1774806075205-7c2c5098-86a4-4c7a-8d5f-0dd558951712.png)

1. **项目起源（2016 年 - 2021 年）** HugeGraph 诞生于 2016 年，最初是 Baidu 为解决复杂的泛安全场景下数据分析痛点而自主研发的。在捐赠给 Apache 基金会前，是国内第一个 GitHub 开源的图数据库， 经过了几年的社区打磨，期间先后发布了 0.5 ～ 0.12（2021 年底）等多个早期版本。

2. **进入 Apache 孵化器（2022 年）** 2022 年 1 月 23 日，HugeGraph 作为一个高性能的可扩展图数据库 + 图计算引擎，正式进入 Apache 软件基金会（ASF） 孵化器，开启了其走向社区多元化 + 高校参与的全球开源之路。

3. **孵化期迭代与生态扩展（2023 年 - 2025 年）** 在孵化期间，HugeGraph 社区保持了稳定的大版本迭代，完成了从单一图数据库向“**全栈图系统**”的蜕变：

   - **1.0.0 版本（2023 年 2 月 22 日）**：这是其进入孵化器后的**首个 Apache 官方发布版本**。这次的版本由 30+ 位 Contributors 贡献了超过 270 个 Pull Requests， 新增 16+ 图算法并对整体技术栈进行了全面升级； 首次发布了新仓库 Computer 作为图计算 OLAP 计算引擎 （替代 Spark-GraphX 支持百亿～千亿图数据的全图计算）。
   - **1.2.0 版本（2023 年 12 月 28 日）**：引入了慢查询记录 / 可视化文档， 核心的存储 + 计算多项性能大幅增强的改进， 增加大数据 spark 生态支持以及多个工具链组件合并为 toolchain 仓库统一管理。
   - **1.3.0 版本（2024 年 4 月 1 日）**：新增 HugeGraph-AI 仓库并发布第一个正式版本（包括 python-client 和图谱化提取 / GNN 等功能模块），大幅改善了 Docker 部署体验以及提供了 OpenTelemetry 分布式 Trace 支持。
   - **1.5.0 版本（2024 年 12 月 10 日）**：随着生产环境数据量级突破千亿，之前使用的 `Cassandra/HBase/TiKV` 存储层遇到许多性能与维护改造瓶颈，经过 2 年打磨后， 社区发布了基于 `Raft + RocksDB`实现的分布式存储底座**HStore**； 并大幅完善 AI 仓库的 LLM 子模块，支持重落地的轻量 GraphRAG、Text2GQL 以及 21 种图机器学习算法。
   - **1.7.0 版本（2025 年 11 月 28 日）**：针对中小规模计算场景发布了新的内存图计算引擎 Vermeer 模块；计算层支持了堆内 / 堆外**内存管理模块**。该模块实现了堆外内存的池化分配，尝试解决复杂图查询中的 OOM 业内难题； Graph AI 模块通过算子重构与采用全新的 C++ 调度框架，使得新架构更灵活地适配 Agentic Graph 的发展<span class="superscript">[4]</span>。

## 开源故事

### 1. 多元化发展

加入 Apache 基金会之前， HugeGraph 社区主要只有国内的同学参与， 参与的开发者大多也都来自同一企业， 多元化这块薄弱； 加入 ASF 后， 涌现了许多海外和其他团体的贡献者， 也获得了不少其他社区的交流合作机会， 完全拥抱了 "Community Over Code" 的文化。

![](https://fastly.jsdelivr.net/gh/bucketio/img19@main/2026/03/30/1774806361612-3d019ddc-7c6f-411b-a9d8-ae30f0f93dc6.png)

此外，除了支持常见的 Flink/Spark/Hadoop 生态， 我们也积极与其他开源社区携手共进。

- HugeGraph 已作为连接器（Connector）被集成到 Apache SeaTunnel 和 Apache TinkerPop；引入了 Apache Fory 进行序列化与堆外内存管理；积极推进对 Apache GraphAR 的图二进制格式支持。
- 我们还与 RocksDB / ToplingDB（存储引擎）、CGraph（图编排）以及 JRaft（共识算法）等开源项目保持着良好的技术合作。我们不仅使用了这些开源技术，还通过提交 PR 和技术反馈的方式，积极回馈这些开源社区。

### 2. 高校 x 开源旅程

从加入 Apache 孵化以来， HugeGraph 连续多年作为**GSoC（Google Summer of Code） 和 OSPP / GLCC** （开源之夏 / CCF）的入选项目组织，已有几十位来自全球的高校学子通过参与核心功能模块开发， 获得了丰富的开源经历与丰厚的奖金。

![](https://fastly.jsdelivr.net/gh/bucketio/img11@main/2026/03/30/1774806412511-e222407b-65e1-45a9-a7bb-edf23b283ba1.png)

其中一些贡献突出且积累更深的同学， 后续还被提名为 Apache Committer 甚至成为 PMC （项目核心） 的一员， 并获得大厂实习等机会。在之后的文章里， 我们会逐步更新这些同学的相关经历和分享， 让每个同学都能展现自己的风采～

### 3. 用户与传承

作为一个经历了长期打磨的项目，HugeGraph 已在多家互联网头部企业和金融机构的生产环境中稳定运行，包括 BAT、货拉拉、 CVTE 、工商银行等知名科技 / 金融企业都是它的真实用户。2026 年初，代码主仓库在 GitHub 突破 3000+ star。整个生态汇聚了超过 210+ 位贡献者，开发和使用者广泛分布于腾讯、百度、 CVTE、货拉拉、360、网易游戏、字节等 50+ 家企业及海内外各大高校。外部贡献者的代码提交量占比超过 90% ，真正实现了单一主体 → 社区主导的的良好演进。

从 2021 年引入 HugeGraph 到风控场景，Graph 数据模型已经应用在风控全生命周期，支持了 P99 百毫秒以内的在线实时场景查询，满足了实时在线反作弊的高性能要求，祝贺 HugeGraph 顺利毕业！

—— **杨嘉奇**，HugeGraph Committer, 货拉拉大数据架构师

恭喜 HugeGraph 正式成为 Apache 顶级项目！图技术在大模型时代面临着很多新的挑战，但同时也被注入了新的活力，HugeGraph 社区能够紧跟科技潮流，给图底层基建和上层图智能应用都带来了很多创新的思路和实现。目前 HugeGraph 在视源制造、质量、教育等很多场景下都有深度的应用，期待未来共同开拓更多有价值的应用场景和有趣的技术突破。

—— **张世鸣**，HugeGraph PMC 成员 、CVTE 研究员

## 重塑图基础设施

随着 AI + Graph 在当下潮流的再度兴起， 当我们讨论 “未来图技术” 发展时，到底会关注什么？

对于面临技术选型，准备从传统闭源或开源单机图数据库（如 Neo4j）迁移的团队来说，选择 HugeGraph 多为解决真实图场景里的难题。 致敬先行者的同时，我们选择了一条循序渐进， 从适配 → 自研的海量图数据规模的分布式之路：

- **良好的水平扩展性**：早期图系统多偏向单机/内存架构，当业务点边数据达到百亿、甚至千亿级时，靠垂直扩容 （加内存/磁盘） 很容易遇到物理瓶颈。而 HugeGraph 从早期支持的多存储后端， 到最新的分布式 **HStore**，可以像搭积木一样轻松水平弹性扩容，稳定抗住高频的并发读写压力。

- **拥抱 AI 能力**：在 LLM 浪潮下，HugeGraph 选择**提供原生 AI 集成能力**，独立的 hugegraph-ai 模块不仅集成了 21 种图学习算法，而且支持 **MCP + GraphRAG**。能直接为大模型提供精准的 Graph Context，改善大模型幻觉问题。

- **低迁移门槛**：HugeGraph 不仅提供了高性能数据导入工具 loader，可无缝对接本地文件、HDFS、Kafka 以及 Flink CDC 等多数据源； 还支持 seatunnel connector 方便数据转换生态复用和扩展。同时它**兼容 Gremlin 与 Cypher 双查询语言**，方便原有图用户平滑迁移。

- **完全开放中立**：业内图系统的高可用/可视化/集群管理/等企业级特性，往往被限制在“企业版”中或者源码不完全开放。而作为 **Apache 顶级项目**，HugeGraph 保持全栈从 “图存储 → 图计算 → 图可视化 / 工具链 → 图 AI” 的 100% 开源，让用户告别生态上的后顾之忧。

![](https://fastly.jsdelivr.net/gh/bucketio/img1@main/2026/03/30/1774806776655-718ff1af-134d-4bb8-8f9b-8b4edd089c54.png)

## 扬帆远航，开启共建新篇章

![](https://fastly.jsdelivr.net/gh/bucketio/img5@main/2026/03/30/1774806785632-4fc321bf-395c-4489-a9e6-b4f53319f6d9.png)

历经多年打磨与 4 年 Apache 孵化后，HugeGraph 的核心图存储与图计算引擎 + 分布式底座已经相对稳定可靠，并在各大互联网企业、高校的真实场景中完成了 “长期试炼”。从基金会毕业也标志着全新探索的开始。

底座的稳定，意味着上层创新的大幕也正式拉开。 我们深知，图的未来属于 “图 + AI” 与 “大规模复杂计算”。因此，也向高校 / 科研团队、实验室及企业开发者发出深度共建邀请：

1. **对高校与实验室（发顶会、做前沿）：** 如果尚缺工业级的数据底座来验证你的图算法或 Graph + LLM 设想？HugeGraph 为你提供开箱即用的图数据平台。我们非常欢迎高校团队以 HugeGraph 为基座开展科研，甚至主导 HugeGraph-AI、内存管理等硬核模块的后续演进。在 Apache 顶级项目的平台上，你的研究成果将直接触达全球成千上万的企业用户，不仅能产出高质量的学术论文（如 `VLDB/SIGMOD`），更能在 Apache 的开源世界留下你的一片羽毛。
2. **对企业与个人开发者（做主导、中立透明）：** HugeGraph 不属于任何商业公司，它是 100% 由 Apache 基金会 / 社区驱动的， 完全开放的开源项目。目前项目正处于从 “分布式图系统” 向 “智能图服务” 的跨越期。加入社区，无需从零开始设计一个图系统，可以直接站在前人的肩膀上，直接主导核心 Feature 的开发，快速晋升为 Apache Committer 甚至 PMC 成员，共同描绘下一代图技术的未来。

此外，社区也将继续深化图与 AI 生态的结合建设，强化图引擎的分布式能力，推动图与 LLM 进一步结合，为 Agentic 化提供更强的支撑。

---

### 感谢与致辞

社区的每一次进步，都离不开全球开发者的共同努力。无论是 **提交代码**，还是 **报告问题**，**贡献文档**，或 **参与讨论**，都对 HugeGraph 成功晋升为顶级项目都至关重要。

在此，我们要特别感谢所有曾参与 HugeGraph 架构重构、代码贡献、文档翻译与问题反馈的社区成员。特别感谢项目 ASF 导师团队、所有参与/提出建议过的 IPMC/PPMC 成员、以及长期以来为社区答疑解惑的所有 Committer/Contributor。（下图为孵化期间社区 GitHub 贡献者完整榜单）

![](https://fastly.jsdelivr.net/gh/bucketio/img9@main/2026/03/30/1774806815020-dbed4b04-5f8a-42d6-bec3-ba527e91df0b.png)

*除了社区贡献外， 也衷心感谢 Baidu 作为捐赠公司为项目成长提供的开放土壤<span class="superscript">[5]</span>。在此要特别致谢 OSPO 的马红伟老师，对项目的鼎力支持与悉心指导；感谢 TC 的包沉浮老师和 OSPP/GLCC 活动方对开源技术和生态的坚定支持；也感谢曾参与项目做出贡献的刘杰，韩祖利， 张义， 李育林，季石磊等团队成员。最后，感谢参与文档编写/修改，项目发版的同学，以及所有关注和支持项目发展的朋友，限于篇幅无法一一具名，但每一份支持我们都铭记于心，开源之路，感谢同行！*

## 致辞

### Apache 导师寄语

---

作为 Apache HugeGraph 孵化导师，非常高兴能够见证 HugeGraph 从 Apache 孵化器顺利毕业成为顶级项目。祝愿 Apache HugeGraph 在未来的道路上依托开放、多元、协作的社群持续发展，取得更大的成绩！

—— **姜宁**，ASF Member，ASF PPMC，ASF 2022 ～ 2024 年董事会董事

---

热烈祝贺 HugeGraph 顺利从 Apache Incubator 毕业，成为 Apache 顶级项目！这不仅是里程碑，更是对社区治理、工程质量与长期可持续的认可。感谢每一位贡献者的坚持与专业，也感谢用户伙伴的真实反馈与共建。

希望 HugeGraph 继续坚持开放透明、社区优先，吸引更多全球开发者参与，把图的存储/计算能力做得更稳定、更易用、更可信赖。未来可期。

—— **代立冬**，ASF Member，Apache SeaTunnel & DolphinScheduler PMC，白鲸开源科技 CTO

---

热烈祝贺 Apache HugeGraph 顺利完成孵化，正式晋升为 Apache 顶级项目！这一里程碑式的成果不仅是社区多年来协同治理的结晶，也充分体现了国际开源基金会对中国原创技术和治理能力的认可。

期待 HugeGraph 以此为新的起点，持续扩大技术影响力，吸引更多元化的贡献者参与共建，深化与其他 Apache 项目的协同与集成，与全球社区一道，共同维护开放、透明、可持续发展的开源基础设施，为行业创新贡献更大力量。

—— **李钰**，ASF Member，阿里云 EMR & Milvus 负责人，Apache HugeGraph 孵化器导师

---

Congratulations to Apache HugeGraph on graduating as a top-level project. Well done to everyone involved and look forward to its new chapter ahead!

—— **潘娟**，ASF Member，Apache HugeGraph 孵化器导师

---

Apache HugeGraph 经过扎实的建设，形成了稳健又充满生命力的国际化开源社区。它不仅得到产业界的大量关注和应用，也吸引了我们高校的不少学生自发加入社区。

期待成为国际顶级开源项目的 Apache HugeGraph 继续成长，为行业带来顶级的大规模图数据库技术与体验。

—— **黄向东**，清华大学软件学院副研究员，ASF Member，Apache IoTDB PMC Chair

---

恭喜 HugeGraph 成为 Apache 顶级项目。顶级项目不是终点，而是长期主义的起点：把信任写进代码，把共识写进流程，把责任写进时间。愿 HugeGraph 以用户价值为锚、以社区协作为帆，越走越稳，越做越亮。

—— **郭炜**，ASF Member，白鲸开源 CEO

---

热烈祝贺 Apache HugeGraph 完成孵化，晋升为 Apache 顶级项目！

作为前百度开源负责人，亲历 HugeGraph 百度内部萌芽成长的过程，也目睹它捐赠给 Apache 基金会直至最后毕业的历程。

一路走来，最令我欣慰与骄傲的，如今的 PMC 成员已不再局限于百度内部，而是真正吸纳了来自不同公司的开发者。这种跨越组织边界、实现真正社区自治的转变，正是开源项目拥有长久生命力的基石。

感谢所有参与项目的贡献者，尤其感谢 PPMC 成员与导师们在孵化期间的专业指引与坚守。

毕业是新的起点，愿 HugeGraph 继续秉持开放初心，在世界级图数据库的舞台上行稳致远！

—— **谭中意**，前百度开源负责人，ASF Member，Apache bRPC PMC 成员

---

### 业内寄语

---

恭喜 HugeGraph 正式晋升为 Apache 顶级项目！作为国内第一个开源的图数据库 / 图系统，HugeGraph 在近 3 年的孵化过程中，扎根于图计算、大数据、AI 等主流领域，创造了属于自身的价值。

同社区、高校紧密合作，尝试新方案，培养新人，和后浪一起成长。我很荣幸，有机会和 HugeGraph 团队的同学一起合作，教学相长。祝福 HugeGraph 不断迭代优化，更好地落地和赋能行业生态。

—— **Chunel Feng**，开源项目 CGraph 创始人

---

得知 Apache HugeGraph 已正式从 Apache 孵化器毕业，成为了顶级项目（TLP）！我作为 Apache GeaFlow（Incubating）的 PPMC，代表 Apache GeaFlow 社区向 HugeGraph 致以最诚挚的祝贺 🎉！

HugeGraph 的毕业，一方面展示了高性能图数据库的核心图技术，另一方面也为整个图开源生态带入了信心；同时我相信在 AI 时代下，图能够为 AI 时代带来更多的可能性。希望有机会能够和 HugeGraph 社区进行深入交流，共同推动图领域和 Graph + AI 应用的落地。再次祝贺 HugeGraph 顺利毕业！

—— **周强**，Apache GeaFlow PPMC / 核心作者

---

祝贺 Apache HugeGraph 从孵化器顺利毕业成为 Apache 顶级项目！作为图技术领域的重要开源项目，HugeGraph 在技术能力、产品演进和社区建设等方面都取得了令人欣喜的进展，充分展现了高质量开源基础软件的发展潜力。

自孵化以来，项目持续迭代、社区稳步成长，始终坚持开放协作、社区共治的 Apache 文化。今天的毕业是一个重要里程碑，也是一段新征程的开始。期待 HugeGraph 在成为顶级项目后不断完善生态、扩大影响力，为全球更多开发者和企业用户创造价值。

—— **杨朝坤**，Apache Fory PMC Chair

---

祝贺 HugeGraph 顺利从 Apache 孵化器毕业！图系统是理解复杂关系数据的重要基础设施，在知识图谱、风控分析和智能应用等场景中发挥着越来越重要的作用。

HugeGraph 通过在分布式架构下提供高性能图存储与查询能力，为海量关系数据处理提供了可靠的平台。很高兴看到 HugeGraph 在孵化期间持续完善技术体系并建立起活跃的开源社区，祝愿项目在未来持续发展壮大，在图数据技术领域产生更广泛的影响！

—— **包沉浮**，百度杰出架构师

---

祝贺 Apache HugeGraph 正式毕业，成为百度捐赠 Apache 的第 5 个顶级项目（TLP）。作为一款高性能、易用的开源图系统，已在业内金融风控、社交网络、网络安全等生产场景中实现规模化应用与落地。

此次顺利毕业，既是对 HugeGraph 技术成熟度、工程稳定性与社区治理能力的充分认可，也标志着百度及中国开源项目在全球图技术生态中持续取得实质性进展。期待 HugeGraph 在未来的发展中，持续联合全球开发者社区，推动图技术与 AI 技术的深度融合，为智能时代更复杂的数据关联分析与决策场景，提供稳定、可靠的开源基础设施。

—— **臧志**，百度工程效能部总监、OSPO 主任

---

### 参与 HugeGraph

> 如果您对图技术/AI/分布式/数据库等技术感兴趣，或者希望为开源社区贡献力量，非常欢迎加入我们！

- **贡献代码**： 访问 [HugeGraph GitHub 仓库](https://github.com/apache/incubator-hugegraph)，迈出第一步提交 PR，参与图系统功能的开发。
- **报告问题与改进建议**： 在 GitHub 上提交 [Issue](https://github.com/apache/incubator-hugegraph/issues)，帮助我们发现问题，改进性能。
- **贡献文档与教程**： 在文档方面，任何改进都会对社区成员产生积极影响，欢迎你为文档翻译、格式化等方面提供帮助。

**HugeGraph** 期待更多开发者、企业、高校同学的加入。让我们一起推动图技术的发展，探索图数据的无限可能。

## Reference:

[1] https://lists.apache.org/thread/djkxttgpj08v74r8rqdv3np856g3krlr (vote process）
[2] https://lists.apache.org/thread/1717m9n576mvvndhzhcjph0n8z10xjn5 (vote result）
[3] https://news.apache.org/foundation/entry/the-apache-software-foundation-announces-new-top-level-project-3
[4] https://hugegraph.apache.org/blog/2025/10/29/agentic-graphrag/
[5] [全票通过！国内首个开源图数据库 HugeGraph 成功进入 Apache 孵化器](https://mp.weixin.qq.com/s?__biz=MzU5ODY4OTgyNg==&mid=2247483964&idx=1&sn=59d2afebbbccd1715c27ffe4bb03bb0d&scene=21#wechat_redirect)
