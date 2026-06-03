---
title: "AgentNet: Decentralized Evolutionary Coordination for LLM-based Multi-Agent Systems"
title_zh: AgentNet：面向LLM多智能体系统的去中心化进化协调
authors: "Yingxuan Yang, Huacan Chai, Shuai Shao, Yuanyi Song, Siyuan Qi, Renting Rui, Weinan Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tXqLxHlb8Z"
tags: ["query:mas-routing"]
score: 8.0
evidence: 去中心化协调与智能体动态路由
tldr: AgentNet提出一种基于RAG的去中心化框架，使LLM多智能体系统能够在有向无环图中自主进化协调和动态路由，解决了集中式协调的扩展性瓶颈和单点故障问题。实验表明，该方法在协作任务上提升了效率和隐私保护。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1365, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 699, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1376, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1352, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 675, \"height\": 95, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 744, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1402, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-txqlxhlb8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1477, \"height\": 748, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1480, \"height\": 1055, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1284, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 741, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1402, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1402, \"height\": 1379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-txqlxhlb8z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 825, \"label\": \"Table\"}]"
motivation: 现有集中式多智能体协调存在扩展性瓶颈、单点故障和隐私问题。
method: 提出基于RAG的去中心化框架，智能体在有向无环图中自主进化并动态路由协作。
result: 在多种协作任务上验证了可扩展性、效率和隐私保护优势。
conclusion: 去中心化动态路由有效克服了集中式协调的局限，提升了多智能体系统的鲁棒性。
---

## Abstract
The rapid advancement of Large Language Models (LLMs) has catalyzed the development of multi-agent systems, where multiple LLM-based agents collaborate to solve complex tasks.   However, existing systems predominantly rely on centralized coordination, which introduces scalability bottlenecks, limits adaptability, and creates single points of failure.   Additionally, concerns over privacy and proprietary knowledge sharing hinder cross-organizational collaboration, leading to siloed expertise.   To address these challenges, we propose AgentNet, a decentralized, Retrieval-Augmented Generation (RAG)-based framework that enables LLM-based agents to autonomously evolve their capabilities and collaborate efficiently in a Directed Acyclic Graph (DAG)-structured network.   Unlike traditional multi-agent systems that depend on static role assignments or centralized control, AgentNet allows agents to specialize dynamically, adjust their connectivity, and route tasks without relying on predefined workflows.
AgentNet’s core design is built upon several key innovations: (1) Fully Decentralized Paradigm: Removing the central orchestrator, allowing agents to coordinate and specialize autonomously, fostering fault tolerance and emergent collective intelligence. (2) Dynamically Evolving Graph Topology: Real-time adaptation of agent connections based on task demands, ensuring scalability and resilience.
(3) Adaptive Learning for Expertise Refinement: A retrieval-based memory system that enables agents to continuously update and refine their specialized skills.
By eliminating centralized control, AgentNet enhances fault tolerance, promotes scalable specialization, and enables privacy-preserving collaboration across organizations.      Through decentralized coordination and minimal data exchange, agents can leverage diverse knowledge sources while safeguarding sensitive information.      Experimental results demonstrate that AgentNet outperforms traditional centralized multi-agent systems, significantly improving efficiency, adaptability, and scalability in dynamic environments, making it a promising foundation for next-generation autonomous, privacy-respecting multi-agent ecosystems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有基于大语言模型（LLM）的多智能体系统（MAS）大多采用**集中式协调**，依赖中央控制器或静态预定义工作流。这导致三个主要问题：①**扩展性瓶颈**：中央控制器易过载，无法应对大规模协作；②**单点故障**：中央控制器一旦失效，整个系统瘫痪；③**隐私与知识壁垒**：跨组织协作时，各方不愿共享私有数据或专有知识，导致智能体能力孤立。此外，**静态角色定义**使智能体无法根据任务需求动态调整，适应性和效率低下。
- **整体含义**：论文旨在构建一个**去中心化、自组织、可进化、隐私保护**的多智能体协作框架，突破集中式架构的局限，实现鲁棒、高效、可扩展的集体智能。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

### 2.1 核心思想
AgentNet 将多智能体系统建模为**有向无环图（DAG）**，每个智能体包含**路由器（router）**和**执行器（executor）**。路由器负责任务路由（转发、拆分或执行），执行器负责具体任务操作。系统无需中央控制器，任务在智能体之间动态路由，智能体通过**检索增强生成（RAG）**利用历史经验持续学习和专门化。

### 2.2 关键技术细节
- **去中心化网络拓扑**：初始为全连接图，每个智能体维护一个权重矩阵 \( w^m(i,j) \) 表示从智能体 \(i\) 到 \(j\) 的连接强度。完成任务后按以下公式更新：
  \[
  w^{m+1}(i,j) = \alpha \cdot w^m(i,j) + (1 - \alpha) \cdot S(a_i^{m+1}, a_j^{m+1}, t_{m+1})
  \]
  其中 \(\alpha\) 为衰减因子，\(S\) 为成功度量。低于阈值 \(\theta_w\) 的边被剪枝。
- **自适应学习与专门化**：每个智能体维护两个固定容量记忆模块 \( M_{rou}^i \) 和 \( M_{exe}^i \)，存储自身经历的任务轨迹片段（观察、上下文、动作）。新任务到来时，通过语义相似度检索最相关的 \(k\) 个片段，用于增强推理和行动（ReAct 框架）。智能体自动剪枝低价值片段以保持高质量记忆。
- **动态任务分配**：每个任务 \( t = (o_t, c_t, p_t) \) 包含描述、能力需求和优先级。系统根据能力向量匹配选择初始智能体：
  \[
  a_{\text{initial}} = \arg\max_{a_i \in A^m} \{\text{sim}(c_{t_{m+1}}, cv_i^m)\}
  \]
  智能体可执行三种操作：
  - **Forward**：将任务原样转发给更合适的智能体。
  - **Split**：分解任务，自己完成匹配部分，剩余子任务路由给其他智能体。
  - **Execute**：独立完成任务。
  智能体能力向量也通过指数平滑更新。

### 2.3 算法流程（伪代码在附录A）
1. 初始化智能体集合、连接、能力向量、记忆模块。
2. 对每个任务，选择初始智能体。
3. 当前智能体通过路由器决定操作（转发/拆分/执行），并更新任务状态。
4. 任务完成后，更新连接权重，剪枝低权重边。
5. 更新参与智能体的能力向量和记忆模块。

## 3. 实验设计

- **数据集与基准**：
  - **MATH**（数学）：700个训练样本，140个测试样本（7类问题）。
  - **BBH**（逻辑问答）：Big-Bench Hard，627个训练样本，100个测试样本（20个任务）。
  - **API-Bank**（函数调用）：100个训练样本，100个测试样本（7类任务，3个难度级别）。
- **对比方法**：
  - **单智能体基线**：Direct、Chain of Thought、Synapse、Self-Consistency、Self-Refinement。
  - **多智能体基线**：MetaGPT、AFLOW、GPTSwarm、MorphAgent。
- **骨干LLM**：DeepSeek-V3、GPT-4o-mini、Qwen-turbo（三种不同模型）。
- **评价指标**：准确率（MATH、BBH、API-Bank）。
- **额外实验**：
  - **异质性实验**：在BBH上测试不同异质性设置（全同质、LLM异质、技能异质、两者混合），分别使用3个和5个智能体。
  - **消融实验**：路由器效果对比（完全随机、随机操作、随机下一智能体ID、全局路由器）；进化阶段对比（有/无进化）。
  - **可扩展性实验**：不同智能体数量和执行器池大小（3/5/9个智能体，30/40执行器上限）。
  - **网络进化可视化**：展示5个智能体在训练过程中连接权重的变化和专门化形成。
  - **自主专门化分析**：固定执行器池大小，观察不同智能体数量下能力得分分布。

## 4. 资源与算力

论文**未明确说明**使用了何种GPU型号、数量以及训练时长。实验通过调用LLM API（如GPT-4o-mini）完成，配置温度为0.0，最大token数2048，top-p=1.0。推理和训练均依赖外部LLM服务，未提及本地计算资源消耗。因此无法量化算力需求。

## 5. 实验数量与充分性

- **实验组数**：主要性能对比（表1）包含3个数据集 × 3种骨干模型 × 约10种方法，共约90组结果；异质性实验（表2）含8种设置；消融实验（图5、表3）各含5种设置；可扩展性实验（图6）含9种配置；网络进化与专门化分析各含1组展示。
- **充分性评价**：实验较为充分，覆盖了多个任务领域、多种基线、多种骨干模型，并包含异质性、消融、可扩展性等分析。但存在以下不足：
  - 未报告多次运行的统计指标（如标准差、置信区间），结果可能受单次随机性影响。
  - 消融实验仅在BBH上使用GPT-4o-mini进行，未跨任务验证。
  - 部分基线（如MorphAgent）在编程任务上表现异常，可能因训练数据构造问题，但论文未深入讨论。
- **客观公平性**：实验设置详细（附录C、D），包括超参数、记忆限制、路由长度等，具备可重复性。但未提供代码（声明将开源），暂时无法完全验证。

## 6. 主要结论与发现

1. **性能提升**：AgentNet 在MATH（92.86%）、BBH（94.00%）、API-Bank（30.00%）上以DeepSeek-V3为骨干时均取得最佳或次优成绩，显著优于单智能体方法和集中式多智能体基线。
2. **去中心化有效性**：消融实验表明，路由器组件对性能至关重要（完全随机仅54.86%，AgentNet达82.14%），且进化阶段（RAG记忆）显著提升准确率（BBH从76%升至86%）。
3. **异质性影响**：在小型团队（3个智能体）中，全同质设置表现最佳；在大型团队（5个智能体）中，异质性（技能或模型差异）反而提升性能，表明多样性在大规模下有益。
4. **可扩展性与鲁棒性**：随着智能体数量增加，性能稳步提升，网络能自动形成专门化子图，证明系统可扩展且具备容错能力。
5. **自主专门化**：智能体在无需显式指派的情况下，自然分化出擅长不同能力（如推理、语言、数学）的角色，体现进化优势。

## 7. 优点

- **完全去中心化**：无需中央控制器，消除了单点故障，增强了系统鲁棒性和可扩展性。
- **动态拓扑与自适应路由**：连接权重和任务路由随经验实时调整，支持高效协作和负载均衡。
- **检索增强的持续学习**：RAG记忆使智能体从历史成功轨迹中学习，不断优化专业能力，避免遗忘。
- **隐私保护**：数据本地存储，仅共享任务必需信息，适合跨组织协作场景。
- **天然涌现专门化**：系统通过任务驱动自动分化出不同专长，无需人工定义角色。
- **实验设计全面**：覆盖数学、逻辑、函数调用三大领域，对比了多种单/多智能体方法，消融和异质性分析完善。

## 8. 不足与局限

- **异构环境适应不足**：论文指出，当智能体能力差异较大时，任务协调和资源分配仍具挑战，未给出成熟解决方案。
- **大规模路由精确性问题**：当前路由器从有限候选集中选择，当智能体数量剧增（如数百个）时，如何高效准确发现最合适的智能体未被充分探索。
- **无统计显著性报告**：所有结果均为单次准确率，未提供多次运行的误差范围，难以评估结果的稳定性。
- **计算资源未公开**：未说明API调用次数、token消耗、实验耗时等，不利于成本评估。
- **跨任务泛化验证有限**：消融和异质性实验仅在BBH上进行，未在MATH或API-Bank上重复，可能缺乏普适性。
- **未讨论失败案例**：论文未深入分析AgentNet在哪些任务或设置下表现不佳，对局限性讨论略偏理想化。
- **代码未及时开放**：虽承诺开源，但当前无法独立复现，影响可验证性。

（完）
