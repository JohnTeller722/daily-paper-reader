---
title: Reinforce LLM Reasoning through Multi-Agent Reflection
title_zh: 通过多智能体反射增强LLM推理
authors: "Yurun Yuan, Tengyang Xie"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6k3oFS3Lbl"
tags: ["query:mas-routing"]
score: 4.0
evidence: 多智能体反射涉及智能体间的解决方案路由
tldr: 本文针对LLM推理中验证-改进范式的反馈空间受限问题，提出DPSDP算法，将多轮改进建模为马尔可夫决策过程，训练演员-评论家系统。多智能体反射机制隐式涉及智能体间路由和协调，实验证明该方法在数学推理任务上显著提升准确性，为多智能体协同路由提供了新视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1478, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 66, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6k3ofs3lbl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 117, \"height\": 66, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1617, \"height\": 1572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1305, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1610, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6k3ofs3lbl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 739, \"height\": 404, \"label\": \"Table\"}]"
motivation: 现有验证-改进方法反馈空间小且缺乏协调训练，效果受限。
method: 提出DPSDP算法，将多智能体反射过程建模为MDP并优化。
result: 在数学推理任务上，DPSDP显著优于现有自我改进方法。
conclusion: 多智能体反射与强化学习结合能有效提升推理路由效率。
---

## Abstract
Leveraging more test-time computation has proven to be an effective way to boost the reasoning capabilities of large language models (LLMs). Among various methods, the verify-and-improve paradigm stands out for enabling dynamic solution exploration and feedback incorporation. However, existing approaches often suffer from restricted feedback spaces and lack of coordinated training of different parties, leading to suboptimal performance. To address this, we model this multi-turn refinement process as a Markov Decision Process and introduce DPSDP (**D**irect **P**olicy **S**earch by **D**ynamic **P**rogramming), a reinforcement learning algorithm that trains an actor-critic LLM system to iteratively refine answers via direct preference learning on self-generated data. Theoretically, DPSDP can match the performance of any policy within the training distribution. Empirically, we instantiate DPSDP with various base models and show improvements on both in- and out-of-distribution benchmarks. For example, on benchmark MATH 500, majority voting over five refinement steps increases first-turn accuracy from 58.2% to 63.2% with Ministral-based models. An ablation study further confirms the benefits of multi-agent collaboration and out-of-distribution generalization.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：当前LLM在推理任务中广泛采用“验证-改进”范式，即通过多轮交互（生成答案、接收反馈、修正答案）来提升性能。然而，现有方法存在两个主要限制：反馈空间狭窄（仅依赖编译器、固定工具等），以及缺乏对参与方（生成器与反馈提供者）的联合训练，导致协作次优。
- **整体含义**：本文旨在通过强化学习（RL）训练一个多智能体系统（演员-评论家），使得两个LLM能够协同迭代地改进答案，从而在多种推理基准上取得显著提升，并具备良好的分布外泛化能力。

## 2. 方法论

- **核心思想**：将多轮细化过程建模为马尔可夫决策过程（MDP），每个状态仅包含最新的答案和对应的反馈（而非完整历史），从而降低上下文长度需求并支持任意长度的测试时迭代。在此基础上提出**DPSDP**算法，采用动态规划思想进行策略搜索，通过直接偏好优化（DPO）从自生成数据中训练演员和评论家。

- **关键技术细节**：
  - **MDP建模**：状态\(s_h\)仅包含问题\(x\)和最新的响应；动作\(a_h\)由演员（生成答案）或评论家（生成反馈）产生；奖励为答案是否与真实答案匹配。
  - **参考策略\(\pi_{\text{ref}}\)**：使用未专门优化的LLM作为数据收集基础，通过KL正则化目标约束优化。
  - **Q值估计**：实际中无法精确计算Q值，用直接正确性或滚动参考策略近似：对反馈步骤的Q值通过参考策略生成的改进答案的正确性估计；对初始答案的Q值直接用其正确性估计。
  - **损失函数简化**：将原交叉熵损失转化为DPO损失，从而只需构造偏好对（正确 vs 错误）即可训练。
  - **初步训练（SFT）**：先用有能力的模型（如Mistral-Large、Llama-3.3-70B）生成高质量反馈和改进实例，对演员和评论家进行监督微调，获得基础能力后再进行DPSDP训练。

- **算法流程**（文字描述）：
  1. 对每个训练问题，从参考策略采样一条完整轨迹（初始答案→反馈→改进答案）。
  2. 在每个状态，采样多个候选响应（n=8），估计其Q值，选出“选中的”（Q>0）与“拒绝的”（Q=0）构成偏好对。
  3. 分别对演员（使用初始答案和改进答案状态）和评论家（使用反馈状态）应用DPO损失。
  4. 最终策略为训练后的演员和评论家。

## 3. 实验设计

- **数据集**：
  - **训练集**：OpenMathInstruct-2（来源于MATH和GSM8K的增强版）。
  - **评估基准**（分布内）：MATH 500、GSM8K。
  - **分布外基准**：MMLU-Pro Math、Olympiad Bench（包含奥数级问题）。
- **对比方法**：
  - STaR（自我对弈微调，仅使用正确轨迹）
  - STaR-DPO（使用正确+错误轨迹进行DPO）
  - Oracle-RISE（使用真实答案作为反馈，有监督优势）
  - 多种消融变体：单智能体（演员和评论家同一模型）、非马尔可夫（状态包含全部历史）、无重启数据收集等。
- **模型**：Ministral-8B-Instruct、Llama-3.1-8B-Instruct、Qwen2.5-3B。
- **评估指标**：p1@t1（初始答案准确率）、m1@t5（5次迭代后多数投票准确率）、p1@t5（5次中至少一次正确）。

## 4. 资源与算力

- 论文明确提及了训练硬件：4×H100 80GB GPU。
- 训练细节：SFT阶段使用梯度累积步数64，批大小1，学习率1e-6或5e-6，训练1个epoch；DPO阶段类似，学习率2e-7或4e-7，KL系数β在0.1~1.0之间。非生成性批评家训练1个epoch，学习率1e-6。
- **未明确说明**：总训练时长、具体耗电量或GPU小时数。

## 5. 实验数量与充分性

- 实验数量充分：
  - **主表（Table 1）**：在4个基准上、3种基模型、多种方法（DPSDP、SFT、非生成批评家、单智能体、非马尔可夫、STaR、STaR-DPO、Oracle-RISE）共约30+行结果。
  - **消融实验**：
    - 单智能体 vs 多智能体
    - 马尔可夫 vs 非马尔可夫
    - 重启 vs 无重启数据收集
    - 有无初步SFT
    - 统一训练 vs 逐步训练（Q值估计验证）
    - 生成性批评家 vs 非生成性批评家
  - **额外分析**：多轮性能曲线、正确性转移比例、过思考现象定性示例。
- **公平性**：所有方法都基于相同的SFT起点，且超参数经调优。基线方法（STaR、STaR-DPO）也使用了相同的训练数据。Oracle-RISE虽使用真实答案反馈但被单独对比。整体实验设计客观、公平。

## 6. 主要结论与发现

- DPSDP显著提升了多轮推理性能：在MATH 500上，Ministral模型m1@t5从SFT的57.2%提升到63.2%（绝对+6%），且优于所有基线。
- 多智能体（演员+评论家）优于单智能体，尤其是在更具挑战性的基准上（MATH 500、Olympiad Bench）。
- 马尔可夫设定（仅用最新答案）优于非马尔可夫设定（使用完整历史），表明合理的状态压缩可避免分布偏移。
- 重启式数据收集增强了探索，带来额外增益。
- 初步SFT对成功至关重要；无SFT直接应用DPSDP几乎无效。
- DPSDP能泛化到分布外基准（Olympiad Bench等），表明模型学会了迭代改进技能而非记忆。
- 非生成性批评家（仅输出二值反馈）在简单任务上表现良好，但在困难任务上逊于生成性批评家。

## 7. 优点

- **理论保证**：给出了性能界（Theorem 1），证明DPSDP可与任意策略竞争，假设合理。
- **实用高效**：通过状态压缩（仅保留最近答案）和DPO损失简化，实现单步训练即可泛化到多轮推理，降低了训练计算成本。
- **探索充分**：重启式采样增强动作空间探索，结合负例学习（DPO）防止退化。
- **泛化能力强**：在分布外基准上依然有效，展示出良好的迁移性。
- **全面的消融**：系统分析了多智能体、马尔可夫假设、Q值估计、SFT必要性等设计选择，提供了深入理解。

## 8. 不足与局限

- **依赖初步SFT**：无SFT阶段时效果极差，增加了模型准备成本。
- **非马尔可夫设定下性能下降**：虽然作者解释了原因（分布偏移），但在某些需要完整历史的任务中可能不适用。
- **生成性批评家可能“过度思考”**：在简单问题上，批评家过度分析导致后续答案出错（如例中GSM8K问题从正确变为错误）。
- **Q值估计近似简单化**：对于反馈步骤，使用参考策略滚动估计Q值，可能引入偏差，尽管实验表明影响有限。
- **计算资源消耗**：需要4×H100 GPU进行训练，对于资源有限团队可能存在门槛。
- **应用限制**：当前仅针对数学推理任务，未验证在其他领域（如代码、对话）的通用性。

（完）
