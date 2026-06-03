---
title: "GraphChain: Large Language Models for Large-scale Graph Analysis via Tool Chaining"
title_zh: GraphChain：通过工具链实现大规模图分析的大语言模型
authors: "Chunyu Wei, Wenji Hu, Xingjia Hao, Xin Wang, Yifan Yang, Yunhai Wang, Yang Tian, Yueguo Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Rdz6ESQYkK"
tags: ["query:mas-routing"]
score: 5.0
evidence: 在大型图分析中使用强化学习生成工具序列，类似于多跳推理的配置选择
tldr: GraphChain提出了一种框架，使LLM通过动态编排专用工具链来分析大规模图。其核心是渐进图蒸馏方法学习生成平衡任务相关性和中间状态压缩的工具序列。该框架结构感知测试时自适应技术进一步提升了泛化能力。这为多跳推理中的配置选择提供了可迁移的方法论。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 640, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 789, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1143, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 1223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rdz6esqykk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1391, \"height\": 1289, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1459, \"height\": 544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1013, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1346, \"height\": 1643, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1346, \"height\": 1593, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1347, \"height\": 1769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1349, \"height\": 1115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rdz6esqykk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1388, \"height\": 1442, \"label\": \"Table\"}]"
motivation: LLM在处理大规模图时面临上下文限制和不灵活推理的问题。
method: 提出GraphChain，包含渐进图蒸馏和结构感知测试时自适应，动态生成工具序列。
result: 在多个大规模图分析任务上，GraphChain显著优于直接使用LLM的基线方法。
conclusion: GraphChain为LLM分析大规模图提供了一种高效且可扩展的范式。
---

## Abstract
Large Language Models (LLMs) face significant limitations when applied to large-scale graphs, struggling with context constraints and inflexible reasoning. We introduce GraphChain, a novel framework enabling LLMs to analyze large graphs by orchestrating dynamic sequences of specialized tools, mimicking human exploratory processes. GraphChain incorporates two core technical contributions: (1) Progressive Graph Distillation, a reinforcement learning approach that learns to generate tool sequences balancing task relevance and intermediate state compression, thereby overcoming LLM context limitations. (2) Structure-aware Test-Time Adaptation (STTA), a mechanism using a lightweight, self-supervised adapter conditioned on graph spectral properties to efficiently adapt a frozen LLM policy to diverse graph structures via soft prompts without retraining. Experiments show GraphChain significantly outperforms prior methods, enabling scalable and adaptive LLM-driven graph analysis.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

大语言模型（LLM）在推理、理解等方面表现出色，但在处理图结构数据时面临两大根本挑战：

- **上下文耗尽**：大规模图（百万级节点/边）无法被压缩进 LLM 的上下文窗口，导致整个图无法直接输入。
- **推理幻觉**：现有工具学习方法（如 Graph-ToolFormer、GraphForge）依赖单步工具调用，将复杂图分析任务交给单一工具，导致不切实际的推理要求，容易出错。

作者受人类探索未知环境过程的启发——逐步拓宽视野、根据反馈动态聚焦——提出 **GraphChain**，通过**动态工具链**使 LLM 能像人类专家一样渐进式地分析大规模图。

## 2. 论文提出的方法论

### 核心思想
将图分析建模为**马尔可夫决策过程（MDP）**，使用强化学习（RL）训练 LLM 策略，使其能生成和编排一系列图处理工具，逐步压缩图信息并聚焦于任务相关部分，最终在 LLM 上下文窗口内生成答案。

### 关键技术细节

#### (1) 渐进图蒸馏（Progressive Graph Distillation）
- **图描述长度（GDL）**：定义内存状态的数据体积，包括结构信息和特征信息。
- **任务相关性（Rel）**：通过辅助 LLM 评分器评估当前状态对回答查询的价值。
- **奖励设计**：中间步骤奖励包括：
  - 工具执行成功
  - GDL 减少（蒸馏）
  - 相关性增加  
  最终步骤奖励基于任务完成质量。
- **信息瓶颈视角**：理论证明该奖励机制引导模型保留任务相关信息、丢弃无关信息。
- **策略优化**：使用 PPO + GAE 稳定训练。

#### (2) 结构感知测试时自适应（STTA）
- **图结构指纹**：计算归一化拉普拉斯矩阵的最小奇异值，得到紧凑的图拓扑表示。
- **软提示生成**：轻量适配器网络将指纹映射为软提示，拼接到 LLM 输入嵌入中。
- **自监督自适应**：用辅助查询在测试图上进行少量 rollout，优化两个目标：
  - 最小化链长度（效率）
  - KL 散度正则化（保持与原始策略的接近）
- 只更新适配器参数，实现高效迁移。

## 3. 实验设计

### 数据集与场景（5个真实域）
| 场景 | 数据集 | 图类型 | 规模（节点/边） |
|------|--------|--------|----------------|
| 金融网络 | Elliptic | 有向 | 203,769 / 234,355 |
| 化学分子 | QM9 | 无向 | ~18 节点/图 |
| 社交网络 | Facebook, Twitter | 无向/有向 | 4,039 ~ 81,306 |
| 引文图 | Cora, CiteSeer, PubMed | 有向 | 2,708 ~ 19,717 |
| 交通网络 | METR-LA | 有向 | 207 / 1,515 |

### 指令数据
- SFT数据集：9,986 个 (query, 工具序列, answer) 三元组
- RL数据集：3,000 个专家标注 (query, answer) 对（每个场景 500 训练 + 100 测试）

### 对比方法
- **文本指令方法**：Claude系列、GPT系列、GLM4、NLGraph、GraphWiz（使用 CoT）
- **工具指令方法**：Graph-ToolFormer、GraphForge、ToolGen（基于 LLaMA 8B 等）
- **公平性处理**：为使基线可处理，将所有图分割成子图（节点数<100）；GraphChain 在完整大图中也保持性能。

## 4. 资源与算力

文中明确说明：
- **硬件**：2 块 NVIDIA A800 (80GB)
- **微调方法**：LoRA（rank=16, alpha=32）基于 Qwen2.5-7B-instruction 模型
- **训练阶段**：分 SFT 和 RL 两阶段，但**未明确指出具体训练时长或总体计算量**。

## 5. 实验数量与充分性

实验非常充分且覆盖全面：
- **主实验**（表2）：在5个场景上与11种基线对比，每个结果附带标准差和统计检验（p<0.05）。
- **消融实验**（图3）：剥离渐进图蒸馏和 STTA 两个组件，验证各自贡献。
- **可扩展性实验**（图4）：改变图大小（50~200k节点）和查询复杂度（1~5步工具），验证性能稳定性。
- **迁移学习实验**（表3）：在金融网络训练后测试于社交/引文/交通网络，评估泛化能力。
- **工具链分析**（图5）：分析与不同域的工具使用分布，证明策略自适应。
- **鲁棒性实验**（表4/5/6）：
  - 减少工具库 50%
  - 更换不同基座模型（Llama3.1-8B, GLM4-9B）
  - 不同模型规模（3B, 7B, 14B）
- 所有实验均使用标准测试集，重复多次报告均值±标准差。

实验设计公平：对基线方法，通过子图使它们能处理；对比时使用了相同或相近的基座模型规模（7B vs 8B），确保比较公平。

## 6. 论文的主要结论与发现

- GraphChain 平均准确率 **84.7%**，比最佳基线 GraphForge（70.2%）提升 **20.7%**，且仅用 7B 参数。
- 渐进图蒸馏是核心优势：缺少该组件性能大幅下降，优于缺失 STTA。
- 可扩展性突出：在全图高达 20 万节点时仍保持 79.5% 准确率，而 GPT-4o 和 GraphForge 下降严重。
- 迁移能力强：仅用单一域训练后，在其他域上准确率接近域内结果；STTA 进一步缩小差距。
- 工具链模式自动适应不同图结构，展示出类人的探索策略。

## 7. 优点（方法或实验设计亮点）

- **创新性强**：将图分析形式化为动态工具链 MDP，结合 RL、信息瓶颈、测试时自适应，构成完整框架。
- **实用性高**：解决了 LLM 处理大规模图的实际痛点（上下文限制、单步工具幻觉）。
- **实验非常全面**：涵盖 5 个真实域、多种基线、消融、可扩展、迁移、鲁棒性分析，结论可信度高。
- **效率与可扩展性**：可处理 20 万节点图，无需完全重训练模型。
- **可迁移性**：STTA 是轻量级适配，适用于新域，降低应用成本。

## 8. 不足与局限

- **静态图限制**：当前实现主要针对静态图，对于动态或时序图（节点/边随时间演变）需要额外适配。
- **工具库依赖**：工具库基于 NetworkX，虽然较全面，但针对特定领域（如分子图、知识图谱）可能需要扩展更多专用操作。
- **计算开销**：RL 训练阶段（PPO + 蒸馏奖励）可能需要较多资源；文中未详细报告训练时长。
- **潜在偏差风险**：训练数据（SFT 和 RL）均由 ChatGPT 和专家生成，可能隐含特定的分析偏好，泛化到非典型的图分析任务时可能存在偏差。
- **自适应质量**：STTA 使用通用辅助查询，对于完全新域可能不够精确，需要进一步研究如何自动生成最相关的查询。

（完）
