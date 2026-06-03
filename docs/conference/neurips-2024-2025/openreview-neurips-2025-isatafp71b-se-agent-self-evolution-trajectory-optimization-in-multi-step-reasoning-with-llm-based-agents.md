---
title: "SE-Agent: Self-Evolution Trajectory Optimization in Multi-Step Reasoning with LLM-Based Agents"
title_zh: SE-Agent：基于LLM智能体的多步推理自进化轨迹优化
authors: "Yifu Guo, Jiaye Lin, Huacan Wang, Yuzhen Han, Sen Hu, Ziyi Ni, Licheng Wang, Mingguang Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=isATAFP71B"
tags: ["query:mas-routing"]
score: 4.0
evidence: 自进化轨迹优化用于多步推理
tldr: SE-Agent针对LLM智能体的多步推理轨迹进行自进化优化，通过构建轨迹库和利用MCTS变体，平衡探索与利用，提升推理效率和正确性。实验表明该方法在多个推理任务上优于基线，为选择最优推理配置提供了新方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1463, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1216, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1272, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 541, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 1210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-isatafp71b/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 1223, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-isatafp71b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 496, \"label\": \"Table\"}]"
motivation: 现有方法忽略轨迹间相互依赖，搜索空间多样性不足，导致冗余推理。
method: 提出自进化框架，构建高质量推理轨迹库，并结合改进的MCTS进行轨迹优化。
result: 在多个复杂推理任务上显著提升准确率和效率，减少冗余步骤。
conclusion: 通过自进化轨迹优化，有效提升了多步推理的性能和资源效率。
---

## Abstract
Large Language Model (LLM)-based agents have recently shown impressive capabilities in complex reasoning and tool use via multi-step interactions with their environments. While these agents have the potential to tackle complicated tasks, their problem-solving process—agents' interaction trajectory leading to task completion—remains underexploited. These trajectories contain rich feedback that can navigate agents toward the right directions for solving problems correctly. Although prevailing approaches, such as Monte Carlo Tree Search (MCTS), can effectively balance exploration and exploitation, they ignore the interdependence among various trajectories and lack the diversity of search spaces, which leads to redundant reasoning and suboptimal outcomes. To address these challenges, we propose SE-Agent, a Self-Evolution framework that enables Agents to optimize their reasoning processes iteratively. Our approach revisits and enhances former pilot trajectories through three key operations: revision, recombination, and refinement. This evolutionary mechanism enables two critical advantages: (1) it expands the search space beyond local optima by intelligently exploring diverse solution paths guided by previous trajectories, and (2) it leverages cross-trajectory inspiration to efficiently enhance performance while mitigating the impact of suboptimal reasoning paths. Through these mechanisms, SE-Agent achieves continuous self-evolution that incrementally improves reasoning quality. We evaluate SE-Agent on SWE-bench Verified to resolve real-world GitHub issues. Experimental results across five strong LLMs show that integrating SE-Agent delivers up to 55% relative improvement, achieving state-of-the-art performance among all open-source agents on SWE-bench Verified.

---

## 论文详细总结（自动生成）

# SE-Agent：基于LLM智能体的多步推理自进化轨迹优化 —— 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：大语言模型（LLM）已在自然语言理解和代码生成等领域展现出强大能力。当配备外部工具和环境交互能力时，这些模型发展为能够处理复杂现实任务的自主智能体。然而，复杂的任务通常需要多轮交互，形成所谓的“推理轨迹”——包含状态和动作序列的交互过程。这些轨迹蕴含了丰富的反馈信息，可用于引导智能体向正确方向解决问题。
- **核心问题**：现有方法（如蒙特卡洛树搜索 MCTS）虽然在探索与利用之间实现了平衡，但它们将轨迹视为独立实体，忽略了不同轨迹之间的相互依赖关系，且搜索空间的多样性不足。这导致推理步骤冗余和次优结果。具体而言，即使采用多样化的采样策略（如改变温度参数或提示词），智能体产生的轨迹在结构上往往高度相似，导致最终结果同质化，限制了搜索空间的有效扩展。
- **研究动机**：针对上述局限性，作者提出 SE-Agent——一个自进化框架，使智能体能够通过迭代优化其推理过程，从而超越初始性能边界，发现传统采样方法难以涌现的新问题解决能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
SE-Agent 的核心思想是利用多条推理轨迹中蕴含的集体智能，通过系统性操作轨迹（而非仅调整采样参数）来生成真正多样化的解决方案，并有效逃离局部最优。具体而言，它通过三个关键操作——**修订（Revision）**、**重组（Recombination）** 和**精炼（Refinement）**——实现轨迹的自我进化。

### 关键技术细节

#### 2.1 修订操作（Revision）
- **生成初始轨迹**：
  - **多规划探索**：通过改变规划策略、提示技术和推理方法，生成多条不同的初始轨迹，最大化轨迹库的维度多样性。
  - **基于突变的多样化**：对现有轨迹应用受控突变（如改变推理步骤、动作选择或中间结论），进一步扩展轨迹池。初始轨迹池通常包含约10条轨迹。
- **反思与修订**：对每条轨迹进行关键反思，分析其优缺点和改进潜力；然后根据反思结果生成修订后的轨迹，消除冗余或循环推理，纳入替代视角。

#### 2.2 重组操作（Recombination）
- **交叉（Crossover）**：识别不同轨迹中的高性能片段，组合成继承多个父本优势的混合轨迹。
- **迁移学习（Transfer）**：将成功轨迹中的知识和策略系统性地转移到欠发达的轨迹上。
- **重构（Restructuring）**：基于全局轨迹分析，利用集体洞察对轨迹进行整体重组。

#### 2.3 精炼操作（Refinement）
- **多维度奖励函数**：综合考虑任务完成度（如非空补丁文件、足够的代码编辑步骤）、推理质量（逻辑连贯性、深度和鲁棒性）和效率（推理步数和资源利用），通过自动指标和专门的评估器（包括规则验证和LLM评估）对轨迹进行评分。
- **选择与收敛**：采用混合选择机制，自动保留高分轨迹并确保不同推理方法的多样性。迭代持续进行，直到达到预设迭代次数或收敛标准（连续迭代中最大奖励提升低于阈值 ε）。最终输出得分最高的轨迹作为最终答案。

#### 算法流程（文字说明）
1. 对给定任务 T，通过多规划探索和突变生成初始轨迹池 T0。
2. 对每条轨迹执行反思与修订，产生修订后的轨迹集合。
3. 利用交叉、迁移和重构三种策略对轨迹进行重组，生成新的混合轨迹。
4. 通过多维度奖励函数评估所有轨迹，并选择 elite 轨迹构成下一代的轨迹池。
5. 重复步骤2-4直到收敛或达到最大迭代次数。
6. 输出最终奖励最高的轨迹作为解决方案。

## 3. 实验设计：数据集、基准与对比方法

### 数据集与基准
- **SWE-bench Verified**：一个从更广泛的 SWE-bench 中精心挑选的子集，包含500个来自真实GitHub仓库的问题。每个实例包括一个自然语言描述的问题描述和对应的代码仓库，开发者编写的单元测试用于验证生成的补丁是否正确。该基准被广泛用于评估自动修复bug系统的有效性。

### 对比方法
- **SWE-Agent**：基于 CodeAct 的框架（作为 SE-Agent 的基础集成模块）。
- **SWE-Search**：基于 MCTS 的多智能体框架，集成自我改进机制。
- 对比在以下5个LLM上进行：
  - **开源模型**：DeepSeek-V3-0324、Qwen-2.5-72b-Instruct、Llama-3.1-70b-Instruct
  - **闭源模型**：GPT-4o、Claude-3.7-Sonnet（后续扩展到Claude-4-Sonnet，达到80.0%解决率）

### 评估指标
- **Pass@1**：首次尝试即成功解决的问题百分比。
- **Pass@5**：在最多五次尝试中成功解决的问题百分比。

## 4. 资源与算力

- **计算资源**：论文在附录A中给出了部署细节：
  - 开源模型（DeepSeek-V3-0324、Qwen-2.5-72B-Instruct、LLaMA-3.1-70B-Instruct）在本地运行，使用 **NVIDIA A100 GPU（80GB内存）**。
  - 闭源模型（GPT-4o、Claude-3.7-Sonnet）通过官方API访问。
- **未明确说明的部分**：
  - 未提及使用的 GPU 数量、训练时长或总体算力消耗（如GPU小时数）。
  - 未报告单独基线方法的资源消耗，因此无法直接比较计算成本。
  - 论文指出 SE-Agent 在相同API成本预算下优于基线（图4展示了最大成本与Pass@1的关系），但未给出绝对成本数值。

## 5. 实验数量与充分性

### 实验分组
1. **主实验**：在5个LLM上对比SE-Agent与两个基线方法（SWE-Agent、SWE-Search），报告Pass@1和Pass@5（表1）。
2. **消融实验**：评估三个变体（w/o Revision、w/o Recombination、w/o All）的性能下降（图2）。
3. **重叠分析**：使用维恩图展示不同框架成功解决问题的重叠情况（图3）。
4. **超参数分析**：改变候选轨迹数量（0到20）和最大API成本，观察性能变化（图4）。
5. **案例研究**：提供两个具体案例（scikit-learn #14629 和 Astropy 问题）说明SE-Agent如何通过自进化解决传统方法无法处理的问题（图5、图6、图7）。

### 充分性分析
- **优点**：
  - 覆盖多种模型（开源+闭源），验证了框架的通用性。
  - 消融实验清晰展示了每个模块的贡献。
  - 超参数敏感性分析提供了实际部署参考。
  - 案例研究深入展示了机制的有效性。
- **不足**：
  - 仅使用单一基准（SWE-bench Verified），缺乏在其他多步推理任务（如数学推理、规划、代码生成等）上的验证。
  - 未报告多次运行的统计显著性（如误差条或置信区间），尽管论文在NeurIPS checklist中声称“实验多次并报告平均结果”，但正文中未给出具体数值。
  - 未进行与多种MCTS变体或更复杂的搜索方法的对比（如Tree-of-Thoughts、Graph-of-Thoughts）。
  - 消融实验仅针对Claude-3.7-Sonnet（图2未明确说明，但根据上下文可能是单一模型），未在不同模型上均验证。

## 6. 论文的主要结论与发现

1. **SE-Agent 在所有5个LLM上均显著优于基线**：与SWE-Agent相比，相对提升高达112%（Llama-3.1-70B）；与更强的MCTS基线SWE-Search相比，平均相对提升约30%。
2. **在所有开源智能体中达到SOTA**：在SWE-bench Verified上，使用Claude-3.7-Sonnet达到61.2% Pass@1，使用Claude-4-Sonnet达到80.0%。
3. **轨迹级操作的有效性**：修订操作提供了多样化的初始轨迹，重组操作实现了跨轨迹的知识融合，精炼操作确保了最终选择的质量。
4. **跨轨迹启发式探索的优势**：SE-Agent能够解决其他方法无法解决的12个独特问题实例（图3维恩图），表明其能探索更广泛的解空间。
5. **计算效率**：仅需10条候选轨迹即可达到近最优性能，且在同一API成本预算下持续优于基线（图4）。

## 7. 优点

- **创新性**：首次将自进化思想引入轨迹层面，而非仅调整采样参数，实现了真正的解空间多样性。
- **通用性**：可作为即插即用模块集成到现有智能体框架中（如SWE-Agent），且不依赖特定LLM能力，只要任务需要多步推理即可受益。
- **理论基础**：与遗传算法和强化学习中的专家迭代方法有概念上的联系，但进行了关键区别（显式操作完整轨迹而非状态-动作对）。
- **实验严谨性**：覆盖多种LLM家族（开源/闭源），进行消融实验和超参数分析，提供了案例研究以直观展示机制。
- **可复现性**：论文提供匿名代码链接，并详细列出了所有提示词模板（附录B）。

## 8. 不足与局限

- **实验覆盖不足**：仅使用SWE-bench一个基准，且只针对代码修复任务。未在多步推理的其他领域（如数学、规划、科学推理）验证泛化能力。
- **缺乏统计显著性报告**：未给出多次运行的误差条或置信区间，削弱了结论的统计可靠性。
- **计算资源比较不透明**：未提供SE-Agent与基线方法的详细计算成本对比（如总API调用次数、GPU小时数），仅展示了成本-性能曲线，但缺少绝对数值。
- **消融实验局限**：仅在Claude-3.7-Sonnet上进行消融？图2说明“Ablation study on SWE-bench Verified with three variants”，但未明确注明模型，推测可能只用一个模型。缺乏跨模型消融验证。
- **应用限制**：
  - 需要生成多条初始轨迹，可能增加初期计算开销。
  - 反思和重组过程依赖LLM的批评能力，如果基座模型反思能力弱，框架效果可能受限。
  - 当前实现针对SWE-bench任务设计（涉及代码编辑），直接迁移到其他类型推理任务可能需要调整操作定义。
- **与其他方法的对比有限**：未与更先进的搜索方法（如Beam Search变体、多样性增强采样）或在其他基准上对比，难以全面评估相对优势。
- **理论基础的解释**：虽然提到与遗传算法的相似性，但未给出严格的收敛性分析或理论基础证明。

（完）
