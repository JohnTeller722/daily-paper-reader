---
title: "From Debate to Equilibrium: Belief‑Driven Multi‑Agent LLM Reasoning via Bayesian Nash Equilibrium"
title_zh: 从辩论到均衡：基于贝叶斯纳什均衡的信念驱动多智能体LLM推理
authors: "Xie Yi, Zhanke Zhou, Chentao Cao, Qiyu Niu, Tongliang Liu, Bo Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=RQwexjUCxm"
tags: ["query:mas-routing"]
score: 6.0
evidence: 基于贝叶斯纳什均衡的多智能体协调推理
tldr: 针对多LLM框架计算成本高且缺乏收敛保证的问题，本文提出ECON范式，将多智能体协调建模为不完全信息博弈，寻求贝叶斯纳什均衡。每个智能体根据对其他智能体策略的信念选择最优响应，实现分布式推理与集中式输出的结合。该方法为多智能体协调路由提供了理论框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1731, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1036, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 964, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1384, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1381, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1494, \"height\": 937, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1631, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 2247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 687, \"height\": 1770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 689, \"height\": 1773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 686, \"height\": 1775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 689, \"height\": 1778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 686, \"height\": 1774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 688, \"height\": 1778, \"label\": \"Table\"}]"
motivation: 多LLM系统计算开销大且缺乏收敛保证，需要更高效的协调机制。
method: 将多智能体协调建模为不完全信息博弈，通过层次化强化学习寻求贝叶斯纳什均衡。
result: 实验表明ECON在多种推理任务上取得更高准确率，同时减少了计算开销。
conclusion: 基于博弈论的均衡方法为多智能体协调路由提供了原则性方案。
---

## Abstract
Multi-agent frameworks can substantially boost the reasoning power of large language models (LLMs), but they typically incur heavy computational costs and lack convergence guarantees. To overcome these challenges, we recast multi-LLM coordination as an incomplete-information game and seek a Bayesian Nash equilibrium (BNE), in which each agent optimally responds to its probabilistic beliefs about the strategies of others. We introduce Efficient Coordination via Nash Equilibrium (ECON), a hierarchical reinforcement-learning paradigm that marries distributed reasoning with centralized final output. Under ECON, each LLM independently selects responses that maximize its expected reward, conditioned on its beliefs about co-agents, without requiring costly inter-agent exchanges.
We mathematically prove that ECON attains a markedly tighter regret bound than non-equilibrium multi-agent schemes. Empirically, ECON outperforms existing multi-LLM approaches by 11.2% on average across six benchmarks spanning complex reasoning and planning tasks. Further experiments demonstrate ECON’s ability to flexibly incorporate additional models, confirming its scalability and paving the way toward larger, more powerful multi-LLM ensembles. The code is publicly available at: https://github.com/tmlr-group/ECON.

---

## 论文详细总结（自动生成）

### 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有多智能体大语言模型（LLM）推理框架（如多智能体辩论 MAD）存在三大瓶颈：① 轮次间高频消息传递导致大量 token 消耗，计算开销大；② 信息量超出上下文窗口容量，阻碍规模化；③ 缺乏收敛性理论保证，有时甚至不如简单的集成或自一致性方法。
- **整体含义**：本文旨在设计一种**原则性、可扩展**的多智能体协调机制，替代高成本的显式通信，同时确保系统能够稳定收敛到最优策略。

---

### 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

#### 核心思想
- 将多 LLM 协调建模为**不完全信息博弈**，求解**贝叶斯纳什均衡（BNE）**。每个智能体基于对其他智能体策略的概率信念（belief）独立选择最大化自身期望奖励的响应，无需直接交换消息。
- 提出 **ECON（Efficient Coordination via Nash Equilibrium）** 框架，采用**分层强化学习**架构：多个 Execution LLM 进行分布式推理，Coordinator LLM 集中输出最终答案。

#### 关键技术细节
1. **问题建模**：形式化为 **DEC-POMDP（分散式部分可观测马尔可夫决策过程）**，定义状态、动作（提示嵌入）、观测、奖励等。
2. **信念网络（Belief Network）**：每个 Execution LLM 维护一个信念网络，将局部轨迹和观测映射为信念状态 \( b_i \)，再生成动作（温度、重复惩罚等参数）。
3. **信念编码器（Belief Encoder）**：汇集所有智能体的信念状态，通过多头注意力生成全局表征 \( E \)。
4. **集中式混合网络（Centralized Mixing Network）**：将各智能体的动作嵌入与全局表征结合，计算全局 Q 值 \( Q_{\text{tot}} \)，并通过最小化混合损失（含 TD 损失、相似性差异损失等）协调局部与全局目标。
5. **奖励设计**：包含动作似然奖励、任务特定奖励、协作贡献奖励三部分，动态调整权重。
6. **BNE 存在性证明**：基于 Glicksberg 不动点定理，在策略空间紧致凸、收益连续拟凹条件下证明 BNE 存在。
7. **收敛性分析**：得到亚线性遗憾界 \( O(N\sqrt{T} / (1-\gamma)) \)，远优于现有 MAD 的线性遗憾 \( \Omega(NT/(1-\gamma)) \)。

#### 算法流程（文字说明）
- **推理阶段**：Coordinator LLM 生成策略和格式 → 下发至 Execution LLM → 每个 Execution LLM 通过信念网络生成动作（提示嵌入）并输出答案 → Coordinator 聚合答案得到最终输出。
- **优化阶段**：利用 TD 损失更新信念网络参数；信念编码器通过全局 TD 损失优化；混合网络通过全局 TD 损失、相似性损失和局部-全局 Q 值一致性损失更新。Early stopping 基于输出稳定性、奖励收敛和损失收敛。

---

### 实验设计：数据集 / 场景、Benchmark、对比方法

#### 数据集与场景
- **数学推理**：GSM8K、GSM-Hard、MATH、SVAMP
- **常识推理**：StrategyQA
- **复杂规划**：TravelPlanner（使用 GPT-4-Turbo 评估）

#### 基准方法
- 单轮 CoT（Zero-shot / Few-shot）
- 多轮 CoT（Self-Consistency with 64 次采样）
- 值引导搜索（TS-LLM、PPO-MCTS）
- 多轮自我改进（ToT、RAP、ReAct）
- 多 LLM 框架（rStar、Multi-Agent Debate 3 轮）

#### 模型使用
- LLaMA3.1 8B/70B/405B、Mistral-7B、Mixtral-8x22B、Qwen1.5 110B、GPT-4-Turbo

---

### 资源与算力
- **论文未明确说明使用的 GPU 型号、数量及训练时长**。仅在超参数表中提及学习率、批量大小等，但无具体硬件信息。
- 推测需要 GPU 集群（如多卡 A100/H100）以运行 70B/405B 模型及多次推理，但作者未公开细节。

---

### 实验数量与充分性

- **主要实验**：在 5 个推理数据集上对比了 9 种基线方法（每种方法在 4 个主流模型上验证），平均结果展示于图 3，详细单数据集结果见附录 E。
- **旅行规划**：在 TravelPlanner 验证集（180 例）和测试集（1000 例）上对比 MAD 等。
- **模型配置分析**：同构 vs 异构、强协调器+弱执行器等（表 2）。
- **Token 效率对比**：表 3 列出 MATH、GSM8K、GSM-Hard 上各方法的 token 使用量。
- **可扩展性实验**：从 3 个 Execution LLM 逐步增至 9 个，并实验多协调器层级（图 4、5）。
- **消融实验**：奖励组件、协调器策略类型、信念编码器/拼接模块的移除（表 5、6）。
- **BNE 有效性验证**：对比达到 BNE 前后的性能差异（表 5 提及平均提升 14%）。
- **总计**：约 10 组以上不同维度的实验，覆盖常见推理、规划、消融、扩展性，实验充分且公平（统一 zero-shot 设置，控制变量）。

---

### 论文的主要结论与发现

1. **性能提升**：ECON 平均超出单智能体方法 10.9%，超出多智能体方法 11.2%。
2. **Token 高效**：相比 3 轮 MAD，平均节省 21.4% token 消耗；相比自一致性大幅降低。
3. **可扩展性**：将 Execution LLM 从 3 个增至 9 个（配合多协调器层级），性能提升 18.1%，且资源增长适中。
4. **理论优势**：证明了 BNE 存在性，给出亚线性遗憾界，而 MAD 为线性遗憾。
5. **鲁棒性**：异构模型组合仍优于基线，但弱于同构组合；在强模型（如 GPT-4）上进一步提升。

---

### 优点

- **理论扎实**：从博弈论出发，严格证明了 BNE 存在性与亚线性收敛，为多智能体协调提供了理论保障。
- **高效通信**：用信念替代显式消息传递，显著降低 token 开销，缓解上下文窗口限制。
- **分层协调设计**：分布式推理 + 集中式输出，兼顾局部智能体灵活性和全局最优性。
- **丰富的消融和扩展实验**：验证了各模块必要性、奖励设计、异构性、可扩展性等，结论可靠。
- **代码开源**：促进可复现性。

---

### 不足与局限

1. **算力公开不足**：未报告训练/推理的具体 GPU 型号、数量、时间，不利于实际复现成本评估。
2. **异构实验表现欠佳**：异构 Execution LLM 组合比同构略差，表明该方法对模型一致性有一定依赖，未充分解决异构协调难题。
3. **奖励函数设计依赖人工归一化**：尽管动态调整权重，但仍需要预设上限 \( R_{\text{max}} \)，在开放任务中可能不够通用。
4. **扩展性上限**：增加 Execution LLM 超过 4 个时性能提升变缓甚至下降（如图 4），虽然后续通过多协调器缓解，但说明单纯增加数量并非线性收益。
5. **仅评估推理任务**：未涉及开放域对话、代码生成等更广泛场景，泛化性有待验证。
6. **小模型性能提升有限**：在较弱模型（如 8B）上提升幅度相对较小（见图 4 中 LLaMA3.1-8B 曲线）。

（完）
