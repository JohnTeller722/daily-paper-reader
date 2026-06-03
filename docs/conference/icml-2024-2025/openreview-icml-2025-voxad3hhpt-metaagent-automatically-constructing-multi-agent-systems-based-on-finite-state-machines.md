---
title: "MetaAgent: Automatically Constructing Multi-Agent Systems Based on Finite State Machines"
title_zh: MetaAgent：基于有限状态机自动构建多智能体系统
authors: "Yaolun Zhang, Xiaogeng Liu, Chaowei Xiao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vOxaD3hhPt"
tags: ["query:mas-routing"]
score: 7.0
evidence: 基于有限状态机自动构建多智能体系统
tldr: 该论文提出MetaAgent框架，基于有限状态机自动构建多智能体系统。给定任务描述后，MetaAgent能设计智能体结构并优化其通信路由，无需人工预定义。实验表明该方法在多种任务上生成了高效的多智能体系统，实现了动态任务分配和路由，直接服务于多智能体路由研究。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1743, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1702, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1813, \"height\": 2157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1821, \"height\": 1895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1820, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1828, \"height\": 1394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1810, \"height\": 889, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1555, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1606, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 808, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 941, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 586, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 409, \"height\": 205, \"label\": \"Table\"}]"
motivation: 现有手动设计多智能体框架局限于预定场景，且自动构造方法缺乏灵活路由。
method: 使用有限状态机建模智能体行为，通过优化算法自动生成和调整路由。
result: 生成的多智能体系统在多个基准任务上性能优于手工设计。
conclusion: 自动构建多智能体系统可有效支持动态路由和任务分配。
---

## Abstract
Large Language Models (LLMs) have demonstrated the ability to solve a wide range of practical tasks within multi-agent systems. However, existing human-designed multi-agent frameworks are typically limited to a small set of pre-defined scenarios, while current automated design methods suffer from several limitations, such as the lack of tool integration, dependence on external training data, and rigid communication structures. In this paper, we propose \textbf{MetaAgent}, a  \textbf{finite state machine} based framework that can automatically generate a multi-agent system. Given a task description, MetaAgent will design a multi-agent system and polish it through an optimization algorithm. When the multi-agent system is deployed, the finite state machine will control the agent's actions and the state transitions. To evaluate our framework, we conduct experiments on both text-based tasks and practical tasks. The results indicate that the generated multi-agent system surpasses other auto-designed methods and can achieve a comparable performance with the human-designed multi-agent system, which is optimized for those specific tasks.

---

## 论文详细总结（自动生成）

# 论文总结：MetaAgent: 基于有限状态机自动构建多智能体系统

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的大语言模型（LLM）多智能体系统大多由人工设计，局限于少数预设场景（如软件开发、数据科学），设计成本高且缺乏泛化能力。自动构建多智能体系统的方法存在多个缺陷：缺乏工具集成、依赖外部训练数据、通信结构僵化（线性、固定辩论或中心化编排），不具备回溯（traceback）和空转移（null-transition）的能力，无法灵活处理错误和未知情况。
- **整体含义**：论文旨在提出一种能够自动生成多智能体系统的框架，该框架基于有限状态机（FSM）建模智能体行为与通信路由，能够在给定任务描述后自动设计智能体角色、状态转换和优化流程，无需人工预定义，且支持工具使用（代码解释器、搜索引擎）和动态回溯。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将多智能体系统建模为一个**有限状态机（FSM）**，其中每个状态代表任务求解过程中的一个子任务或情况，包含：
  - 一个**任务求解智能体**（agent）
  - 一个**条件验证器**（condition verifier），用于检查输出是否满足预定义的自然语言转换条件
  - 一个**状态指令**（instruction）
  - **监听器列表**（listeners），指定输出信息传递给哪些其他智能体
- **自动构建过程**（两阶段）：
  1. **智能体设计**：给定通用任务描述，设计器LLM生成任务分析和系统目标，然后设计最简智能体集合（名称、系统提示、工具列表），以JSON格式输出。
  2. **状态与转换设计**：设计器LLM基于智能体和任务描述，设计FSM的状态集和自然语言转换条件（包括前向、回溯、空转移）。每个状态有目标智能体、指令、监听器；条件验证器根据智能体输出判断是否满足转换条件，若不满足则触发空转移（允许当前智能体多轮迭代），若满足则转移到目标状态（可回溯到之前状态）。
- **优化算法**：初始FSM可能状态过多、冗余，因此采用迭代合并算法：
  - 对状态集合S中的每对状态，调用LLM判断是否可合并（基于角色区分度、信息传递必要性、工具分配重叠）。
  - 若可合并，则将两个状态及其对应智能体合并，更新状态集，重复直到无合并可能。此过程无需外部数据和大量迭代（与ADAS等不同）。
- **部署阶段**：从初始状态开始，用户查询和状态指令输入给任务求解智能体，其输出由条件验证器评估，决定是空转移（反馈并留在当前状态）还是转移到下一个状态，同时将输出存入监听器内存。若达到最终状态或超过最大转移次数，任务结束。
- **FSM的泛化性**：论文论证了现有的线性结构、去中心化辩论、带编排者的协作结构都是FSM的特化版本（缺乏空转移或有限回溯），而FSM提供最大灵活性。

## 3. 实验设计

- **数据集/场景**：
  - **文本任务**：Trivial Creative Writing（100个题目，需写故事包含所有答案）、GPQA(Diamond)（198个研究生级科学选择题）。
  - **实用任务**：Machine Learning Bench（ML Bench, 5个数据集：Titanic, House Prices, SCTP, ICR, SVPC），Software Development（5个软件：2048游戏、贪吃蛇、打砖块、Excel应用、天气应用，每个有4个客观检查点）。
- **基准对比方法**：
  - 文本任务：Direct, CoT, CoT-SC, llm-debate, Self-Refine, SPP。
  - ML Bench：AutoGen, Open Interpreter, TaskWeaver, MetaGPT, DataInterpreter（均为人类设计），以及SPP、AutoAgents（自动设计）。
  - 软件开发：MetaGPT（人类设计），AutoAgents, SPP（自动设计）。
- **评估指标**：
  - 文本任务：成功率（Trivial Creative Writing中答案覆盖率；GPQA中正确率）。
  - ML Bench：归一化性能得分（NPS），基于F1、准确率或RMSE等指标。
  - 软件开发：通过检查点的比率（每个软件4个测试点）。
- **基础模型**：主实验使用GPT-4o，温度0以保证可重复性。工具池包括代码解释器和搜索引擎。

## 4. 资源与算力

- **论文未明确报告具体的GPU型号、数量或训练时长**。文中仅提到使用GPT-4o作为基础模型（通过API调用），设计阶段和部署阶段均调用LLM，无独立训练过程。成本分析仅统计了token消耗（例如，5个ML任务总token：设计阶段约6,226，部署阶段约39,663；6个软件任务总token：设计阶段约5,378，部署阶段约42,374）。因此，论文主要依赖商业API，未涉及自有算力投入。

## 5. 实验数量与充分性

- **实验组数**：
  - 文本任务：2个数据集×多种基线（7种对比方法）+ MetaAgent（共8种方法）。
  - ML Bench：5个数据集×8种方法（包括人类设计和自动设计）+ MetaAgent。
  - 软件开发：5个任务×4种方法（MetaGPT, AutoAgents, SPP, MetaAgent）。
  - 消融实验：在ML Bench、软件开发、文本任务上分别对工具使用、优化、回溯进行去除实验（共3组消融，每组含4个任务维度）。
  - 基础模型质量实验：在ML Bench上替换设计器/执行器为GPT-3.5-Turbo，共4种组合。
  - 成本分析：统计了两类任务的总token消耗。
- **充分性评估**：
  - 实验覆盖了多种任务类型（文本生成、问答、机器学习、软件开发），且对比了多种当前最好的自动设计和人类设计系统，比较全面。
  - 消融实验验证了关键组件的重要性，基础模型实验分析了设计器与执行器的影响。
  - 不足：未在更大规模或更多任务上验证（如多轮交互、复杂推理任务）；未评估不同LLM后端的鲁棒性（仅使用GPT-4o和GPT-3.5）；未报告统计显著性检验或多次运行的方差（温度设为0但LLM输出仍有随机性）。总体较为充分，但可进一步提升客观性。

## 6. 主要结论与发现

- MetaAgent生成的多智能体系统在文本任务上超越所有自动设计方法（写作0.86 vs SPP 0.79，GPQA 0.60 vs 最佳基线llm-debate 0.54）。
- 在ML Bench上，MetaAgent平均NPS为0.83，仅次于专门为ML任务设计的人类系统DataInterpreter（0.86），优于所有其他人类设计和自动设计系统（包括MetaGPT、AutoGen等）。
- 在软件开发任务上，MetaAgent平均通过率0.85，显著优于MetaGPT（0.35）、AutoAgents（0.20）、SPP（0.15）。
- 消融实验表明：去除工具使用导致写作和GPQA分别下降8.1%和13.3%；去除优化导致ML Bench下降26.5%、软件开发下降35.3%；去除回溯导致ML Bench下降13.3%、软件开发下降58.8%。说明工具、优化、回溯均至关重要。
- 基础模型质量：执行器使用GPT-4o比设计器使用GPT-4o更重要（性能下降更多）。
- 成本分析显示，MetaAgent的总token消耗低于AutoAgents和MetaGPT，在自动设计方法中具有成本优势。

## 7. 优点

- **自动化程度高**：仅需任务描述，即可自动生成完整的多智能体系统，无需人工调参或预定义路由。
- **灵活的路由机制**：FSM支持空转移（多轮迭代）和状态回溯（错误修复），比现有线性/固定结构更适合复杂任务。
- **工具集成**：自动为智能体分配代码解释器和搜索引擎，增强实际应用能力。
- **无需外部数据**：优化算法只需LLM判断合并性，不依赖额外训练数据或大量迭代。
- **统一理论框架**：证明现有各类多智能体结构均为FSM的特例，提供了一般化视角。
- **实验设计全面**：覆盖文本、机器学习、软件开发三大类任务，对比多种基线，并有详尽的消融和成本分析。

## 8. 不足与局限

- **依赖LLM能力**：设计器和执行器均依赖GPT-4o级别模型。当使用较弱模型（GPT-3.5）时性能大幅下降，限制了在弱模型上的适用性。
- **未处理状态爆炸**：优化算法基于LLM判断合并性，可能无法保证全局最优，且对状态数量较大的任务可能效率低。
- **实验可重复性**：温度设为0，但LLM输出仍有随机性，未报告多次实验结果的标准差，难以评估结果的稳定性。
- **任务覆盖有限**：未测试需要长期计划或大量交互的现实任务（如机器人控制、多轮对话），也未评估对未见任务类型的泛化能力。
- **安全性/鲁棒性考量**：论文未讨论FSM设计可能产生的安全风险（如智能体滥用工具、错误传播），也未进行对抗性测试。
- **对比公平性**：部分基线（如SPP、AutoAgents）未适配工具，导致在实用任务上表现差，可能未能充分反映其潜力。MetaAgent使用的工具（代码解释器）提升了代码执行能力，其他方法可能因缺乏此能力而处于劣势。
- **论文未公开所有实验细节**：例如每个任务的具体检查点设计（仅附录B简略描述）、ML Bench的NPS计算方式、多次运行的成本波动等，可复现性有限。

（完）
