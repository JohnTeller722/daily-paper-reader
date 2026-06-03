---
title: Long-Horizon Planning for Multi-Agent Robots in Partially Observable Environments
title_zh: 部分可观察环境下的多智能体机器人长期规划
authors: "Siddharth Nayak, Adelmo Morrison Orozco, Marina Ten Have, Jackson Zhang, Vittal Thirumalai, Darren Chen, Aditya Kapoor, Eric Robinson, Karthik Gopalakrishnan, James Harrison, Anuj Mahajan, brian ichter, Hamsa Balakrishnan"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=Y1rOWS2Z4i"
tags: ["query:mas-routing"]
score: 5.0
evidence: 基于语言模型的多机器人长期规划，适用于部分可观察环境
tldr: LLaMAR提出了一种基于语言模型的多智能体机器人长期规划认知架构，在部分可观察环境中实现了最先进的结果。该方法利用语言模型理解自然语言指令并分解任务，通过多智能体协调完成长期目标，对多智能体任务分配和协调具有借鉴意义。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1392, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1403, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-y1rows2z4i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1323, \"height\": 851, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1233, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1049, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 652, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1041, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1484, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1826, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-y1rows2z4i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 861, \"height\": 509, \"label\": \"Table\"}]"
motivation: 语言模型在部分可观察多智能体场景中面临长期规划挑战。
method: 提出LLaMAR认知架构，基于语言模型进行多智能体长期任务规划，处理部分可观察性。
result: 在多个机器人任务中取得最优性能，验证了语言模型在多智能体规划中的有效性。
conclusion: LLaMAR展示了语言模型在复杂多智能体规划中的潜力，促进了自主机器人系统的进步。
---

## Abstract
The ability of Language Models (LMs) to understand natural language makes them a powerful tool for parsing human instructions into task plans for autonomous robots. Unlike traditional planning methods that rely on domain-specific knowledge and handcrafted rules, LMs generalize from diverse data and adapt to various tasks with minimal tuning, acting as a compressed knowledge base. However, LMs in their standard form face challenges with long-horizon tasks, particularly in partially observable multi-agent settings. We propose an LM-based Long-Horizon Planner for Multi-Agent Robotics (LLaMAR), a cognitive architecture for planning that achieves state-of-the-art results in long-horizon tasks within partially observable environments. LLaMAR employs a plan-act-correct-verify framework, allowing self-correction from action execution feedback without relying on oracles or simulators. Additionally, we present MAP-THOR, a comprehensive test suite encompassing household tasks of varying complexity within the AI2-THOR environment. Experiments show that LLaMAR achieves a 30\% higher success rate than other state-of-the-art LM-based multi-agent planners in MAP-THOR and Search \& Rescue tasks. Code can be found at [https://github.com/nsidn98/LLaMAR](https://github.com/nsidn98/LLaMAR)

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：语言模型（LM）在标准形式下难以处理长期（long-horizon）任务，特别是在**部分可观察的多智能体环境**中。传统规划方法依赖领域知识与手工规则，泛化能力弱；而LM虽能从多样化数据中学习、适应多种任务，但在长期规划中面临环境非平稳性、智能体间协调困难等挑战。
- **研究动机**：开发一种能够利用LM理解自然语言指令、自动分解为可行子任务，并支持多智能体协作完成长期目标的认知架构，无需依赖特权信息（如全局地图或模拟器反馈），从而更接近真实世界的自主机器人部署。
- **整体含义**：该论文提出了**LLaMAR**（一种基于LM的长期规划多智能体机器人框架），采用**计划-行动-纠正-验证**循环，在部分可观察动态环境中实现了当前最先进的性能，并提供了标准化的测试套件**MAP-THOR**，为多智能体规划研究提供了新的基准与思路。

---

### 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：将LM作为认知架构的核心，通过四个专用模块（Planner、Actor、Corrector、Verifier）实现端到端的多智能体规划与执行，每一步都结合实时观察与执行反馈，实现自纠正与自验证。
- **关键技术细节**：
  - **Planner模块**：根据当前观察、记忆及已完成/开放的子任务，生成或更新**开放子任务集**（`GO`），如“将番茄运到冰箱”。
  - **Actor模块**：结合纠正模块输出的**纠正动作**（`ac`），为每个智能体生成当前决策步的**高层面动作**（如导航、拾取、放置等），并更新联合记忆。
  - **Corrector模块**：基于上一步行动的**执行反馈**（成功/失败），分析失败原因并建议**纠正性高层面动作**（如“先靠近物体再拾取”）。
  - **Verifier模块**：通过观察执行结果，判断哪些子任务已完成，将其从开放子任务移至已完成子任务集（`GC`），无需依赖模拟器或 oracle。
  - **探索策略**：当任务所需对象不可见时，使用CLIP嵌入计算**探索得分**，选择与开放子任务语义匹配度最高的方向进行探索（算法1）。
  - **动作解析**：利用微调的SentenceBERT将LM的自由文本输出映射为可执行的高层面动作。
- **算法流程**（伪代码）：
  1. 初始化记忆、开放/已完成子任务、动作、纠正动作为空。
  2. 循环（最多T步）：
     - 采集所有智能体的联合观察图像 → Planner模块更新开放子任务。
     - Actor模块结合纠正动作和观察，生成各智能体的高层面动作。
     - 在环境中同步执行动作，获得执行反馈。
     - Corrector模块分析失败原因，输出纠正动作。
     - Verifier模块根据执行结果更新已完成子任务。
     - 若开放子任务集为空则终止。
  3. 输出最终任务完成状态。

---

### 3. 实验设计：数据集、基准、对比方法

- **数据集/场景**：
  - **MAP-THOR**：基于AI2-THOR模拟器的多智能体家庭环境任务套件，共**45个任务**，每个任务在**5种不同房间布局**上测试。任务按语言指令模糊度分为4类（明确物品种类/数量/目标、隐含数量、隐含物品种类、完全隐含）。
  - **Search & Rescue (SAR)**：自定义的搜索救援网格环境，包含火灾（不同类别和扩散）与被困人员，需要智能体合作灭火和救人。
- **基准方法**：
  - Act、ReAct、Chain-of-Thought（CoT）、SmartLLM（修改为部分可观察）、CoELA（修改为不使用oracle）。
  - 所有方法均使用GPT-4V作为基础LM，便于公平比较。
- **评价指标**：
  - **Success Rate (SR)**：全部子任务完成的成功率。
  - **Transport Rate (TR)**：已完成的子任务比例。
  - **Coverage (C)**：与目标对象交互的成功率。
  - **Balance (B)**：各智能体贡献的均匀度。
  - **Average Steps (L)**：完成任务的决策步数（上限30步）。

---

### 4. 资源与算力

- 论文中**未明确说明**主要实验所使用的GPU型号、数量及总训练时长。所有基于GPT-4V的查询均通过OpenAI API调用完成，成本较高。
- 文中仅提及**SentenceBERT微调**部分：在1个Apple M1核心上运行约5分钟，使用2800条训练样本，10个epoch，学习率2×10⁻⁵，批量大小64。
- 由于主要依赖商业API和预训练模型，实验的算力消耗主要体现为API调用的计算时间与费用；文中提及每个决策步需要查询4个LM模块，因此计算开销高于其他对比方法。

---

### 5. 实验数量与充分性

- **实验数量**：
  - **MAP-THOR 2-agent实验**：对比5种基线（Act、ReAct、CoT、SmartLLM、CoELA），报告各指标的均值与95%置信区间（表2）。
  - **消融实验**：移除LLaMAR各模块（Actor alone、Planner+Actor+Verifier、Planner+Actor+Corrector+Oracle、完整LLaMAR）（表3）。
  - **不同智能体数量（1-5）**：在MAP-THOR和SAR环境上测试（表4）。
  - **不同底层LM**：GPT-4V、GPT-4、LLaVA、IDEFICS-2、CogVLM（表2）。
  - **SAR环境实验**：独立的实验设置与结果（表4）。
  - **失败案例分析**：给出了Mis-generalization、相互干扰、探索不足等典型失败模式，并提供图示。
- **充分性与公平性**：
  - 基线均被修改为适用于部分可观察设定，提示词亦保持一致格式，避免因提示差异导致的偏差。
  - 所有指标报告置信区间，结果统计显著。
  - 消融实验系统性地验证了每个模块的必要性。
  - 在不同房间布局、不同任务难度上测试，增强了鲁棒性评估。
  - **潜在偏差**：所有实验仅在两种仿真环境（AI2-THOR和SAR）中进行，未涉及真实物理机器人；且GPT-4V作为主要基础LM，可能限制了通用性结论。

---

### 6. 论文的主要结论与发现

- **LLaMAR在MAP-THOR上以GPT-4V为基础时，SR达到0.66，较最佳基线（ReAct的0.34）提升约97%**（实质是33%→66%，提升30个百分点，文中表述“30% higher success rate”指相对提升约94%）。
- **模块化架构关键**：去除Planner、Corrector或Verifier任一模块均导致性能显著下降；其中Corrector模块对于从执行失败中恢复至关重要。
- **增加智能体数量**：在MAP-THOR中，从2个增加到3个时SR提升，但4-5个时因拥堵略有下降；而在更宽敞的SAR环境中，SR持续上升至0.74（5-agent）。但平衡性（B）随智能体增多而下降，表明任务分配不均。
- **探索策略有效**：包含CLIP引导探索的版本SR（0.66）略优于无探索版本（0.62）。
- **LLaMAR不依赖特权信息**，仅使用实时观察与执行反馈，即可与使用oracle反馈的版本性能相当（SR 0.66 vs 0.67）。
- **失败模式**包括：泛化错误（高/低层抽象误判）、智能体间干扰、对象未探索、动作解析错误等，为后续改进提供方向。

---

### 7. 优点

- **方法创新**：
  - 提出**计划-行动-纠正-验证**四模块认知架构，实现了无需oracle反馈的全闭环自我修正，这在多智能体长期规划中首次实现。
  - 引入**启发式探索策略**，利用CLIP语义相关性引导智能体前往可能包含任务对象的区域，提高探索效率。
  - 采用**集中式多智能体系统（CMAS）**，通过联合观察和记忆进行协调，优于现有分散式框架。
- **实验设计**：
  - 构建了**MAP-THOR**标准化基准，涵盖4个难度等级、45个任务、5种布局，便于重复和对比。
  - 消融实验全面，证实每个模块的必要性。
  - 在**两种不同领域（家庭与搜救）** 上验证，展示泛化能力。
  - 报告了**置信区间**和**失败案例分析**，透明且客观。

---

### 8. 不足与局限

- **计算成本高**：每个决策步需查询4次LM，导致高于基线方法的API调用成本和延迟，限制了实时应用。
- **空间推理有限**：模型仅依赖文本描述和图像特征，无法进行精确的3D空间推理（如避障、最短路径），制约导航效率。
- **底层LM性能瓶颈**：性能受限于GPT-4V或开源VLM的指令跟随与推理能力，偶现误解环境规则或物体属性导致低效或错误。
- **实验覆盖不够全面**：
  - 仅在仿真环境（AI2-THOR和SAR）中验证，未在真实机器人上测试。
  - 智能体数量上限为5，未探索更大规模团队。
  - 任务种类虽有45个，但均为家庭或搜救主题，缺乏更广泛的任务领域。
- **探索策略依赖CLIP**：虽有效但可能无法应对物体概念模糊或CLIP嵌入不准确的情况。
- **动作解析失败**：SentenceBERT在对象匹配和计数上有时出错（约3.3%的失败率），影响执行可靠性。
- **未讨论在动态变化环境（如非平稳目标）中的表现**。

---

（完）
