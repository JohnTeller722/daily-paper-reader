---
title: On the Resilience of LLM-Based Multi-Agent Collaboration with Faulty Agents
title_zh: 基于LLM的多智能体协作在故障智能体下的韧性研究
authors: "Jen-tse Huang, Jiaxu Zhou, Tailin Jin, Xuhui Zhou, Zixi Chen, Wenxuan Wang, Youliang Yuan, Michael Lyu, Maarten Sap"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bkiM54QftZ"
tags: ["query:mas-routing"]
score: 8.0
evidence: "研究不同多智能体系统结构（如A->B->C）作为路由机制在有故障智能体下的韧性"
tldr: "当前基于LLM的多智能体系统缺乏对故障智能体影响的系统性研究。本文系统评估了不同系统结构（如链式A->B->C、双向A<->B<->C等）在故障智能体下的韧性表现，并提出了AutoTransform和AutoInject两种模拟故障的方法。实验揭示了结构选择对整体性能的关键影响，并展示了通过简单调整可提升系统韧性。该工作为设计鲁棒的多智能体路由拓扑提供了重要指导。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 806, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1511, \"height\": 1289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1721, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1716, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkim54qftz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 951, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1099, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1307, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1507, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1355, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1690, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1277, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1175, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1750, \"height\": 1697, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1748, \"height\": 1656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1758, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1752, \"height\": 1073, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1754, \"height\": 1727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1742, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1745, \"height\": 1024, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1731, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkim54qftz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1742, \"height\": 558, \"label\": \"Table\"}]"
motivation: 多智能体系统中故障智能体的影响尚不明确，缺乏对不同系统结构韧性的系统性理解。
method: 提出AutoTransform和AutoInject两种方法在智能体响应中注入可控错误以模拟故障；在多种任务下评估不同系统结构的韧性。
result: 不同系统结构对故障的韧性差异显著，链式结构在串联故障下脆弱，双向结构容忍度更高。
conclusion: 系统结构（路由拓扑）是影响多智能体系统可靠性的关键设计因素，可通过结构优化提升韧性。
---

## Abstract
Large language model-based multi-agent systems have shown great abilities across various tasks due to the collaboration of expert agents, each focusing on a specific domain. However, the impact of clumsy or even malicious agents—those who frequently make errors in their tasks—on the overall performance of the system remains underexplored. This paper investigates: (1) What is the resilience of various system structures (e.g., A$\rightarrow$B$\rightarrow$C, A$\leftrightarrow$B$\leftrightarrow$C) under faulty agents, on different downstream tasks? (2) How can we increase system resilience to defend against these agents? To simulate faulty agents, we propose two approaches—AutoTransform and AutoInject—which introduce mistakes into the agents' responses. Experiments on four downstream tasks using six systems show that the "hierarchical" structure, i.e., A$\rightarrow$(B$\leftrightarrow$C), exhibits superior resilience with the lowest performance drop of 5.5%, compared to 10.5% and 23.7% of other two structures. To further improve resilience, we introduce (1) Challenger, that introduces a mechanism for each agent to challenge others' outputs, and (2) Inspector, an additional agent to review and correct messages, recovering up to 96.4% errors made by faulty agents. Our code and data are available at https://github.com/CUHK-ARISE/MAS-Resilience.

---

## 论文详细总结（自动生成）

# 基于LLM的多智能体协作在故障智能体下的鲁棒性研究——中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：LLM-based多智能体系统（如MetaGPT、Camel）通过分工协作已展现出强大能力，但现有工作主要关注单智能体安全或攻击诱导毒性输出，未系统研究**故障智能体（clumsy/malicious agents）**对系统整体性能的影响，尤其是不同系统结构（链式、扁平、层次）在面对故障时的鲁棒性差异。
- **核心问题**：
  1. 不同系统结构在故障智能体下的鲁棒性如何？不同下游任务（代码生成、数学、翻译、文本评估）的受影响程度如何？
  2. 如何提升系统鲁棒性以防御故障智能体？
- **整体含义**：该工作首次从管理科学视角（线性、扁平、层次三种组织结构）系统评估多智能体系统的鲁棒性，揭示了结构对错误传播的关键影响，并为设计更可靠的多智能体路由拓扑提供了指导。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 故障模拟方法
- **AutoTransform（自动转换）**：
  - 核心思想：将正常智能体的角色描述（profile）改写为“故障”版本，使其在保持原有功能的同时，刻意引入隐蔽错误。
  - 流程：①分析原始profile，提取任务目标；②列出可能引入错误的方式（强调隐蔽性）；③用LLM重写profile，注入错误指令。
- **AutoInject（自动注入）**：
  - 核心思想：直接截获智能体间的消息，按概率和错误率注入特定错误，提供精确控制。
  - 关键因素：
    - **错误率**：宏观（消息错误比例 \(P_m\)）和微观（单条消息中错误内容比例 \(P_e\)）。
    - **错误类型**：语法错误（违反逻辑/事实） vs. 语义错误（逻辑正确但意图不符）。
  - 流程：根据任务类型（代码、数学、翻译、评估），用LLM按指定错误类型和比例替换消息中的行/句子。

### 2.2 鲁棒性提升方法
- **Challenger（挑战者）**：在每个智能体profile中添加挑战他人输出的能力，使其能质疑收到的消息。
- **Inspector（检查员）**：新增一个独立智能体，审查所有消息并修正错误，类似“警察”角色。

## 3. 实验设计

### 3.1 下游任务与基准
- **代码生成**：HumanEval（164个问题），评估指标Pass@1。
- **数学问题求解**：CIAR（50个反直觉算术问题），评估准确率。
- **翻译**：CommonMT（100个句子，词汇类子集），用BLEURT-20评估。
- **文本评估**：FairEval（80个“赢/平/输”标注），评估一致准确率。

### 3.2 多智能体系统结构（三种类型，各两个系统）
- **线性结构**：MetaGPT（5个智能体）、Self-collab（3个智能体）。
- **扁平结构**：Camel（2个智能体）、SPP（2~5个智能体）。
- **层次结构**：MAD（多智能体辩论，3个智能体）、AgentVerse（动态招募，4个智能体）。

### 3.3 对比方法
- **正常无故障系统**（Vanilla）
- **单智能体基线**（每个任务单个LLM）
- **两种故障注入方法**：AutoTransform、AutoInject
- **两种防御方法**：Challenger、Inspector及二者组合

### 3.4 骨干模型
- 主实验：GPT-3.5和GPT-4o（温度=0）；消融实验使用GPT-3.5。
- 额外验证：LLaMA-3.1-70B、o1-Mini。

## 4. 资源与算力

- 论文未明确说明具体使用的GPU型号、数量及训练时长。所有实验均基于OpenAI API调用（GPT-3.5/4o），未涉及模型训练，仅推理。推测使用一般商用API资源，算力需求适中。

## 5. 实验数量与充分性

- **实验数量**：涵盖4个任务、6个多智能体系统，共24种基础组合；在两种故障方法、两种错误率、两种错误类型、两种防御机制下做了大量消融（见附录A/B/C表格）。具体包括：
  - 不同错误率（Pm和Pe变化）
  - 不同错误类型（语义vs语法）
  - 多个故障智能体场景（附录B.3）
  - 高级图拓扑（星形vs完全图，附录B.4）
  - 更复杂任务（Snake游戏，附录B.5）
  - 不同骨干模型（GPT-3.5/4o、LLaMA、o1-Mini）
- **充分性评价**：
  - **充分**：实验覆盖了结构、任务、错误控制、防御等多个维度，消融分析细致。
  - **客观公平**：所有系统使用默认作者设置，温度固定为0，评估指标为常见自动指标（Pass@1、准确率、BLEURT），但未进行人工评估；各结构因框架差异无法完全控制prompt变量，但通过每类结构选两个系统在一定程度上平均了偏差。

## 6. 论文的主要结论与发现

1. **结构鲁棒性**：层次结构（如MAD、AgentVerse）性能下降最小（平均5.5%），远优于扁平（10.5%）和线性（23.7%），与人类组织层级结构优势一致。
2. **任务敏感性**：客观任务（代码生成-22.6%、数学-9.9%）比主观任务（文本评估-5.4%、翻译-4.7%）对错误更敏感。
3. **错误注入的意外收益**：在某些系统（如MAD、Camel）和任务中，故意注入错误反而提升性能（最高12.1%），原因包括“双重检查”和“发散思维”打破僵局。
4. **错误率影响**：增加错误消息比例（Pm）比增加单条消息错误密度（Pe）对性能影响更大；当错误过多时系统可能察觉并纠正。
5. **错误类型**：语义错误比语法错误更具破坏性，因为LLM更容易发现语法不符。
6. **防御有效性**：Challenger和Inspector组合可恢复Self-collab系统96.4%的性能损失，显著提升线性和扁平系统的鲁棒性。
7. **错误注入方式差异**：AutoTransform在更强模型（GPT-4o）上造成更大性能下降，而AutoInject在较弱模型（GPT-3.5）上影响更大，反映指令遵循能力随模型增强而提升。

## 7. 优点

- **首创性**：首次系统研究多智能体系统结构对故障鲁棒性的影响，填补了安全与协作交叉领域的空白。
- **方法通用**：AutoTransform和AutoInject可应用于任何智能体profile和任务，无需手动编写错误案例。
- **实验全面**：覆盖4种代表性任务、6个主要框架、2种骨干模型、多种错误率和类型，并提供消融和扩展验证（图拓扑、复杂任务、多故障智能体）。
- **实用指导**：提出Challenger和Inspector两种轻量级防御策略，可集成到现有系统中，最高恢复96.4%性能损失。
- **可复现**：公开代码与数据，详细提示模板在附录中。

## 8. 不足与局限

- **骨架模型单一**：所有智能体共用同一LLM（GPT-3.5或GPT-4o），未测试异构模型场景；温度固定为0，未探索随机性影响。
- **任务与场景有限**：仅使用文本基准（代码、数学、翻译、评估），未涉及多模态、开放域对话或长程规划任务。
- **结构-提示混淆**：不同结构框架自带不同角色设计（如层次结构有领导者，扁平无），实验无法完全分离结构效果与prompt工程的影响。作者通过每类选两个系统部分缓解，但残留偏差仍然存在。
- **自动化评估局限性**：依赖自动指标（Pass@1、BLEURT），未进行人类评估，可能忽略语义合理但自动评分低的情况。
- **错误注入真实性**：AutoTransform生成的故障智能体可能不总是产生错误（尤其在GPT-3.5上指令遵循不稳定），导致实验条件不完全可控；AutoInject虽可精确控制，但人为注入错误与现实故障行为有差距。
- **算力资源未说明**：缺乏具体的GPU使用信息，不利于复现和能耗估计。

（完）
