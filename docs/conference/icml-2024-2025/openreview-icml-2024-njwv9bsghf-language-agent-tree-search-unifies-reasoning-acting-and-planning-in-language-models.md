---
title: "Language Agent Tree Search Unifies Reasoning, Acting, and Planning in Language Models"
title_zh: 语言代理树搜索：统一语言模型中的推理、行动与规划
authors: "Andy Zhou, Kai Yan, Michal Shlapentokh-Rothman, Haohan Wang, Yu-Xiong Wang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=njwv9BsGHF"
tags: ["query:mas-routing"]
score: 6.0
evidence: 将蒙特卡洛树搜索与LLM集成用于推理和规划，与多跳推理配置优化相关
tldr: 现有语言模型在决策任务中依赖简单行为过程，限制了其作为自主代理的部署。本文提出语言代理树搜索（LATS），将蒙特卡洛树搜索与语言模型集成，统一了推理、行动和规划能力。通过树搜索和自反思，LATS显著提升了代理在复杂任务中的探索和适应能力，为多跳推理中的资源配置优化提供了框架性方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-njwv9bsghf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 656, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-njwv9bsghf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1757, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-njwv9bsghf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 696, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-njwv9bsghf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1758, \"height\": 931, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 744, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 743, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 778, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 611, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 878, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 748, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1338, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 714, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1711, \"height\": 1250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 740, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 809, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-njwv9bsghf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 813, \"height\": 194, \"label\": \"Table\"}]"
motivation: 现有语言模型代理的简单行为过程限制了其自主部署，需要更统一的推理-规划-行动框架。
method: 将蒙特卡洛树搜索集成到语言模型中，结合基于LM的价值函数和自反思进行探索式决策。
result: 在多种决策任务中，LATS框架优于现有方法，实现了更有效的自适应问题求解。
conclusion: LATS通过树搜索统一了推理、行动与规划，为LLM代理的决策强化提供了新范式。
---

## Abstract
While language models (LMs) have shown potential across a range of decision-making tasks, their reliance on simple acting processes limits their broad deployment as autonomous agents. In this paper, we introduce Language Agent Tree Search (LATS) -- the first general framework that synergizes the capabilities of LMs in reasoning, acting, and planning. By leveraging the in-context learning ability of LMs, we integrate Monte Carlo Tree Search into LATS to enable LMs as agents, along with LM-powered value functions and self-reflections for proficient exploration and enhanced decision-making. A key feature of our approach is the incorporation of an environment for external feedback, which offers a more deliberate and adaptive problem-solving mechanism that surpasses the constraints of existing techniques. Our experimental evaluation across diverse domains, including programming, interactive question-answering (QA), web navigation, and math, validates the effectiveness and generality of LATS in decision-making while maintaining competitive or improved reasoning performance. Notably, LATS achieves state-of-the-art pass@1 accuracy (92.7%) for programming on HumanEval with GPT-4 and demonstrates gradient-free performance (average score of 75.9) comparable to gradient-based fine-tuning for web navigation on WebShop with GPT-3.5. Code can be found at https://github.com/lapisrocks/LanguageAgentTreeSearch

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有语言模型（LM）在作为自主代理时，通常依赖简单的行为过程（如ReAct中的单步推理-行动循环），缺乏深思熟虑的决策能力：无法考虑多条路径、无法前瞻规划、也无法从外部反馈中有效学习。这限制了它们在复杂、交互式环境中的通用部署。
- **研究动机**：尽管LM在推理（如CoT、ToT）和行动（如ReAct、Reflexion）方面已有进展，但现有方法要么只依赖内部知识（无外部反馈），要么是反射式的（不进行多步搜索）。亟需一个统一框架，同时具备**推理、行动和规划**能力，并能利用环境反馈动态调整策略。
- **整体含义**：本文提出的**语言代理树搜索（LATS）**首次将蒙特卡洛树搜索（MCTS）与LM代理结合，通过树搜索进行规划，利用LM生成的价值函数和自反思进行高效探索，从而显著提升LM在多种决策和推理任务上的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将每个决策步骤视为树中的一个节点（状态），状态包含输入、已执行的动作序列和观察序列。使用MCTS在该树上进行搜索，同时利用LM作为**策略生成器**（扩展节点）、**价值函数**（评估节点）和**反思生成器**（提供语义梯度）。整个过程无需额外训练，仅通过上下文学习实现。
- **关键技术细节**：
  - **节点结构**：节点 `s = [x, a_1...i, o_1...i]`，其中 `x` 为初始输入，`a_i` 为动作，`o_i` 为环境观察。
  - **动作空间**：混合空间，包含**推理痕迹**（内部思想）和**外部行动**（如API调用、搜索、点击等）。
  - **算法流程**：包括六个操作：
    1. **Selection（选择）**：从根节点开始，使用UCT公式选择最有前景的叶子节点。
    2. **Expansion（扩展）**：从选中的节点采样n个动作，执行并获取环境观察，添加n个子节点。
    3. **Evaluation（评估）**：为每个新节点计算价值分数。
    4. **Simulation（模拟）**：从当前节点继续扩展直到终止状态（成功将终止）。
    5. **Backpropagation（反向传播）**：用终止时的奖励更新路径上所有节点的访问次数和平均价值。
    6. **Reflection（反思）**：若任务失败，使用LM生成语义反思，存储为经验，在后续搜索中作为上下文提示。
- **价值函数公式**：
  \[
  V(s) = \lambda \cdot LM(s) + (1-\lambda) \cdot SC(s)
  \]
  - `LM(s)`：向LM提供节点状态和外部反馈，让其生成一个1-10的分数。
  - `SC(s)`：自一致性分数，即从同一状态多次采样得到的动作中，出现频率高的倾向更正确。
  - `λ` 为超参数，控制两部分权重。
- **UCT公式**：用于选择节点：
  \[
  UCT(s) = V(s) + w \sqrt{\frac{\ln N(p)}{N(s)}}
  \]
  其中 `N` 为访问次数，`w` 为探索权重。

## 3. 实验设计：数据集、场景、基准、对比方法

- **数据集与场景**：
  - **HotPotQA**：多跳问答，使用Wikipedia API进行信息检索（外部反馈可提供正确答案的验证）。
  - **HumanEval & MBPP**：编程任务，用合成测试套件提供编译和运行反馈。
  - **WebShop**：在线购物环境，1.18M商品，12k指令，需导航并匹配用户规格。
  - **Game of 24**：数学推理任务（仅内部推理，无外部环境反馈）。
- **基准方法**：
  - 推理类：CoT、CoT-SC、ToT、RAP。
  - 行动类：ReAct、Reflexion。
  - 混合类：将ToT/RAP扩展为支持外部反馈的版本（ToT(ReAct)、RAP(ReAct)）。
  - 其他：Beam Search（Xie et al.）、IL/RL（WebShop领域）。
- **评估指标**：
  - HotPotQA：Exact Match (EM)。
  - HumanEval/MBPP：Pass@1。
  - WebShop：平均分数（Score）和成功率（SR）。
  - Game of 24：成功率。

## 4. 资源与算力

- **文中说明**：论文在致谢中提到“This work used NVIDIA GPUs at NCSA Delta through allocations CIS220014, CIS230012, and CIS230218 from the ACCESS program”。但**未明确给出**具体的GPU型号、数量、单次实验的推理时间或训练时长（LATS本身无需训练，仅进行推理）。
- **备注**：由于方法基于推理（无模型训练），算力主要用于LM的多次调用。论文报告了不同方法的token消耗和节点数（见表9、10），但未提供绝对时间或硬件配置。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要实验覆盖4个领域共5个数据集（HotPotQA、HumanEval、MBPP、WebShop、Game of 24）。
  - 每个领域内均比较了多个基线（通常5-8个），并进行了超参数调整（如n、k、λ、w）。
  - 消融实验：在HotPotQA上测试了移除反思、修改搜索算法、移除LM价值函数、改变探索权重等；在Game of 24上验证了λ的影响；在HumanEval上测试了迭代次数对性能的影响。
- **充分性与公平性**：
  - 所有实验使用相同的LM版本（GPT-3.5或GPT-4），采样种子一致或固定。
  - 对每个方法进行了多次采样以降低方差（如k=50轨迹）。
  - 部分数据集使用了子集（HotPotQA 100问、WebShop 50指令、Game of 24 50题），但属于常见做法，且与基线在相同条件下对比。
  - 代码已开源，可复现。
- **总体评价**：实验较为充分，但若能在更大规模（如全量HotPotQA）上验证会更具说服力。消融实验设计合理，覆盖了主要组件。

## 6. 论文的主要结论与发现

- **主要结论**：LATS作为首个统一推理、行动和规划的框架，在多种任务上显著优于现有方法。
  - HotPotQA（GPT-3.5）：LATS (CoT+ReAct) 达到EM 0.71，相比ReAct (0.32) 和 Reflexion (0.51) 有大幅提升。
  - HumanEval（GPT-4）：LATS 达到 Pass@1 92.7%，成为SOTA；GPT-3.5下达到83.8%，远超ReAct (56.9%) 和 Reflexion (68.1%)。
  - MBPP（GPT-3.5）：LATS 81.1%，超过RAP (71.4%) 和 Reflexion (70.0%)。
  - WebShop（GPT-3.5）：LATS 平均分数75.9，成功率38%，超越了基于强化学习的方法（如IL+RL得分62.4，SR 28.7%）。
  - Game of 24（GPT-3.5）：LATS 成功率44%，优于RAP (40%) 和 ToT (20%)。
- **关键发现**：
  - 简单将搜索算法与外部反馈组合（如ToT(ReAct)）效果不佳，LATS的专门设计（如价值函数、反思）至关重要。
  - 使用环境反馈能显著增强推理能力（甚至可以超越纯内部推理）。
  - MCTS比DFS/BFS更适合语言代理场景，且样本效率更高（相同k下扩展更少节点）。
  - 自反思提供了有价值的语义梯度，但效果在复杂环境（WebShop）中较有限。

## 7. 优点

- **统一框架**：首次将推理、行动和规划融合到一个框架内，适用于多种任务（内部推理和外部交互）。
- **无监督/无需训练**：完全基于上下文学习，无需微调，可快速适配不同LM和环境。
- **模块化设计**：策略网络、价值函数、反思生成器可独立更换，灵活性强。
- **高效搜索**：通过MCTS和提出带自一致性的价值函数，平衡探索与利用，且token开销低于其他树搜索方法（如表9所示）。
- **强适应性**：能够利用外部反馈进行实时调整，且通过反思积累经验，实现“试错学习”。
- **实验全面性**：覆盖编程、问答、网页导航、数学推理等多样场景，验证了框架的通用性。

## 8. 不足与局限

- **计算成本较高**：相对于ReAct等简单方法，LATS需要多次LM调用和树扩展，推理时间和token消耗更大（虽然论文显示在相同预算下效率已优于ToT/RAP）。
- **环境回退假设**：方法假设可以在环境中撤回到任意历史状态（否则无法形成搜索树），这在许多真实交互环境中不成立（如物理机器人、不可逆操作）。论文承认这一限制。
- **实验数据集规模偏小**：部分实验使用了子集（如100个HotPotQA、50个WebShop），可能无法完全体现统计显著性。全量测试会更有说服力。
- **反思效果有限**：在WebShop这样复杂的环境中，LM生成的反思往往泛泛而谈，对实际改进帮助不大，导致增益低于其他任务。
- **价值函数依赖LM质量**：LM的价值评分可能不准确，尤其当任务超出其知识范围或不具备可靠的外部反馈时。
- **未讨论超参数选择指南**：λ、w、n、k等超参数对性能影响较大，但论文仅给出经验值，缺乏自动调整或迁移指导。

（完）
