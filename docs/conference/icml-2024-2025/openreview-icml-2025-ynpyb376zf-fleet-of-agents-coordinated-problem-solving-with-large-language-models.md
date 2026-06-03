---
title: "Fleet of Agents: Coordinated Problem Solving with Large Language Models"
title_zh: 智能体舰队：基于大语言模型的协同问题求解
authors: "Lars Henning Klein, Nearchos Potamitis, Roland Aydin, Robert West, Caglar Gulcehre, Akhil Arora"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yNpYb376zf"
tags: ["query:mas-routing"]
score: 8.0
evidence: 智能体舰队通过动态树搜索和遗传粒子滤波协调多个智能体，平衡成本与质量
tldr: 针对多智能体推理中成本与质量的权衡问题，本文提出Fleet of Agents（FoA）框架。它利用LLM作为智能体，通过遗传粒子滤波方法进行动态树搜索，生成大量智能体自主探索，并根据启发式价值函数重采样以平衡探索与利用。该方法在多个推理任务上实现了成本与质量的优化。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 792, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1249, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1757, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 1312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1433, \"height\": 1185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1186, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1185, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1189, \"height\": 1189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1761, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ynpyb376zf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1758, \"height\": 578, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1020, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1749, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 905, \"height\": 1609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 907, \"height\": 1417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1259, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 904, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ynpyb376zf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1237, \"height\": 199, \"label\": \"Table\"}]"
motivation: 现有方法难以有效平衡多智能体推理的成本与质量。
method: 提出FoA框架，利用遗传粒子滤波实现多智能体动态树搜索和自适应分支。
result: 在多个基准上，FoA在相同预算下获得更高质量的解决方案。
conclusion: 这种动态多智能体协调方法为路由策略提供了实用框架。
---

## Abstract
While numerous frameworks have been developed to enhance the reasoning abilities of large language models (LLMs), there is a scarcity of methods that effectively balance the trade-off between cost and quality. 
In this paper, we introduce Fleet of Agents (FoA), a novel and intuitive yet principled framework utilizing LLMs as agents to navigate through dynamic tree searches, employing a genetic-type particle filtering approach. 
FoA spawns a multitude of agents, each exploring the search space autonomously, followed by a selection phase where resampling based on a heuristic value function optimizes the balance between exploration and exploitation. 
This mechanism enables dynamic branching, adapting the exploration strategy based on discovered solutions. 
We conduct extensive experiments on four benchmark tasks, \``Game of 24\'', \``Mini-Crosswords\'', \``WebShop\'' and \``SciBench\'', utilizing four different LLMs, GPT-3.5, GPT-4, LLaMA3.2-11B, and LLaMA3.2-90B. 
On average across all tasks and LLMs, FoA obtains an absolute quality improvement of $\simeq 5\%$ while requiring only $\simeq 35\%$ of the cost of previous SOTA methods. Notably, our analyses reveal that (1) FoA achieves the best cost-quality trade-off among all benchmarked methods, and (2) FoA+ LLaMA3.2-11B surpasses the Llama3.2-90B model. FoA is publicly available at [https://github.com/au-clan/FoA](https://github.com/au-clan/FoA).

---

## 论文详细总结（自动生成）

# 论文《Fleet of Agents: Coordinated Problem Solving with Large Language Models》中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有LLM推理框架在**成本**与**质量**之间难以取得良好平衡。单查询方法（如IO、CoT）成本低但成功率极低；多查询方法（如ToT、GoT、LATS）质量高但成本高昂，且无法动态调节搜索策略。
- **研究动机**：需要一种既能保持高质量又能控制成本的通用推理框架，尤其适用于需要与环境交互的序列决策任务（如Web导航）。
- **整体含义**：通过引入**遗传型粒子滤波**思想，协调多个LLM agent进行协同搜索，实现探索与利用的动态平衡，从而在有限资源下获得更优的推理性能。

## 2. 论文提出的方法论
- **核心思想**：将多个LLM agent看作粒子，在搜索空间中进行**变异-选择**循环。
    - **变异阶段**：每个agent独立探索搜索空间，执行k步动作，生成新的状态。
    - **选择阶段**：基于启发式价值函数对当前所有agent状态进行**重采样**（带替换），高价值状态被复制，低价值状态被淘汰，从而动态调整搜索方向（动态分支）。
- **关键技术细节**：
    - **强制变异**：agent不能停留在原状态，必须尝试新动作。
    - **突然死亡**：无效状态（如无效解）的agent被删除，随机复制一个其他agent填补。
    - **回溯机制**：允许从历史状态中重采样，引入折扣因子γ（γ∈[0,1]）避免过早陷入局部最优。
    - **重采样方案**：支持线性、指数、贪婪等多种加权方式。
    - **缓存与批处理**：减少重复LLM调用，进一步降低成本。
- **算法流程**：
    1. 初始化N个agent，每个agent处于初始状态。
    2. 循环：
        - **Mutation Phase**：每个agent独立执行k步动作，更新状态；处理终端状态（突然死亡）。
        - **Selection Phase**：计算每个agent当前状态的价值，根据价值分布进行重采样，得到新的agent群体。
        - 若找到解或达到预算，终止。
- **关键区别**：与ToT等固定分支因子方法不同，FoA的**分支因子是动态的**（通过重采样自动调节），更具灵活性和效率。

## 3. 实验设计
- **数据集与场景**：
    - **Game of 24**：数学谜题，1362个题目，测试集100题（901-1000）。评价指标：成功率。
    - **Mini Crosswords**：5×5填字游戏，156个谜题，测试集20个。评价指标：字母重叠率。
    - **WebShop**：模拟电商网站导航，12087个子任务，测试集50个。评价指标：平均得分（属性匹配度）。
    - **SciBench**：科学推理（物理、化学、生物），600+问题，每领域取15%验证，85%测试。评价指标：准确率。
- **基准模型**：GPT-4（主要），GPT-3.5、LLaMA3.2-11B、LLaMA3.2-90B（泛化性验证）。
- **对比方法**：
    - 单查询：IO、CoT、CoT-SC、AoT。
    - 多查询：ToT、GoT、RAFA、ReST-MCTS*、LATS。
    - 特殊：WebShop中还包括监督/强化学习模型（IL、IL+RL、WebGUM）和人类专家。
- **公平性保障**：直接复用对比方法的prompt（如ToT的提示词），避免因提示工程差异导致不公。

## 4. 资源与算力
- **算力说明**：论文未明确提及使用的GPU型号、数量或训练时长。所有实验均通过**API调用**完成（OpenAI GPT系列，TogetherAI的LLaMA系列），属于推理阶段计算，不涉及模型训练。
- **成本度量**：以**美元计费**，依据API定价（如GPT-4: $30/1M输入tokens, $60/1M输出tokens）。实验成本在文中表格中直接列出（例如Game of 24: GPT-4下FoA花费$62.93, ToT花费$75.02）。

## 5. 实验数量与充分性
- **实验数量**：
    - 主实验：4个任务 × 4个LLM × 多个基线（每个任务至少5种方法），总计上百组实验。
    - 消融实验：在Game of 24上对**5个组件**（Selection phase、Resampling、Backtracking、Caching、Batching）分别进行去除测试，并使用3种LLM验证。
    - 模型分析：成本-质量折衷图、模型规模-质量对比、与SOTA方法在不同预算下的表现。
- **充分性评估**：
    - **充分**：覆盖了多种推理类型（数学、语言、交互、科学）、多种模型规模、多个消融角度。
    - **客观公平**：统一使用原文prompt，控制成本统计口径，多次运行（GPT-4除外）并报告均值/std。
    - **不足**：部分任务（WebShop/SciBench）仅用GPT-3.5，未用GPT-4；WebShop未运行所有基线（如LATS因成本过高只用GPT-3.5）；某些方法因代码或资源不可用而未比较（如BoT、RAP）。

## 6. 论文的主要结论与发现
- **核心结论**：
    - FoA在**所有任务和所有LLM上均取得最优质量**，同时成本显著低于SOTA方法。
    - 平均质量提升约**5%**，成本仅为SOTA方法的**约35%**。
    - FoA实现**最佳成本-质量折衷**，在所有价格点下均优于ToT、GoT、RAFA、ReST-MCTS*等。
    - **FoA + LLaMA3.2-11B 性能超过 LLaMA3.2-90B**，说明FoA可显著增强小模型能力。
- **其他发现**：
    - 消融实验表明每个组件（选择、重采样、回溯、缓存、批处理）都对最终性能有正面贡献。
    - 动态分支机制比固定分支因子更灵活高效。

## 7. 优点
- **方法创新性**：首次将**遗传型粒子滤波**引入LLM agent协调，在推理框架中实现动态搜索广度控制。
- **即插即用**：FoA是**运行时（runtime）**而非提示方案，可直接集成任何现有agent，无需修改其行为。
- **可控性**：可精确指定agent数量N和步数k，从而预测和限制延迟与成本。
- **实验设计严谨**：重用其他方法prompt，控制变量；跨多个模型、多个任务验证；包含充分消融。
- **实用性**：开源代码，成本明确，易于复现和扩展。

## 8. 不足与局限
- **固定舰队规模**：当前为每个任务分配固定数量agent，未根据难度自适应调整。
- **价值函数简单**：仅使用启发式LLM评估，未利用历史信息或相邻状态平滑，可能导致估值噪声。
- **同质agent**：所有agent行为相同，未引入层次化或异构结构（如专家agent）。
- **部分任务模型局限**：WebShop和SciBench仅用GPT-3.5测试，未验证在更强模型（GPT-4）下的表现。
- **成本统计局限**：仅基于API价格，未考虑本地部署、延迟等其他成本。
- **基线覆盖不足**：部分SOTA方法（如BoT、RAP、TouT）因代码/资源不可用而未比较。
- **泛化性验证有限**：仅在四个任务上测试，未涉及更复杂长对话或实时决策场景。

（完）
