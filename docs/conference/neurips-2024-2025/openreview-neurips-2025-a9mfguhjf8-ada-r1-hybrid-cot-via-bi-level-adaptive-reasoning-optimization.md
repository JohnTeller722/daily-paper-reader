---
title: "Ada-R1: Hybrid-CoT via Bi-Level Adaptive Reasoning Optimization"
title_zh: Ada-R1：通过双层次自适应推理优化实现混合思维链
authors: "Haotian Luo, Haiying He, Yibo Wang, Jinluan Yang, Rui Liu, Naiqiang Tan, Xiaochun Cao, Dacheng Tao, Li Shen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=a9MfGUHjF8"
tags: ["query:mas-routing"]
score: 8.0
evidence: 自适应推理深度选择以平衡效率与准确率
tldr: Ada-R1提出双层次自适应推理优化框架，根据问题复杂度动态选择短或长思维链，避免不必要的长推理开销。实验显示该方法在保持准确率的同时显著降低推理成本，直接服务于多跳推理中的资源配置优化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1302, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1422, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1426, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 651, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a9mfguhjf8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 644, \"height\": 545, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1160, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1281, \"height\": 1442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1036, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 787, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1275, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 580, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-a9mfguhjf8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1070, \"height\": 382, \"label\": \"Table\"}]"
motivation: 长推理链虽然提升性能但带来高昂开销，且并非所有问题都需要长推理。
method: 提出两阶段框架：先构建混合推理模型，再通过双层次优化自适应选择推理深度。
result: 在多个基准上取得与长推理链相当的准确率，但推理时间大幅减少。
conclusion: 自适应推理深度选择有效平衡了多跳推理的准确率与效率，具有实用价值。
---

## Abstract
Recently, long-thought reasoning models achieve strong performance on complex reasoning tasks, but often incur substantial inference overhead, making efficiency a critical concern. Our empirical analysis reveals that the benefit of using Long-CoT varies across problems: while some problems require elaborate reasoning, others show no improvement—or even degraded accuracy. This motivates adaptive reasoning strategies that tailor reasoning depth to the input. However, prior work primarily reduces redundancy within long reasoning paths, limiting exploration of more efficient strategies beyond the Long-CoT paradigm. To address this, we propose a novel two-stage framework for adaptive and efficient reasoning. First, we construct a hybrid reasoning model by merging long and short CoT models to enable diverse reasoning styles. Second, we apply bi-level preference training to guide the model to select suitable reasoning styles (group-level), and prefer concise and correct reasoning within each style group (instance-level). Experiments demonstrate that our method significantly reduces inference costs compared to other baseline approaches, while maintaining performance. Notably, on five mathematical datasets, the average length of reasoning is reduced by more than 50\%, highlighting the potential of adaptive strategies to optimize reasoning efficiency in large language models.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：长思维链（Long-CoT）模型（如 OpenAI o1、DeepSeek-R1）在复杂推理任务中表现出色，但推理开销巨大（高延迟、高算力消耗）。更关键的是，并非所有问题都需要长思维链——简单问题使用长思维链不仅浪费资源，有时甚至降低准确率。
- **动机**：现有效率优化方法（如 O1-Pruner、DPO）主要在 Long-CoT 分布内压缩冗余，但未考虑从根本上选择更短的推理路径；而能同时支持长短输出的方法（如 CoT-Valve）缺乏基于问题复杂度的自适应选择能力。
- **目标**：实现一种自适应推理策略，使模型能够根据输入问题自动选择适合的推理风格（长或短），从而在保持准确率的同时显著降低推理成本。

### 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：两阶段框架。第一阶段构建能同时生成长短思维链的混合模型；第二阶段通过双层次偏好训练（Bi-Level Preference Training）引导模型自适应选择推理风格并压缩推理长度。
- **关键技术细节**：
  1. **Stage I: 长短推理模型融合（Long-and-Short Reasoning Merge）**  
     将 Long-CoT 模型（参数 θ<sub>L</sub>）和 Short-CoT 模型（参数 θ<sub>S</sub>）线性加权合并：  
     θ<sub>H</sub> = α·θ<sub>L</sub> + (1-α)·θ<sub>S</sub>，α∈[0,1]。  
     得到一个能生成两种推理路径的混合模型 π<sub>θ<sub>H</sub></sub>。
  2. **Stage II: 双层次偏好训练**  
     - **组级别偏好（Group-Level Preference）**：对每个问题采样 K 个长/短答案，计算每组正确率期望。若长组准确率显著高于短组（超过阈值 ε），则偏好长组；否则偏好短组。构造偏好对 (x, y<sub>w</sub>, y<sub>l</sub>)。
     - **实例级别偏好（Instance-Level Preference）**：在确定了偏好组后，在该组的所有正确答案中，选择最短的作为偏好样本，选择最长的作为拒绝样本，进一步鼓励简洁正确推理。
     - **优化目标**：使用 DPO（Direct Preference Optimization）在收集的偏好数据集 D<sub>group</sub> ∪ D<sub>instance</sub> 上优化混合模型。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - 训练集：MixMathematics（AIME : MATH : GSM8K = 1:3:1，共 2500 题）。
  - 分布内评估：AIME25、MATH500、GSM8K 测试集。
  - 分布外评估：OlympiadBench、Minerva（数学推理）；LogiQA、GPQA、MMLU（非数学推理）。
- **基准模型**：DeepSeek-R1-Distill-Qwen-7B 和 1.5B（Long-CoT 模型）；Short-CoT 模型通过长模型在少量短 CoT 数据上微调得到。
- **对比方法**：Long（原始长推理）、Short（短推理）、Merge（仅融合）、DPO（朴素偏好优化）、O1-Pruner、CoT-Valve、Ada-R1（本文方法）。

### 4. 资源与算力

- 论文附录 B 说明：训练使用 8×A800-80G GPU，batch_size=32，学习率 5e-7，训练 2 个 epoch。β 取 0.05（1.5B）或 0.1（7B）。未明确说明训练总时长，但设备配置和超参数已给出。

### 5. 实验数量与充分性

- **实验组数**：
  - 主实验（Table 2）：在 5 个数学数据集上对比 6 种方法，含 7B 和 1.5B 两个规模。
  - 消融实验（Table 3）：分析 Merge、SFT、instance-level、group-level、bi-level 各组件贡献。
  - 进一步评估：
    - Thinking Ratio 分析（Figure 3）
    - 分难度自适应推理分析（Figure 4）
    - 合并模型损失验证（Table 4）
    - 非数学领域 OOD 测试（Table 5：LogiQA、GPQA、MMLU）
  - 附案例研究（Appendix E）和 t-SNE 可视化（Appendix D）。
- **充分性与公平性**：
  - 对比方法覆盖了分布内（Limited）和分布外（Broad）优化方法，包含强基线（O1-Pruner、CoT-Valve）。
  - 评估指标同时使用准确率和推理长度（token 数），兼顾效率与质量。
  - 消融实验充分，验证了每个设计选择的重要性。
  - 多轮次重复实验（AIME25 报告 4 次平均），降低随机性。
  - 总体实验设计合理、客观，结论有充分数据支撑。

### 6. 主要结论与发现

- Ada-R1 在保持准确率的同时，实现了大幅推理长度缩减：
  - 7B 模型：平均长度减少 50.93%，准确率仅下降 1.65%（如 MATH 上长度减少 58% 且准确率不变，GSM8K 上长度减少 74% 且准确率提升）。
  - 1.5B 模型：平均长度减少 43.28%，准确率下降 1.21%。
- 与 O1-Pruner 等有限范围优化方法相比，Ada-R1 长度缩减更显著；与 CoT-Valve 等广范围优化方法相比，准确率损失极小。
- 自适应分析表明：模型在简单问题上更多使用短推理，在困难问题上倾向长推理，实现了按需分配计算资源。
- 非数学领域（LogiQA、GPQA、MMLU）也验证了其泛化能力，准确率提升 23.63%，长度减少 25.37%。

### 7. 优点

- **创新性**：首次明确将“自适应推理深度选择”作为效率优化的核心思路，而非仅压缩长推理冗余。
- **方法设计简洁有效**：模型融合+双层次 DPO 训练，无需复杂架构改动，易于复现和扩展。
- **实验全面**：涵盖多难度数学任务、非数学推理任务、消融分析、内部机制可视化（t-SNE）和案例分析。
- **实用价值显著**：在推理成本敏感的场景（如实时系统、资源受限设备）中有直接应用潜力。
- **代码和模型权重将开源**，促进社区进一步研究。

### 8. 不足与局限

- **实验覆盖局限**：主要聚焦数学推理（5个数学数据集 + 少量非数学基准），对更广泛的常识推理、多模态推理等任务未验证。
- **现实场景适用性**：论文自身指出（Appendix F），现实任务的问题复杂度模式可能不如数学题目清晰，模型依赖“问题复杂性可预测”的假设，实际中可能失效。
- **训练数据规模较小**：仅 2500 个训练样本，可能不足以充分学习复杂真实分布。
- **融合系数 α 的选择**：基于 100 个 AIME 问题的验证，样本量小，可能不能推广到其他分布。
- **未报告误差线/置信区间**：虽然对 AIME25 做了 4 次平均，但主实验 table 未提供标准差，统计显著性不明。
- **未讨论失败案例或潜在偏差**：当模型错误选择推理风格时，补偿机制或性能影响未深入分析。

（完）
