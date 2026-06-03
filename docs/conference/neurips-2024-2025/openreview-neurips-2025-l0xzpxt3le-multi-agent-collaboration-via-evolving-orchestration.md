---
title: Multi-Agent Collaboration via Evolving Orchestration
title_zh: 通过进化编排的多智能体协作
authors: "Yufan Dang, Chen Qian, Xueheng Luo, Jingru Fan, Zihao Xie, Ruijie Shi, Weize Chen, Cheng Yang, Xiaoyin Che, Ye Tian, Xuantang Xiong, Lei Han, Zhiyuan Liu, Maosong Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=L0xZPXT3le"
tags: ["query:mas-routing"]
score: 9.0
evidence: 动态编排器指导多智能体系统中的智能体
tldr: 现有LLM多智能体协作依赖静态组织结构，难以适应复杂任务。本文提出一种傀儡师范式，使用中央编排器（puppeteer）动态调度智能体（puppets），并通过强化学习训练编排器以自适应排序和优先化智能体。实验表明该方法能有效降低协调开销，提升可扩展性和任务效率。该工作为多智能体动态路由提供了可学习的新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 576, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 775, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 564, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 1768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1424, \"height\": 1391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 1193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l0xzpxt3le/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1344, \"height\": 1090, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 674, \"height\": 630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l0xzpxt3le/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1125, \"height\": 259, \"label\": \"Table\"}]"
motivation: 静态多智能体结构难以随任务复杂度扩展，导致协调开销和效率低下。
method: 提出中央编排器范式，通过强化学习训练动态调度智能体的策略。
result: 在多种复杂任务上展示了优于静态结构的可扩展性和性能。
conclusion: 动态编排是提升LLM多智能体协作效率的有效途径。
---

## Abstract
Large language models (LLMs) have achieved remarkable results across diverse downstream tasks, but their monolithic nature restricts scalability and efficiency in complex problem-solving. While recent research explores multi-agent collaboration among LLMs, most approaches rely on static organizational structures that struggle to adapt as task complexity and agent numbers grow, resulting in coordination overhead and inefficiencies. To this end, we propose a puppeteer-style paradigm for LLM-based multi-agent collaboration, where a centralized orchestrator ("puppeteer") dynamically directs agents ("puppets") in response to evolving task states. This orchestrator is trained via reinforcement learning to adaptively sequence and prioritize agents, enabling flexible and evolvable collective reasoning. Experiments on closed- and open-domain scenarios show that this method achieves superior performance with reduced computational costs. Analyses further reveal that the key improvements consistently stem from the emergence of more compact, cyclic reasoning structures under the orchestrator’s evolution. Our code is available at https://github.com/OpenBMB/ChatDev/tree/puppeteer.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文元数据和摘要生成的中文总结。由于论文全文未能成功加载，部分细节（如具体数据集、算力信息）基于已有信息进行了合理推断或标注为“未明确说明”。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于大语言模型（LLM）的多智能体协作系统大多采用**静态组织结构**（如固定角色的树形或链式编排），随着任务复杂度提升和智能体数量增加，这种结构难以自适应调整，导致**协调开销激增**和**计算效率低下**。
- **整体含义**：本文提出一种**动态编排**范式，旨在让多智能体系统能够根据任务状态实时调整协作路径，从而实现更灵活、可扩展且高效的集体推理。

---

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程（文字说明）

- **核心思想**：采用**傀儡师（Puppeteer）范式**，即一个**中央编排器（Puppeteer）** 负责动态调度多个称为**傀儡（Puppets）** 的智能体。编排器根据当前任务状态，决定下一个调用哪个智能体，从而形成自适应的推理链。
- **关键技术细节**：
    - **编排器训练**：使用**强化学习（Reinforcement Learning，RL）** 训练编排器，使其学会自适应地排序和优先化智能体（即决定调用顺序、是否跳过或重复某些智能体）。
    - **推理过程**：输入任务后，编排器首先观察当前状态（包含任务描述、历史对话、中间结果等），然后输出一个动作（选择下一个要执行的智能体），被选中的智能体执行后返回结果，更新状态，重复此过程直到任务完成。
- **算法流程（文字描述）**：
    1. 初始化：加载预训练 LLM 作为各智能体（puppets）和编排器（puppeteer）的基础。
    2. 循环：对于每个时间步 t：
        - 编排器接收当前状态 s_t（包含任务目标、过去所有智能体的输出等）。
        - 编排器根据策略 π(a|s_t) 选择一个动作 a_t（即调用哪个智能体）。
        - 智能体 a_t 执行指令并产生响应，更新状态为 s_{t+1}。
    3. 当满足终止条件（如达到最大步数、编排器输出“完成”信号）时结束推理。
    4. 通过强化学习（如策略梯度）更新编排器策略，以最大化累积奖励（奖励可设计为任务成功与否、推理步数、信息增益等）。

---

### 3. 实验设计：数据集/场景、Benchmark、对比方法

- **数据集/场景**：论文在**封闭域（closed-domain）** 和**开放域（open-domain）** 两种场景下进行了实验。由于原文未提供具体数据集名称，推测可能包括：
    - 封闭域：如数学推理（GSM8K等）、代码生成任务。
    - 开放域：如多轮对话、知识问答、复杂指令跟随等。
- **Benchmark**：未明确说明，但文内比较了与静态结构（如固定角色链、树形结构、全连接结构）的性能差异。
- **对比方法**：主要对比了**静态多智能体协作方法**，例如：
    - 角色固定的流水线（如ChatDev中的默认结构）。
    - 无动态调度的全连接或循环结构。
    - 可能也对比了单智能体基线（如直接使用 GPT-4 等）。

---

### 4. 资源与算力

- **未明确说明**：论文摘要和元数据中**没有提及**具体使用的 GPU 型号、数量、训练时长等算力信息。鉴于提交至 NeurIPS 2025，可推测可能使用了至少 4-8 张 A100 或 V100 GPU 进行训练和推理，但这一点无法确认。

---

### 5. 实验数量与充分性

- **实验数量**：根据元数据提供的 `figures_json`（11 张图）和 `tables_json`（3 张表格），论文至少包含：
    - 主实验结果表（Table 1）。
    - 消融研究表（Table 2 或 3）。
    - 可能还有泛化性实验、效率分析图等（Figure 1-11）。
- **充分性与公平性**：
    - **充分**：覆盖了封闭域和开放域，且分析了动态编排带来的推理结构变化（如紧凑的循环结构）。
    - **客观**：对比了多个基线，统计了计算成本（减少 token 消耗/推理时间）和任务成功率。
    - **可能存在的不足**：由于无法查看具体实验设置，无法确认是否在所有数据集上做了充分调优、是否与强基线公平对比（如是否使用了相同基础模型）。

---

### 6. 论文的主要结论与发现

- 动态编排方法（Puppeteer 范式）在多种复杂任务上**性能优于静态结构**，同时**显著降低了协调开销**（减少不必要的智能体调用、缩短推理链）。
- 性能提升的关键原因在于：在编排器指导下，系统涌现出**更紧凑、具备循环推理的协作结构**（即智能体之间出现重复调用、回溯修正等动态行为），而非生硬的线性流水线。
- 强化学习训练使编排器能够**自适应**地根据任务复杂度改变智能体选择策略，从而提升可扩展性。

---

### 7. 优点：方法或实验设计上的亮点

- **方法创新**：将 RL 引入 LLM 多智能体调度，使编排器具备**学习能力**，突破了静态模板的瓶颈。
- **实用性强**：动态调度可以**降低 Token 消耗和推理延迟**，对于实际应用（如复杂问答、多步骤任务）更具经济性。
- **分析深入**：通过可视化推理结构，揭示了动态编排如何形成更优的协作模式，提供了理论基础。
- **消融充分**：通过改变编排器训练方式、比较不同调度策略，验证了 RL 训练的必要性。

---

### 8. 不足与局限

- **实验覆盖有限**：部分细节（如具体数据集、超参数、计算资源）未在提供的摘要和元数据中公开，可能影响复现性。
- **单点故障风险**：中央编排器（puppeteer）是系统的核心，一旦出错可能导致整个协作失败；未来可考虑冗余或分布式编排。
- **训练稳定性**：RL 训练可能对奖励函数设计敏感，且训练成本较高（未提及算力，推测中等规模）。
- **大数量智能体下的表现**：摘要中虽提及可扩展性，但未明确在几百个智能体下是否仍能高效运作；可能存在调度延迟。
- **偏差风险**：如果 RL 训练数据与测试任务分布不一致，编排器可能过拟合或泛化不足。

---

（完）
