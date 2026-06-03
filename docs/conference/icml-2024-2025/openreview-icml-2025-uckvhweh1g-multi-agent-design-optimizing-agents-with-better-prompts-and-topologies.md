---
title: "Multi-Agent Design: Optimizing Agents with Better Prompts and Topologies"
title_zh: 多智能体设计：通过更好的提示和拓扑优化智能体
authors: "Han Zhou, Xingchen Wan, Ruoxi Sun, Hamid Palangi, Shariq Iqbal, Ivan Vulić, Anna Korhonen, Sercan O Arik"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=uCKvHweh1g"
tags: ["query:mas-routing"]
score: 8.0
evidence: 优化智能体提示和拓扑以实现有效路由
tldr: 多智能体系统设计中提示和拓扑的选择极为复杂。本文通过分析设计空间，提出MASS框架，自动优化智能体的提示和交互拓扑，从而实现了高效的任务路由和协作。实验证明MASS在多个复杂任务上显著提升了性能，并降低了人工设计成本。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1672, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 838, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1786, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1673, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1130, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uckvhweh1g/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1870, \"height\": 2155, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 929, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 469, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1754, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uckvhweh1g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 477, \"label\": \"Table\"}]"
motivation: 手动设计多智能体系统的提示和拓扑费时费力，且难以达到最优。
method: 提出MASS框架，利用搜索算法联合优化提示和拓扑。
result: MASS在多个基准任务上取得了优于手工设计的性能。
conclusion: 自动化提示和拓扑优化是提升多智能体系统路由效果的有效途径。
---

## Abstract
Large language models, employed as multiple agents that interact and collaborate with each other, have excelled at solving complex tasks. The agents are programmed with prompts that declare their functionality, along with the topologies that orchestrate interactions across agents. Designing prompts and topologies for multi-agent systems (MAS) is inherently complex. To automate the entire design process, we first conduct an in-depth analysis of the design space aiming to understand the factors behind building effective MAS. We reveal that prompts together with topologies play critical roles in enabling more effective MAS design. Based on the insights, we propose Multi-Agent System Search (MASS), a MAS optimization framework that efficiently exploits the complex MAS design space by interleaving its optimization stages, from local to global, from prompts to topologies, over three stages: 1) block-level (local) prompt optimization; 2) workflow topology optimization; 3) workflow-level (global) prompt optimization, where each stage is conditioned on the iteratively optimized prompts/topologies from former stages. We show that MASS-optimized multi-agent systems outperform a spectrum of existing alternatives by a substantial margin. Based on the MASS-found systems, we finally propose design principles behind building effective multi-agent systems.

---

## 论文详细总结（自动生成）

# 多智能体设计：通过更好的提示和拓扑优化智能体（MASS）——论文深入总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多智能体系统（MAS）的设计依赖于手动配置每个智能体的**提示（prompt）** 以及智能体间的**拓扑结构**（即交互与协作方式）。然而，这两个设计空间都非常庞大且相互耦合，手动调优费时费力，且易受智能体提示敏感性的级联影响。
- **动机**：现有自动化工作要么单独优化提示（如 DSPy），要么单独优化拓扑（如 AFlow、ADAS），但**缺乏对两者联合优化的系统性理解**。作者认为，提示和拓扑都是影响 MAS 性能的关键因素，且存在相互依赖关系，需要协同优化。
- **整体意义**：提出了一个名为 **MASS（Multi-Agent System Search）** 的自动化框架，通过分阶段交替优化提示和拓扑，自动发现高效的多智能体系统，从而降低人工设计成本并提升任务性能。

## 2. 论文提出的方法论

### 核心思想
将 MAS 的设计视为一个**组合优化问题**，同时搜索最优的提示（指令和示例）和最优的智能体交互拓扑。通过“从局部到全局、从提示到拓扑”的渐进式优化，降低搜索复杂度。

### 关键技术细节
MASS 包含三个优化阶段：

1. **模块级提示优化（Block-level Prompt Optimization）**  
   - 对每个基础构建块（如 Predictor、Reflector、Debator 等）单独进行提示优化。  
   - 使用 MIPROv2（贝叶斯代理模型）联合优化指令和少量示例。  
   - 先从单智能体开始 warm-up，然后对每个拓扑的最小配置（如 2 个 Predictor + 1 个 Debator 作为 Debate 模块）进行优化，并记录验证集上的性能增益（影响力指标 \( I_{a_i} = E(a_i^*)/E(a_0^*) \)）。

2. **工作流拓扑优化（Workflow Topology Optimization）**  
   - 基于第一阶段得到的各模块影响力 \( I_a \)，通过 Softmax 计算每个拓扑维度被选中的概率 \( p_a = \text{Softmax}(I_a, t) \)。  
   - 通过拒绝采样生成候选拓扑，激活满足 \( u > p_a \) 的维度（\( u \sim U(0,1) \)），并限制总智能体数量不超过预算 \( B \)。  
   - 在预设的顺序约束（如 Summarize → Reflect → Debate → Aggregate）下搜索有效拓扑配置。

3. **工作流级提示优化（Workflow-level Prompt Optimization）**  
   - 固定第二阶段找到的最佳拓扑，对整个 MAS 系统进行全局提示优化，以建模智能体间的相互依赖关系。

### 算法流程（文字说明）
- 输入：搜索空间 A、拓扑构建函数、提示优化器 O、评估器 E、验证集 D、温度 t、候选数 N、预算 B。  
- 输出：优化的多智能体系统 W*。  
  1. 对初始智能体进行提示优化得到 \( a_0^* \)。  
  2. 对每个其他构建块进行条件提示优化，得到 \( a_i^* \)，并计算影响力 \( I_{a_i} \)。  
  3. 根据影响力计算选择概率，通过拒绝采样生成 N 个候选拓扑，评估并选出最佳拓扑 \( W_c^* \)。  
  4. 对最佳拓扑进行工作流级全局提示优化，得到最终系统 \( W^* \)。

## 3. 实验设计

### 数据集与场景
| 任务类型 | 数据集 | 评估指标 |
|---------|--------|----------|
| 数学推理 | MATH | 准确率 |
| 离散推理 | DROP | F1 |
| 多跳长上下文理解 | HotpotQA, MuSiQue, 2WikiMultiHopQA | F1 |
| 代码生成 | MBPP, HumanEval, LiveCodeBench (test output prediction) | pass@1 / 准确率 |

### 对比方法
- **手动基线**：CoT、CoT-SC（自一致性）、Self-Refine、Multi-Agent Debate  
- **自动设计基线**：ADAS（基于元智能体的搜索）、AFlow（基于蒙特卡洛树搜索的流程优化）  
- 所有方法限制最大智能体数 ≤ 10。

### 主要模型
- 主实验：Gemini 1.5 Pro 和 Gemini 1.5 Flash  
- 验证实验：Claude 3.5 Sonnet

## 4. 资源与算力

- **论文未明确说明**使用的 GPU 型号、数量或训练时长。  
- 提及使用了 Gemini 1.5 Pro/Flash 和 Claude 3.5 Sonnet 作为 LLM 后端，优化过程涉及大量 API 调用（提示优化、拓扑评估等），但具体算力成本未量化。

## 5. 实验数量与充分性

- **实验数量**：  
  - 在 8 个数据集上报告了 Gemini 1.5 Pro 和 Flash 的结果（表 1）。  
  - 额外在 Claude 3.5 Sonnet 上验证了 6 个数据集（表 4）。  
  - 进行了分阶段消融实验（图 5），对比了不同阶段贡献及有无剪枝的影响。  
  - 提供了优化轨迹对比（图 6）和 token 效率分析（图 9）。  
  - 附录中展示了最佳拓扑可视化（图 8）和部分优化提示示例。

- **充分性与公平性**：  
  - 任务覆盖了推理、多跳理解、代码生成，较为全面。  
  - 对比方法均采用相同后端模型，限制智能体数量一致。  
  - 但部分基线（如 AFlow）的元提示仅适用于 Claude，因此作者用 Claude 作为优化器、Gemini 作为执行器进行了参考性对比，并非完全公平。  
  - 消融实验验证了每个阶段的必要性，客观性较好。

## 6. 论文的主要结论与发现

1. **提示优化比单纯增加智能体数量更 token 有效**，且优化后的提示与其他拓扑模块组合能进一步提升性能。  
2. **并非所有拓扑都有益**，只有少数拓扑（如辩论、聚合）在特定任务上带来正增益，因此需要在影响力空间内搜索。  
3. **MASS 的三个阶段都带来显著增量**：模块级提示优化（+6%）、拓扑优化（+3%）、工作流级提示优化（+2%），最终平均性能提升约 13%（对比 CoT）。  
4. **MASS 显著优于所有手动和自动基线**，在 Gemini 1.5 Pro 上平均 78.8%（Flash 74.3%），在 Claude 3.5 Sonnet 上也大幅领先。  
5. 总结出三条设计原则：  
   - 先在局部优化单个智能体的提示，再组合。  
   - 通过组合影响力高的拓扑构建更有效的 MAS。  
   - 对整体系统进行全局提示优化有助于建模智能体间的依赖。

## 7. 优点

- **方法创新**：首次在 MAS 自动化设计中联合优化提示和拓扑，并采用分阶段策略降低搜索复杂度。  
- **设计空间分析深入**：通过预实验量化提示和拓扑的影响力，为剪枝搜索空间提供理论依据。  
- **实验全面**：多个领域、多个模型、多种基线，消融实验充分。  
- **结果显著**：在所有任务上均获得最佳或接近最佳结果，且 token 效率更高。  
- **可解释性强**：通过影响力度量选择拓扑，优化过程可视化，并提炼出设计原则。

## 8. 不足与局限

- **实验覆盖有限**：仅使用了 Gemini 和 Claude 系列模型，未验证其他主流 LLM（如 GPT-4、Llama）。  
- **搜索空间可能不完整**：拓扑仅包含 Aggregate、Reflect、Debate、Summarize、Tool-use 等，未涵盖更复杂的动态路由或分层结构。  
- **公平性缺陷**：AFlow 基线因元提示限制使用了不同优化器，对比不完全公平。  
- **计算成本未量化**：未报告优化所需的 token 总量、API 调用次数或 GPU 小时数，实际部署成本不明确。  
- **泛化能力**：方法高度依赖验证集和评估指标，在零样本或低资源场景下可能迁移性不足。  
- **未讨论失败案例**：对某些任务（如 MuSiQue 上 MASS 提升较小）的原因未深入分析。

（完）
