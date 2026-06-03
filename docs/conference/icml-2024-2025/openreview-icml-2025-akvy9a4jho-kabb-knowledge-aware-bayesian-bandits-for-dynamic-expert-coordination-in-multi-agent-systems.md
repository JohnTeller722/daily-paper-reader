---
title: "KABB: Knowledge-Aware Bayesian Bandits for Dynamic Expert Coordination in Multi-Agent Systems"
title_zh: KABB：多智能体系统中动态专家协调的知识感知贝叶斯Bandits
authors: "Jusheng Zhang, Zimeng Huang, Yijia Fan, Ningyuan Liu, Mingyan Li, Zhuojie Yang, Jiawei Yao, Jian Wang, Keze Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AKvy9a4jho"
tags: ["query:mas-routing"]
score: 9.0
evidence: 通过贝叶斯Bandits动态协调专家实现路由
tldr: 多智能体系统面临静态知识和协调效率低下的挑战。本文提出KABB框架，利用知识感知贝叶斯Bandits实现动态专家选择和自适应路由。该框架通过知识距离模型和Thompson采样策略，在保持高性能的同时显著降低了通信成本。实验证明KABB在多智能体任务中取得了最优的成本-性能平衡。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 786, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 978, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 727, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1764, \"height\": 955, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1531, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1532, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 610, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 725, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1279, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1782, \"height\": 2086, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1783, \"height\": 1694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1785, \"height\": 1796, \"label\": \"Table\"}]"
motivation: 多智能体系统受限于静态知识和低效的协调机制。
method: 提出知识感知贝叶斯Bandits框架，包含知识距离模型和自适应Thompson采样。
result: KABB在多个任务上实现了最优的成本-性能平衡。
conclusion: 动态专家路由是提升多智能体系统效率的关键，KABB提供了有效方案。
---

## Abstract
As scaling large language models faces prohibitive costs, multi-agent systems emerge as a promising alternative, though challenged by static knowledge assumptions and coordination inefficiencies. We introduce Knowledge-Aware Bayesian Bandits (KABB), a novel framework that enhances multi-agent system coordination through semantic understanding and dynamic adaptation. The framework features three key innovations: a customized knowledge distance model for deep semantic understanding, a dual-adaptation mechanism for continuous expert optimization, and a knowledge-aware Thompson Sampling strategy for efficient expert selection. Extensive evaluation demonstrates KABB achieves an optimal cost-performance balance, maintaining high performance while keeping computational demands relatively low in multi-agent coordination.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题背景**：随着大语言模型（LLM）规模扩大，训练和推理成本急剧上升。多智能体系统（MAS）通过协调多个专家模型提供了一种有前景的替代方案，但现有方法（如 Mixture-of-Agents、Mixture-of-Experts）存在两个关键局限：
  - **静态知识假设**：无法适应专家能力随时间的变化或新概念的出现。
  - **协调效率低**：要么计算成本随智能体数量线性增长（如 MoA），要么只能处理预定义任务（如 MoE）。
- **研究动机**：将多臂老虎机（MAB）的探索-利用平衡能力与知识图谱的语义表示能力结合，构建一个动态、自适应的专家协调框架。
- **整体含义**：提出 **KABB（Knowledge-Aware Bayesian Bandits）**，通过知识距离模型、双适应机制和知识感知的汤普森采样，实现**语义理解驱动的动态专家选择**，在保持高性能的同时显著降低计算成本，为 MAS 提供更灵活高效的协作范式。

## 2. 方法论
### 核心思想
- 将专家能力、任务需求、团队协同性映射到知识图谱中，利用贝叶斯在线学习动态优化专家子集的选择策略。

### 关键技术细节
- **知识距离模型（Knowledge Distance）**  
  定义一个复合距离函数 `Dist(S, t)`，综合考虑五个维度：
  - 任务难度（基于知识图谱拓扑深度）
  - 语义匹配（Jaccard 相似度）
  - 依赖复杂度（知识图中专家与任务的依赖边数）
  - 历史有效性（平均历史成功率）
  - 团队互补性（Synergy，量化内部协作程度）
  各维度通过可学习权重加权，并证明该距离满足伪度量性质（非负性、条件对称性、近似三角不等式）。

- **双适应机制（Dual Adaptation）**  
  - **贝叶斯参数自适应**：使用指数时间衰减因子 `γ^Δt` 更新 Beta 分布参数，强调近期反馈，弱化陈旧数据。
  - **知识图谱进化**：根据任务结果持续更新概念关系（如概念重叠、团队协同性），使专家表示随时间演化。

- **知识感知汤普森采样（Knowledge-Aware Thompson Sampling）**  
  在传统 Beta 分布采样的置信度函数中引入三项修正：
  - 知识距离惩罚 `exp(-λ·Dist(S,t))`
  - 时间衰减 `γ^Δt`
  - 团队协同增益 `Synergy^η`
  最终通过 `θ̃_S = E[θ_S] · exp(-λ·Dist) · γ^Δt · Synergy^η` 指导专家子集选择，实现探索-利用的高效平衡。

- **聚合阶段**：采用两阶段知识图谱引导的响应集成，包括语义冲突检测和加权融合，减少矛盾输出。

### 算法流程（文字说明）
1. 接收任务 `T_t`，解析为概念需求向量 `d_t`；
2. 将每个 LLM 映射为能力向量 `v_e`，形成专家集合 `E`；
3. 根据 `d_t` 和 `v_e` 计算知识距离，并通过知识感知汤普森采样选出最优专家子集 `S_t`（默认 top-3 专家从 top-2 概念）；
4. 所选专家独立生成回答，聚合器合成最终输出；
5. 收集性能反馈（成功/失败），更新贝叶斯参数 `α, β` 并调整知识图谱。

## 3. 实验设计
### 数据集与基准
- **主要评测**：
  - **AlpacaEval 2.0**（805 条指令，GPT-4 作为评判者，报告长度控制的 LC 胜率）
  - **MT-Bench**（多轮对话能力）
  - **FLASK-Hard**（89 个困难样本，12 个技能维度评分）
- **附加评测（附录 D）**：
  - **BBH**（BIG-Bench Hard，推理任务）
  - **MATH**（数学问题求解）
  - **Arena-Hard**（500 道难题）

### 基线方法
- 单模型：GPT-4 系列、Qwen2-72B-Instruct、LLaMa-3-70B-Instruct、Gemma-2-27B、WizardLM-2-8x22B、DeepSeek-V3、DeepSeek-R1。
- 多智能体系统：**Mixture-of-Agents (MoA)**（同模型配置，6 个提议者 + 1 个聚合器，2 层结构）。
- 消融变体：KABB w/o Deepseek、KABB-Single-LLaMa3。
- 路由/优化方法对比（表 2）：知识感知路由（KA）+ MAB vs. 分类器路由（CL）、PPO、MCTS、A2C。

### 模型配置
- 6 个开源模型作为专家库，12 个知识概念，24 个专家（通过定制提示使模型专注特定领域）。
- 聚合器固定为 Qwen2-72B-Instruct。
- 默认选择 top-2 概念、top-3 专家。

## 4. 资源与算力
- 论文在附录 F 中明确说明：**所有实验在一台搭载单张 NVIDIA GeForce RTX 3090 的服务器上完成**。
- **未提及训练时长**，模型均为现成开源模型，无需重新训练。仅需进行推理和在线更新（参数更新计算量小），因此对算力需求较低。论文强调成本-性能比优势。

## 5. 实验数量与充分性
- **主要实验数量**：包含 3 个核心基准（表 1、图 3），2 个路由/优化方法对比（表 2），3 个推理基准（附录 D 表 3-4），以及参数敏感性分析（附录 B）、概念/专家数量影响分析（附录 C）和案例研究（附录 E）。
- **充分性评价**：
  - 覆盖**对话、指令跟随、推理、数学、编程**等多种能力，基准全面。
  - 消融实验（w/o Deepseek、Single-LLaMa3）验证了组件贡献。
  - 与不同路由策略和优化算法的对比客观且公平（相同模型配置、相同评估协议）。
  - 采用了长度控制去偏（LC win rate），避免长度偏见。
  - **潜在局限**：仅在通用英文任务上评估，未涉及多语言或垂直领域（如医疗、法律）；Arena-Hard 上 KABB 不如 GPT-4 系列；部分案例显示专家选择可能不够精准。

## 6. 主要结论与发现
- **性能领先**：KABB 在 AlpacaEval 2.0 上达到 **77.9% LC 胜率**，比 MoA（68.1%）提升 9.8%，仅次于 DeepSeek-R1（80.1%）。MT-Bench 平均分 9.60，高于所有单模型和 MoA。
- **成本效益突出**：仅需选择 2-3 名专家即可获得接近甚至超越全量模型的效果。与 MoA 相比，达到相似 LC 胜率的成本仅为 1/7。在成本-性能帕累托前沿上表现最优。
- **动态适应有效**：知识感知路由（KA）显著优于分类器路由（CL），且 MAB 优化器优于 PPO、MCTS、A2C。
- **理论保证**：证明了知识距离的伪度量性质和累计遗憾上界（O(√T log T)）。

## 7. 优点
- **创新性**：首次将知识距离、团队协同和时间衰减统一纳入贝叶斯 MAB 框架，形成闭环动态优化。
- **实用性强**：直接使用现有 LLM 作为专家，无需额外训练或微调，易于部署。
- **效率高**：通过知识图谱先验减少不必要的探索，在成本敏感场景下优势明显。
- **理论完备**：提供了知识距离度量的数学性质和收敛性证明，支撑方法可靠性。
- **评估严谨**：使用多种去偏指标（LC win rate、RAS、PWRS），消融实验全面，代码和配置可复现。

## 8. 不足与局限
- **实验覆盖**：仅针对通用英文任务，未验证在多语言、专业领域（如医学、法律）或长文档处理上的表现。
- **专家选择偏差**：案例研究（附录 E 表 7-8）显示，某些情况下 KABB 会误选不相关的专家（如将人文专家分配给植物学问题），虽能通过增加专家数部分缓解，但仍有改进空间。
- **输出简洁性**：在 FLASK-Hard 的“conciseness”维度上得分略低于基线，说明聚合器倾向于生成更详尽的回答，可能牺牲简洁性。
- **环境依赖**：实验基于单张 3090，但实际生产部署可能需要更高算力（如处理高并发请求）。论文未提供端到端延迟测量。
- **静态知识图谱初始化**：12 个概念和 24 个专家需要人工定义，如何自动构建或扩展知识图谱未讨论。
- **对比方法局限**：与 MoA 对比时，MoA 的聚合器与 KABB 相同，但 MoA 本身也有多种变体（如层数不同），论文未进行充分的超参数调优。

（完）
