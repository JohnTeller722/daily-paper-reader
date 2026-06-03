---
title: "DyFlow: Dynamic Workflow Framework for Agentic Reasoning"
title_zh: DyFlow：用于智能体推理的动态工作流框架
authors: "Yanbo Wang, Zixiang Xu, Yue Huang, Xiangqi Wang, Zirui Song, Lang Gao, Chenxi Wang, Xiangru Tang, Yue Zhao, Arman Cohan, Xiangliang Zhang, Xiuying Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0pbUfmwNTy"
tags: ["query:mas-routing"]
score: 8.0
evidence: 动态工作流生成直接对应于多智能体LLM架构中的高效任务路由
tldr: 针对现有智能体系统工作流僵化、缺乏自适应性的问题，本文提出DyFlow框架，能够根据任务需求和实时反馈动态生成并调整推理工作流。实验表明，该方法在多个推理基准上显著提升了任务成功率和推理深度，为实现多智能体系统中的动态任务路由提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 658, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 587, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0pbufmwnty/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 691, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 601, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1413, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1331, \"height\": 923, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1257, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1022, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1201, \"height\": 979, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0pbufmwnty/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1339, \"height\": 404, \"label\": \"Table\"}]"
motivation: 现有基于LLM的智能体系统工作流大多手工设计或固定，缺乏适应性和灵活性。
method: 提出DyFlow，自适应地构建和调整推理步骤，根据任务需求和实时反馈动态生成工作流。
result: 在多个推理基准上，DyFlow相比固定工作流提升了任务成功率和推理深度。
conclusion: 动态工作流生成能显著增强智能体系统的泛化能力和鲁棒性。
---

## Abstract
Agent systems based on large language models (LLMs) have shown great potential in complex reasoning tasks, but building efficient and generalizable workflows remains a major challenge. Most existing approaches rely on manually designed processes, which limits their adaptability across different tasks. While a few methods attempt automated workflow generation, they are often tied to specific datasets or query types and make limited use of intermediate feedback, reducing system robustness and reasoning depth. Moreover, their operations are typically predefined and inflexible.
To address these limitations, we propose **DyFlow**, a dynamic workflow generation framework that adaptively constructs and adjusts reasoning procedures based on task requirements and real-time intermediate feedback, thereby enhancing cross-task generalization.
DyFlow consists of two core components: a designer and an executor. The designer decomposes complex problems into a sequence of sub-goals defined by high-level objectives and dynamically plans the next steps based on intermediate outputs and feedback. These plans are then carried out by the executor, which executes each operation using dynamic operators with context-aware parameterization, enabling flexible and semantically grounded reasoning.
We systematically evaluate DyFlow across diverse domains, including social reasoning, biomedical tasks, mathematical problem solving, and code generation.
Results demonstrate that DyFlow significantly outperforms existing baselines, achieving substantial Pass@k improvements and exhibiting robust generalization across diverse domains.

---

## 论文详细总结（自动生成）

# DyFlow：用于智能体推理的动态工作流框架 - 详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于大型语言模型（LLM）的智能体系统大多采用**静态、预定义的工作流**（如角色固定、执行顺序固定），缺乏根据中间反馈进行适应性调整的能力。当子任务失败或产生异常输出时，系统通常只能中断或传播错误，无法动态修正计划。
- **背景**：尽管已有一些方法尝试自动化工作流生成（如AFlow、ADAS），但它们仍属于“预执行优化”——工作流在运行前固定，且对中间反馈利用不足。而像DyLAN、MaAS等虽能动态配置智能体，但无法在子目标层面实时调整。
- **整体含义**：本文提出**DyFlow**，一个**反馈驱动、动态生成工作流**的框架，使智能体推理过程能够根据实时中间输出、错误信号自适应地规划后续步骤，从而提升跨任务泛化能力和鲁棒性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将复杂推理建模为**迭代的子目标规划与执行循环**，通过高层“设计者”（Designer）和底层“执行者”（Executor）的分工实现动态适应。
- **关键技术细节**：
  - **状态表示**：系统在每个时间步 \( t \) 维护一个状态 \( s_t \)，包含原始任务、历史计划、中间输出和错误信息。
  - **算子模板集合**：定义一组可复用的算子模板（如 `GENERATE_PLAN`, `DECOMPOSE_PROBLEM`, `GENERATE_ANSWER`, `REVIEW_SOLUTION`, `REFINE_ANSWER`, `GENERATE_CODE` 等）。
  - **阶段子图**：设计者为每一轮规划生成一个有向图 \( G_t = (V_t, E_t, v_t^{\text{start}}, C_t^{\text{end}}) \)，节点是算子实例，边表示依赖关系，入口点 `v_t^{\text{start}}`，终止条件 `C_t^{\text{end}}`。
  - **执行流程**：执行者按拓扑顺序执行算子实例，从全局内存缓冲区 \( M \) 中检索输入，将输出写回 \( M \)，并更新状态 \( s_{t+1} \)。
  - **设计者训练**：采用**两阶段训练**：先用监督微调（SFT）从成功轨迹中蒸馏，再用自博弈偏好优化（KTO）从自身生成轨迹中学习有效/无效计划。KTO避免了复杂的成对比较和在线奖励建模，利用轨迹级成功/失败标签。
  - **公式**（算法伪代码见原论文Algorithm 1）：
    - 设计者生成子图：\( G_t \sim \pi_\theta(\cdot \mid f_{\text{summary}}(s_t)) \)
    - SFT损失：\( \mathcal{L}_{\text{SFT}}(\theta) = -\mathbb{E}_{(s, G^{\text{expert}})} \left[ \log \pi_\theta(G^{\text{expert}} \mid f_{\text{summary}}(s)) \right] \)
    - KTO损失：\( \mathcal{L}_{\text{pref}}(\theta) = \mathbb{E}_{(s, G, l)} \left[ L_{\text{single}}^{\text{pref}}(p_\theta, p_{\text{ref}}, l; \beta) \right] \)

## 3. 实验设计：数据集、基准和对比方法

- **数据集**（5个领域，3个用于训练，2个用于零样本泛化测试）：
  - 逻辑推理：LiveBench
  - 数学推理：MATH（难度5级，4个类别）
  - 医学推理：PubMedQA
  - 代码推理：HumanEval（零样本）
  - 社交推理：SocialMaze（零样本，多轮博弈推理）
- **基准方法**：
  - 提示方法：Vanilla, Chain-of-Thought (CoT), Self-Consistency (SC), LLM-Debate, Self-Refine
  - 自动化智能体框架：ADAS, AFlow, MaAS
- **评价指标**：准确率（SocialMaze, PubMedQA, MATH, LiveBench）和 Pass@1（HumanEval），此外还报告了 Pass@k（k=1~5）曲线。

## 4. 资源与算力

- **训练资源**（附录D.2）：
  - GPU：2× Nvidia A6000
  - 设计者模型：Phi-4（14B开放权重），使用LoRA参数高效微调
  - SFT阶段：1.5k条成功子图样本，cutoff=2048，batch_size=1，梯度累积4步，学习率5e-6，余弦调度，bf16，3个epoch
  - KTO阶段：2k条自博弈样本（正负比1:1），cutoff=4096，batch_size=1，梯度累积8步，学习率2e-4，KL惩罚β=0.1，bf16，3个epoch
- **推理资源**：使用Phi-4作为执行者，温度0.01，设计者DyPlanner（同样基于Phi-4训练）。

## 5. 实验数量与充分性

- **主实验**（表1）：在5个数据集上对比8种基线，每个任务均有明确数值。
- **泛化分析**（表2、表3、图4）：
  - 跨设计者泛化：Claude-3.7-Sonnet、GPT-4.1、DyPlanner（轻量）对比
  - 跨执行者泛化：GPT-4o-mini、Phi-4、GPT-4.1-mini对比
  - 跨任务泛化：在3个训练域上训练，测试剩余2个域（多组组合）
- **消融实验**（表4）：去除SFT、去除KTO、去除动态算子、去除动态规划（一次性规划）
- **Pass@k曲线**（图3、图7）：k=1~5
- **算子使用频率分析**（图6）
- **成本分析**（表8、表9）：训练和推理的token消耗和美元成本
- **算例分析**（附录F）：多个具体任务（MATH、LiveBench、逻辑谜题、SocialMaze、代码解析）的逐步对比
- **充分性评价**：实验覆盖了不同模型规模、不同领域、不同泛化场景，消融完整，对比基线丰富（既有提示方法也有智能体框架）。但未报告统计显著性（误差条），作者在checklist中说明由于计算成本未提供，但认为趋势一致。

## 6. 论文的主要结论与发现

1. **DyFlow在5个推理域均显著优于所有基线**：平均准确率61.45%，比最强基线MaAS（57.74）高出约3.7个百分点，比Vanilla基线（53.44）高出8个百分点。
2. **强大的零样本泛化能力**：在未参与训练的HumanEval和SocialMaze上分别达到92.07%和17.18%，SocialMaze上比MaAS高出近4个百分点。
3. **P@k进一步提升**：DyFlow在P@5下HumanEval达98.17%，远高于CoT，表明推理稳定性和多样性更好。
4. **轻量设计者效果媲美大模型**：基于Phi-4训练的DyPlanner在多个任务上接近甚至超过GPT-4.1和Claude-3.7-Sonnet作为设计者的版本，且成本极低（总推理成本仅0.42美元 vs Claude的34.61美元）。
5. **跨执行者泛化**：DyFlow搭配不同执行者（GPT-4o-mini, Phi-4, GPT-4.1-mini）均能提升性能，尤其在弱模型上提升显著。
6. **消融实验证实各组件不可或缺**：去除动态规划导致性能下降最大（约5个百分点），去除KTO或SFT也各有1~3个百分点的损失。

## 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - **反馈驱动的动态规划**：将规划与执行紧密结合，实现子目标级实时调整，比仅调整角色或动作更具鲁棒性。
  - **两阶段训练策略**：SFT提供稳定初始化，KTO利用自博弈偏好信号有效优化，无需成对偏好或在线奖励，稳定且实用。
  - **轻量设计者**：通过蒸馏和偏好优化，使小型开源模型（Phi-4）获得接近闭源大模型的规划能力，降低部署成本。
  - **算子可复用、可配置**：10种算子模板支持多种推理场景，且可通过上下文参数化动态实例化。
- **实验亮点**：
  - **多维度泛化测试**：跨设计者、跨执行者、跨任务（零样本）三类泛化实验，全面验证框架适应性。
  - **成本-性能权衡分析**：明确报告了训练和推理的token消耗与美元成本，显示DyFlow在性价比上的优势。
  - **丰富的定性案例**：附录F提供了5个具体推理任务的完整运行轨迹对比，直观展示动态规划如何修正错误。

## 8. 不足与局限

- **外部工具集成缺失**（论文附录E）：当前算子集主要面向符号/文本推理，不支持搜索、数据库查询、环境交互等工具使用。尽管在评估任务中瓶颈主要是规划而非外部知识，但对更复杂的实际应用（如网页问答、具身推理）仍有限制。
- **实验统计显著性未报告**：主要结果未给出误差条或置信区间，可能受随机性影响，但文中已说明计算成本约束并提供了多维度一致趋势。
- **训练依赖强执行者生成轨迹**：SFT阶段需要从GPT-4等强模型蒸馏轨迹，增加了初始成本；但设计者一旦训练完成即可独立使用。
- **算子集有限**：当前仅10种算子，面对需要更细粒度甚至全新推理模态的任务（如多模态、连续决策）可能需要扩展。
- **未探索多智能体协作场景**：DyFlow当前为单个设计者+单个执行者的分层结构，未涉及多智能体动态组队或通信。
- **可能存在的偏差**：训练数据仅来自MATH、PubMedQA、LiveBench三个域，虽验证了零样本泛化，但更广泛域的性能仍需考察。

（完）
