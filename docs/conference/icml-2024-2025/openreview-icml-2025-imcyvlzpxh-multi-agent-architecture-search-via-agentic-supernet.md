---
title: Multi-agent Architecture Search via Agentic Supernet
title_zh: 通过智能体超网络进行多智能体架构搜索
authors: "Guibin Zhang, Luyang Niu, Junfeng Fang, Kun Wang, LEI BAI, Xiang Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=imcyVlzpXh"
tags: ["query:mas-routing"]
score: 9.0
evidence: 为多跳推理动态选择架构
tldr: 该论文针对LLM多智能体系统的手工设计难题，提出MaAS框架。它放弃固定单一架构，转而优化一个概率性的智能体超网络，能够根据每个查询的难度和领域动态分配推理资源。实验表明，MaAS在多个多跳推理任务上实现了更好的准确率-成本权衡，直接满足了如何为开放式多跳推理选择最佳配置的需求。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1741, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 833, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 838, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1739, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 1256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 674, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 1066, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 680, \"height\": 565, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1818, \"height\": 979, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 969, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1207, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1205, \"height\": 233, \"label\": \"Table\"}]"
motivation: 手动设计多智能体系统耗时且难以动态适应不同查询的难度和领域。
method: 提出MaAS框架，优化一个概率分布的智能体超网络，实现按需动态架构选择。
result: 在多个推理任务上，MaAS在准确率和推理成本之间取得了优于静态系统的平衡。
conclusion: 动态架构搜索是优化多智能体推理性能和资源利用的有效途径。
---

## Abstract
Large Language Model (LLM)-empowered multi-agent systems extend the cognitive boundaries of individual agents through disciplined collaboration and interaction, while constructing these systems often requires labor-intensive manual designs. Despite the availability of methods to automate the design of agentic workflows, they typically seek to identify a static, complex, one-size-fits-all system, which, however, fails to dynamically allocate inference resources based on the difficulty and domain of each query. To address this challenge, we shift away from the pursuit of a monolithic agentic system, instead optimizing the \textbf{agentic supernet}, a probabilistic and continuous distribution of agentic architectures. We introduce \textbf{MaAS}, an automated framework that samples query-dependent agentic systems from the supernet, delivering high-quality solutions and tailored resource allocation (\textit{e.g.}, LLM calls, tool calls, token cost). Comprehensive evaluation across six benchmarks demonstrates that MaAS \textbf{(I)} requires only $6\\sim45\\%$ of the inference costs of existing handcrafted or automated multi-agent systems, \textbf{(II)} surpasses them by $0.54\\%\sim11.82\\%$, and \textbf{(III)} enjoys superior cross-dataset and cross-LLM-backbone transferability.

---

## 论文详细总结（自动生成）

# 论文《Multi-agent Architecture Search via Agentic Supernet》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：目前基于大语言模型（LLM）的多智能体系统（如 AutoGen、MetaGPT）通常依赖手工设计，而自动化的工作流设计方法（如 AFlow、GPTSwarm）往往试图搜索一个**静态的、通用的、复杂**的单架构，但这类方法无法根据不同查询的难度和领域动态分配推理资源（如 LLM 调用次数、工具使用、Token 开销）。
- **核心问题**：如何让多智能体系统在推理时实现 **查询自适应**的资源分配与性能优化，避免“一刀切”的资源浪费或性能不足。
- **整体含义**：该论文提出从“寻找单个最优架构”转向“优化一个概率分布（agentic supernet）”，从而根据每个查询采样适合的子架构，实现性能与成本的权衡。

## 2. 方法论

### 核心思想
- **提出智能体超网络（Agentic Supernet）**：一个包含多个候选智能体算子（operator）及其概率分布的连续架构空间。
- **查询自适应采样**：通过一个控制器网络，根据输入查询的语义和难度，从超网络中采样一个多智能体系统（即子网络）执行推理。
- **联合优化**：超网络的参数（算子概率分布）和算子本身（通过文本梯度）共同优化，以最大化性能并最小化成本。

### 关键技术细节

- **智能体算子定义**：每个算子由 LLM 调用集合、提示词、工具集合组成，例如 CoT、Self-Refine、Multi-agent Debate、ReAct 等。
- **超网络结构**：包含 L 层（实验中 L=4），每层的算子概率分布由控制器网络生成，且支持提前退出（early-exit）算子。
- **控制器网络**：采用 MoE 风格，使用轻量嵌入模型（MiniLM）编码查询和已选算子，计算每个候选算子的得分，按得分排序累积直到阈值（thres=0.3）决定该层激活哪些算子。
- **优化目标**：最小化期望负性能 + λ × 成本，其中成本为 token 开销。
- **梯度估计**：
  - 对分布 π：采用蒙特卡洛采样和重要性权重（成本感知的贝叶斯方法）近似梯度。
  - 对算子本身：由于包含自然语言和工具调用，使用 LLM 生成的**文本梯度**来更新提示词、温度、算子结构（如图 3）。
- **算法流程**：训练集上，对每个查询循环多层采样架构，执行获得答案和反馈，联合更新分布和算子。

## 3. 实验设计

### 数据集和 Benchmark
- **数学推理**：GSM8K、MATH（617 个高难度子集）、MultiArith（但原文表 1 中写 SVAMP？实际上表中是 MultiArith，正文也提到 MultiArith，后面又提到 SVAMP 可能是笔误）
- **代码生成**：HumanEval、MBPP
- **工具使用**：GAIA（多领域任务，包括网页浏览、文件读取等）
- 总计 6 个公开基准，训练/测试比 1:4。

### 对比方法
- **单智能体基线**：Vanilla、CoT、ComplexCoT、Self-Consistency
- **手工多智能体**：MultiPersona、LLM-Debate、LLM-Blender、DyLAN、AgentVerse、MacNet
- **自动化多智能体**：AutoAgents、GPTSwarm、ADAS、AgentSquare、AFlow
- 此外在 GAIA 上还对比 AutoGPT、TapeAgent、Sibyl。

### 主要实验结果（表 1、表 2）
- MaAS 在 5 个常规基准上平均准确率 83.59%，超过所有对比方法（第二名为 AFlow 82.25%）。
- 在 GAIA 上平均 20.69%，显著优于第二名（AgentSquare 16.34% 等）。

## 4. 资源与算力

- **未明确说明使用的 GPU 型号、数量及训练时长**。实验中仅提及通过 API 调用闭源模型（gpt-4o-mini）和开源模型（Qwen-2.5-72b、llama-3.1-70b）进行推理和训练。
- **训练时间与成本**：在 MATH 上，MaAS 训练仅耗时 53 分钟，花费 3.38$；而 AFlow 需 184 分钟、22.50$。推理时 MaAS 花费 0.42$、19 分钟，均为最低。

## 5. 实验数量与充分性

- **实验数量**：涵盖 6 个数据集、对比 14 种以上的基线方法，并包括：
  - 消融实验（表 4）：移除文本梯度、移除提前退出、移除成本约束。
  - 参数敏感性分析（图 7）：层数 L、成本系数 λ、采样次数 K。
  - 转移性分析（表 7、表 8）：跨模型（gpt-4o-mini→Qwen/llama）和跨数据集（MATH→GSM8K 等）。
  - 归纳性分析（图 8、图 9）：在训练中未见过 Debate 算子，测试时仍能合理使用。
  - 案例研究（图 5、图 6）：可视化采样概率和生成工作流。
- **公平性**：基线均在相同的 gpt-4o-mini 后端上运行，参数固定。实验设计较客观。

## 6. 主要结论与发现

1. **性能领先**：MaAS 在 6 个基准上超越所有手工和自动化方法 0.54%～16.89%。
2. **极端成本效率**：推理成本仅为对比方法的 6%～45%，训练成本低至 AFlow 的 15%。
3. **自适应资源分配**：通过提前退出和算子动态选择，简单查询使用浅层、简单算子，复杂查询使用深层、复合算子（图 5 证明）。
4. **强迁移性**：跨 LLM 和跨数据集表现良好。
5. **归纳能力**：能够适应训练时未见的新算子。

## 7. 优点

- **创新性**：首次将神经架构搜索中的超网络概念引入多智能体系统设计，改变了“寻找单一最优架构”的范式。
- **实用性强**：同时优化性能和成本，适合实际部署场景（资源有限、查询多样性）。
- **方法完备**：包含控制器、文本梯度、提前退出等组件，形成端到端自动化流程。
- **实验全面**：消融、敏感度、迁移性、归纳性均有验证，且成本分析详细。

## 8. 不足与局限

- **硬件资源未说明**：未提及 GPU 型号、数量，实验可复现性依赖于商业 API。
- **文本梯度质量依赖 LLM**：算子更新依赖于 LLM 生成的文本梯度，可能不稳定或受限于基础 LLM 的推理能力。
- **超参数选择**：层数 L、阈值 thres 等可能对结果敏感，文中仅在部分参数上测试（如 L=4 固定后分析），未做更广泛的调优。
- **算子集合预定义**：初始算子集合由人工选取（如 CoT、Debate 等），限制了搜索空间的上限。
- **仅在部分数学/代码/工具任务上验证**，未涉及更复杂的开放域对话、多模态交互等场景。
- **实验规模**：训练集较小（如 MATH 仅 119 个训练样本），可能影响泛化性。

（完）
