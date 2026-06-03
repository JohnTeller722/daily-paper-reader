---
title: United Minds or Isolated Agents? Exploring Coordination of LLMs under Cognitive Load Theory
title_zh: 统一思维还是孤立智能体？认知负荷理论下的LLM协调探索
authors: "HaoYang Shang, Xuan Liu, Zi Liang, Jie ZHANG, Haibo Hu, Song Guo"
date: 2025-05-04
pdf: "https://openreview.net/pdf?id=Lq1qoP4Kwt"
tags: ["query:mas-routing"]
score: 7.0
evidence: 提出多智能体协调框架以减轻认知负荷
tldr: LLM在复杂多约束任务中表现受限，类比于人类认知负荷。本文引入认知负荷理论，提出CoThinker多智能体框架，通过结构化任务分配与协调来降低各智能体认知负载。实验证明CoThinker在多个复杂任务上显著提升性能，展示了协调路由在多智能体系统中的价值。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1409, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1293, \"height\": 849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1441, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lq1qop4kwt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 595, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-lq1qop4kwt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lq1qop4kwt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1170, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lq1qop4kwt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1169, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-lq1qop4kwt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1169, \"height\": 570, \"label\": \"Table\"}]"
motivation: 单个LLM处理多约束任务时认知负荷过载，需要多智能体协调分担。
method: 基于认知负荷理论设计CoThinker框架，将任务分解并路由给多个LLM智能体，减少每个智能体的负载。
result: 在多种复杂任务上，CoThinker较单模型和多智能体基线取得更好效果。
conclusion: 认知负荷理论指导的多智能体协调能有效提升LLM系统能力。
---

## Abstract
Large Language Models (LLMs) exhibit a notable performance ceiling on complex, multi-faceted tasks, as they often fail to integrate diverse information or adhere to multiple constraints. 
We posit that such limitation arises when the demands of a task exceed the LLM's effective cognitive load capacity. This interpretation draws a strong analogy to Cognitive Load Theory (CLT) in cognitive science, which explains similar performance boundaries in the human mind, and is further supported by emerging evidence that reveals LLMs have bounded working memory characteristics.
Building upon this CLT-grounded understanding, we introduce ***CoThinker***, a novel LLM-based multi-agent framework designed to mitigate cognitive overload and enhance collaborative problem-solving abilities. ***CoThinker*** operationalizes CLT principles by distributing intrinsic cognitive load through agent specialization and managing transactional load via structured communication and a collective working memory. We empirically validate *CoThinker* on complex problem-solving tasks and fabricated high cognitive load scenarios, demonstrating improvements over existing multi-agent baselines in solution quality and efficiency. Our analysis reveals characteristic interaction patterns, providing insights into the emergence of collective cognition and effective load management, thus offering a principled approach to overcoming LLM performance ceilings.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大型语言模型（LLM）在处理复杂、多约束任务时出现性能天花板，表现为思维退化、缺乏多样性、无法遵循多个要求。现有研究虽通过多智能体系统尝试解决，但多依赖直觉，缺乏理论支撑。
- **类比认知负荷理论（CLT）**：作者将LLM性能退化类比于人类认知过载——当任务需求超出LLM的有效工作记忆容量时发生。已有研究表明LLM具有有界工作记忆和类似人类的失败模式。
- **整体含义**：通过引入认知科学中的CLT，解释LLM性能瓶颈，并基于此设计更合理的多智能体协作架构，以提升复杂问题求解能力。

## 2. 方法论：核心思想与技术细节
- **核心思想**：将CLT原则操作化到多智能体系统中，通过分布内在认知负荷（intrinsic load）和管理交易负荷（transactional load）来缓解过载，模拟人类集体智慧。
- **技术细节**：
  - **智能体并行思考（Agent Parallel Thinking）**：利用“思维风格编排器”为每个智能体生成任务特定的思维风格（基于Sternberg理论），促进认知劳动分工，降低单个智能体的内在负荷。
  - **交互记忆系统（Transactive Memory System, TMS）**：维护集体工作记忆状态 μ(t)，包含：（1）专家目录（谁知道什么），（2）共享知识库（共识与已建立事实），（3）差异与未解决问题。减少冗余处理。
  - **通信调节器（Communication Moderator）**：通过固定入度N和概率重连β构建小世界通信网络。以概率1-β连接认知相似的智能体（强连接，局部聚类），以概率β随机连接不同智能体（弱连接，全局集成）。平衡本地协作与信息多样性。
  - **合成器（Synthesizer）**：在T轮迭代后，由外部或组内智能体整合所有智能体最终输出和TMS状态，生成最终解。
  - **算法流程**：初始化（风格生成、初始输出、TMS初始化）→ 迭代（选择参考集、智能体生成、更新TMS）→ 最终合成。

## 3. 实验设计
- **数据集/场景**：
  - **LiveBench**：包含数学、推理、指令跟随、数据分析、语言五个类别，由Big-Bench Hard、AMPS、IFEval等构成。
  - **CommonGen-Hard**：高元素交互性的约束生成任务，要求从30余个干扰概念中选择3-5个目标概念生成连贯段落。
- **Benchmark**：使用Gemini系列模型（gemini-1.5-flash-8b, gemini-1.5-flash, gemini-1.5-pro）。
- **对比方法**：
  - 单智能体：标准提示（IO）、思维链（CoT）、自我反思（Self-Refine, SR）。
  - 多智能体：多智能体辩论（MAD）、多样化多智能体辩论（DMAD）。
- **评估指标**：LiveBench上各子任务相对分数（归一化于闪存8b-IO基线）；CommonGen-Hard上10维度LLM评判分数。

## 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量、训练时长。所有实验通过Gemini模型的API调用完成，未涉及本地训练或微调，计算资源主要依赖云API。因此无法提供具体算力信息。

## 5. 实验数量与充分性
- **主要实验**：
  - LiveBench主表（表1）：覆盖3种模型、5个类别，共15组对比。
  - CommonGen-Hard雷达图和轮数图（图3）。
  - 消融研究（图4、5、6、7、8）：分别探索参考集大小N（4个水平）、探索率β（4个水平）、智能体数量M（3个水平），以及组合配置（3种M/N组合）。
  - 附录中提供各子任务原始分数（表2-4）。
- **充分性评价**：
  - 实验覆盖不同能力梯度的模型和多种任务类型，消融参数范围合理。
  - 但缺少统计显著性检验（无误差棒），仅报告点估计。消融图显示趋势但未验证可靠性。
  - 各基线在相同参数（温度、惩罚）下运行，比较公平。
  - 总体实验设计较全面，客观性较好。

## 6. 主要结论与发现
- CoThinker在**高认知负荷任务**（数据分析、推理、数学）上持续优于所有基线，尤其在Data Analysis和Reasoning类别提升显著（例如在gemini-1.5-pro上相对IO提升达1.82倍）。
- 在**低负荷任务**（指令跟随）上优势不明显甚至略差，印证了认知负荷理论：低负荷任务下协作通信开销可能成为负担。
- CommonGen-Hard上CoThinker实现多轮持续改进，而基线（MAD）因过载在后期性能下降。
- 消融研究显示存在最优参数（N≈2-3，β≈0.3-0.6，M≈6），参数选择需平衡信息多样性与过载风险，验证了认知负荷管理原则。

## 7. 优点
- **理论驱动**：首次将认知负荷理论（CLT）系统性地应用于LLM多智能体设计，提供可解释的理论基础。
- **架构创新**：综合运用智能体分工、交互记忆系统、小世界网络通信等多模块设计，模拟人类集体认知机制。
- **实验扎实**：跨3种模型、2种任务套件、多种基线对比，消融研究覆盖关键超参数。
- **洞察深刻**：通过结果差异区分高/低负荷任务，验证理论预测，并揭示参数敏感性与交易成本问题。

## 8. 不足与局限
- **模型单一**：仅使用Gemini系列LLM，未在开源模型（如Llama）或不同架构上验证，泛化性未知。
- **无统计检验**：缺乏误差棒或显著性检验，结果稳定性存疑。
- **交易成本定量分析缺失**：虽讨论交易负荷，但未提供量化指标（如token数、延迟）对比。
- **思维风格生成依赖LLM编排器**：风格质量可能不稳定，且未研究对内在负荷分布的直接证据。
- **未开源代码**：论文虽描述详尽但未提供可运行代码，复现需较大工作量。
- **低负荷任务效果有限**：指令跟随等简单任务上协作可能引入冗余开销，适用场景受限。

（完）
