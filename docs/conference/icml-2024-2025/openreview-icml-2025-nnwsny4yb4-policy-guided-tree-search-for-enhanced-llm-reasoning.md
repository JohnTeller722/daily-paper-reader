---
title: Policy Guided Tree Search for Enhanced LLM Reasoning
title_zh: 策略引导树搜索增强LLM推理
authors: Yang Li
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NNWSNy4YB4"
tags: ["query:mas-routing"]
score: 4.0
evidence: 使用学习到的策略动态选择推理路径，类似于推理空间中的路由
tldr: 现有树搜索方法依赖预定义启发式或穷举，效率低下。本文提出策略引导树搜索（PGTS），通过强化学习训练策略，动态决定树搜索中扩展、分支、回溯或终止等操作，无需手动设计启发式。在数学推理、逻辑推理和规划任务上的实验表明，该方法在准确率和效率上均优于基线。这种动态路径选择机制可迁移至多智能体系统作为内部路由策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1500, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 820, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 1368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1319, \"height\": 1780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1302, \"height\": 1982, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nnwsny4yb4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1324, \"height\": 2212, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nnwsny4yb4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1750, \"height\": 804, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nnwsny4yb4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nnwsny4yb4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 698, \"height\": 345, \"label\": \"Table\"}]"
motivation: 现有树搜索依赖预定义启发式或穷举，效率低。
method: 提出策略引导树搜索（PGTS），用RL训练策略动态决定搜索步骤。
result: 在多个推理任务上比基线方法更高效且准确。
conclusion: 动态策略引导可避免手动设计启发式，是一种通用的推理路径路由方法。
---

## Abstract
Despite their remarkable capabilities, large language models often struggle with tasks requiring complex reasoning and planning. While existing approaches like Chain-of-Thought prompting and tree search techniques show promise, they are limited by their reliance on predefined heuristics and computationally expensive exploration strategies. We propose Policy-Guided Tree Search (PGTS), a framework that combines reinforcement learning with structured tree exploration to efficiently navigate reasoning paths. Our key innovation is a learned policy that dynamically decides between expanding, branching, backtracking, or terminating exploration, eliminating the need for manual heuristics or exhaustive search. Experiments across mathematical reasoning, logical deduction, and planning benchmarks demonstrate that PGTS achieves superior reasoning performance while significantly reducing computational costs compared to existing methods. These results establish PGTS as a scalable and effective solution for tackling complex reasoning tasks with LLMs.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）在需要复杂推理与规划的任务（如数学问题、逻辑推理、真实世界规划）中表现不佳。现有的链式推理（CoT）和树搜索方法虽有效，但存在两大局限：① 严重依赖预定义的启发式规则或人工设计的奖励函数，缺乏适应性；② 探索过程计算开销大，尤其是MCTS等需要大量采样和评估。
- **整体意义**：本文提出**策略引导树搜索（Policy-Guided Tree Search, PGTS）**，将强化学习（RL）与结构化树搜索相结合，训练一个学习策略来动态决策搜索方向（扩展、分支、回溯、终止），从而避免手动启发式、减少穷举，在提升推理准确率的同时显著降低计算成本。该方法可视为一种推理空间的**动态路径路由**机制，具有通用性。

### 2. 论文提出的方法论

- **核心思想**：将LLM的推理过程形式化为一个**树搜索MDP（TS-MDP）**，其中状态是已探索的部分推理树，动作包括四种操作：
  - **Expand（扩展）**：从当前节点生成下一个推理步骤。
  - **Branch（分支）**：探索当前节点的兄弟节点（替代路径）。
  - **Backtrack（回溯）**：回退到之前节点（可指定步数），允许从次优路径恢复。
  - **Terminate（终止）**：结束搜索，返回当前路径的答案。
- **关键技术细节**：
  - 状态由推理树表示，节点特征来自LLM最后隐藏层，边特征为即时奖励（如步骤的对数似然）。
  - 策略网络采用**GPS图Transformer**架构，结合局部消息传递（MPNN）和全局注意力，捕捉树的结构和全局上下文。
  - 使用**PPO（Proximal Policy Optimization）**训练策略，奖励函数包含任务特定奖励和动作成本（如分支、回溯有额外成本），鼓励高效探索。
  - 通过**约束掩码**确保动作有效性（如深度/广度限制），避免无效操作。
- **训练细节**：策略训练无需人工标注的推理链，仅需问题-答案对，使用最多1000个训练样本即可收敛。动作成本设为固定超参数（扩展0.1，分支0.2，回溯0.5，终止0.0）。

### 3. 实验设计

- **数据集与场景**：
  - **数学推理**：GSM8K、MATH500、AQUA。
  - **常识推理**：StrategyQA。
  - **逻辑推理**：PrOntoQA、GPQA。
  - **规划任务**：Blocksworld（4步和8步）。
- **基准方法**：Chain-of-Thought（CoT）及其结合自一致性（SC），以及Monte Carlo Tree Search（MCTS，包括最佳路径、加权聚合、Oracle变体）。
- **模型与设置**：使用LLaMA3.1-8B和LLaMA3.1-70B，推理温度0.6，top-p=0.9。定义每个推理步骤为一个句子。树广度限制为4，深度根据数据集设定（如GSM8K最大深度16）。PGTS策略使用2层GPS + 线性层，训练数据量≤1000条。

### 4. 资源与算力

- 论文中未明确说明训练PGTS策略所使用的具体GPU型号、数量及训练时长。仅提及使用LLaMA3.1系列模型（8B和70B）进行推理，策略网络结构轻量（2层GPS），训练样本不超过1000条，开销较小。但未提供详细的算力统计。
- **备注**：由于策略网络轻量且训练样本少，推测资源需求不高，但原文缺少具体数字。

### 5. 实验数量与充分性

- **实验数量**：共涵盖8个数据集（数学、常识、逻辑、规划），每个数据集均报告了多种方法（CoT、CoT-SC、MCTS不同变体、PGTS、PGTS-SC）的结果，以及8B和70B两个尺度。
- **消融实验**：
  - 训练样本量分析（训练曲线显示1000样本后收敛）。
  - 树广度（2/4/6）对性能和生成长度的影响（在AQUA上）。
  - 策略网络结构消融（GPS vs SAN vs SLM vs LLM Agent，以及去除边特征/全局注意力/局部消息传递的效果）。
- **充分性与公平性**：
  - 对比方法包括当前主流技术（CoT、MCTS），且MCTS使用了Oracle变体作为上界。
  - 控制变量：树广度一致（均为4），推理步骤定义相同。
  - 缺点：GPQA任务上PGTS表现弱于MCTS，作者归因于任务复杂性和训练数据限制，但未进行深入分析；也未与ToT、A*等最新方法对比。整体实验设计较为系统和全面，消融实验充分。

### 6. 论文的主要结论与发现

- **性能提升**：PGTS在大部分数据集上优于CoT，且与MCTS性能相当甚至更好（尤其是在加入SC后）。例如LLaMA3.1-8B上，MATH准确率从CoT的34.40%提升至PGTS-SC8的52.20%，Blocksworld（8步）从CoT的2.10%提升至PGTS-SC8的6.99%。
- **计算效率**：PGTS显著低于MCTS的token消耗：MATH上MCTS消耗CoT的16.25倍，而PGTS仅5.28倍；GSM8K上MCTS为13.33倍，PGTS仅1.29倍。
- **动态策略有效**：学习到的策略能自适应决定何时扩展、分支、回溯、终止，避免“过度思考”（overthinking），自动平衡探索与利用。
- **结构化建模优势**：图Transformer策略优于简单语言模型（SLM、LLM Agent），说明捕捉树局部和全局结构的重要性。

### 7. 优点

- **方法创新**：首次将强化学习与图Transformer结合，学习树搜索的显式策略，替代手工启发式，通用性强。
- **高效性**：训练仅需少量样本（1000条），推理时token成本远低于MCTS，实用价值高。
- **结构灵活**：通过回溯和终止机制自动调整搜索深度和广度，避免无效计算。
- **消融充分**：验证了策略网络各组件（边特征、全局注意力、局部MPNN）的必要性，并比较了不同实现方式。
- **多领域验证**：涵盖数学、常识、逻辑、规划4大类任务，展示了方法的广泛适用性。

### 8. 不足与局限

- **GPQA性能差**：在复杂的知识密集型逻辑任务（GPQA）上PGTS明显弱于MCTS，说明当前策略对高难度、领域多样的任务泛化能力有限。
- **未与更多树搜索变体对比**：例如Tree-of-Thoughts（ToT）、A* Search、Graph-of-Thoughts等，仅与MCTS和CoT对比，可能不够全面。
- **奖励设计简单**：使用对数似然作为中间奖励，作者也承认未来可引入更复杂的奖励（如自评估、任务特定指标），这可能限制策略学习质量。
- **计算资源未明确**：未报告训练和推理的GPU时间、显存等，不利于复现和成本评估。
- **公平性隐患**：PGTS训练使用了部分数据集的ground truth（用于计算ORM），而MCTS Oracle也使用了ground truth，但MCTS无Oracle版本可能不公平。作者在对比中区分了Oracle变体，但未完全揭示信息泄露风险。
- **未知泛化性**：实验仅在LLaMA3.1模型上进行，未验证其他架构（如GPT-4、Mistral）或更大模型上的表现。

（完）
