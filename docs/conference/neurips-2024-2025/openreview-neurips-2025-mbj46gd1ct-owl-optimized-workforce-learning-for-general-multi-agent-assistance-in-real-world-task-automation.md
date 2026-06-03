---
title: "OWL: Optimized Workforce Learning for General Multi-Agent Assistance in Real-World Task Automation"
title_zh: OWL：针对通用多智能体辅助的优化劳动力学习以实现真实世界任务自动化
authors: "Mengkang Hu, Yuhang Zhou, Wendong Fan, Yuzhou Nie, Ziyu Ye, Bowei Xia, Tao Sun, Zhaoxuan Jin, Yingru Li, Zeyu Zhang, Yifeng Wang, Qianshuo Ye, Bernard Ghanem, Ping Luo, Guohao Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MBJ46gd1CT"
tags: ["query:mas-routing"]
score: 9.0
evidence: 协调器负责子任务管理和高效任务路由
tldr: OWL提出了一种分层多智能体框架Workforce，通过解耦规划与执行，并引入协调器进行子任务路由，实现了跨领域任务自动化。该方法解决了当前系统需要完整重新设计的缺陷。实验表明，该框架在多个领域任务上表现优异，提升了泛化能力和效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1352, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 501, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1352, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mbj46gd1ct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1396, \"height\": 834, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1496, \"height\": 1079, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 931, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1404, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1388, \"height\": 672, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1505, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 738, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1018, \"height\": 705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1158, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mbj46gd1ct/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1382, \"height\": 310, \"label\": \"Table\"}]"
motivation: 现有LLM多智能体系统跨领域迁移时需要完全重新设计和重新训练，缺乏通用性。
method: 提出Workforce分层框架，包含领域无关的规划器、协调器（负责子任务路由）和领域特定的工人。
result: 在多个真实世界任务上验证了框架的泛化能力和效率提升，无需重新设计。
conclusion: 通过解耦规划与执行并引入协调路由，实现了跨领域任务自动化的有效泛化。
---

## Abstract
Large Language Model (LLM)-based multi-agent systems show promise for automating real-world tasks but struggle to transfer across domains due to their domain-specific nature.
Current approaches face two critical shortcomings: they require complete architectural redesign and full retraining of all components when applied to new domains.
We introduce **Workforce**, a hierarchical multi-agent framework that decouples strategic planning from specialized execution through a modular architecture comprising:
*(i)* a *domain-agnostic* **Planner** for task decomposition,
*(ii)* a **Coordinator** for subtask management, and
*(iii)* specialized **Workers** with *domain-specific* tool-calling capabilities.
This decoupling enables cross-domain transferability during both inference and training phases:
During inference, Workforce seamlessly adapts to new domains by adding or modifying worker agents;
For training, we introduce **Optimized Workforce Learning (OWL)**, which improves generalization across domains by optimizing a domain-agnostic planner with reinforcement learning from real-world feedback.
To validate our approach, we evaluate Workforce on the GAIA benchmark, covering various realistic, multi-domain agentic tasks.
Experimental results demonstrate Workforce achieves open-source state-of-the-art performance (**69.70%**), outperforming commercial systems like OpenAI's Deep Research by **2.34%**.
More notably, our OWL-trained 32B model achieves **52.73%** accuracy (**+16.37%**) and demonstrates performance comparable to GPT-4o on challenging tasks.
To summarize, by enabling scalable generalization and modular domain transfer, our work establishes a foundation for the next generation of general-purpose AI assistants.

*Our code is available at [Anonymous URL](https://anonymous.4open.science/r/annonymous-owl/), and our data is available at [Anonymous URL](https://huggingface.co/anonymous21016).*

---

## 论文详细总结（自动生成）

# 论文总结：OWL: Optimized Workforce Learning

## 1. 核心问题与整体含义（研究动机和背景）
- **动机**：当前基于 LLM 的多智能体系统（MAS）多为领域特定设计，跨领域迁移时需要完全重新设计架构并对所有组件进行重新训练，缺乏通用性和可扩展性。例如 MetaGPT 依赖软件工程的标准流程，无法直接扩展到其他领域。
- **目标**：提出一种通用的、模块化的多智能体框架，能够在不重新设计整体系统的情况下快速适配新领域，并提升跨领域迁移能力。
- **整体含义**：通过解耦战略规划与领域特定执行，实现“即插即用”的智能体扩展，为通用 AI 助手奠定基础。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将多智能体系统分为三个层次——领域无关的 Planner（任务分解）、Coordinator（子任务管理与分配）、领域特定的 Worker（工具调用执行）。这种解耦使得新域只需添加或替换 Worker 节点，而 Planner 和 Coordinator 保持不变。
- **Workforce 推理框架**：
  - Planner Agent：分析用户任务并分解为子任务，基于 Worker 能力注册表。
  - Coordinator Agent：根据 Worker 能力将子任务分配给合适的 Worker，管理依赖关系，集成中间结果。
  - Worker Nodes：一组专门化的智能体（如 Web Agent、文档处理 Agent、推理/编码 Agent），每个配备特定工具集。
  - 通信机制：通过共享任务通道（Task Channel）进行集中式通信，只有最终结果被发布，执行上下文隔离。
  - 重规划机制：当 Worker 报告子任务失败时，Planner 根据失败信息重新生成子任务，实现测试时扩展。
- **OWL（Optimized Workforce Learning）训练方法**：
  - 仅对 Planner 进行训练，Worker 保持不变。
  - 两阶段：第一阶段使用监督微调（SFT）初始化 Planner；第二阶段使用直接偏好优化（DPO）进一步优化，从真实世界反馈中学习。
  - 训练数据：从四个数据集（HotpotQA、WikiTableQuestions、数学问题、Infinity-MM）中通过 Workforce 生成轨迹，过滤后得到 1,599 条 SFT 轨迹和 1,009 条 DPO 偏好对。
- **关键算法流程**（文字描述）：
  - 初始化失败计数 F=0，失败信息集 I 为空，失败标志 B=False。
  - 若 F ≤ 最大重规划次数，则 Planner 根据 I 分解或重新规划子任务。
  - Coordinator 为每个子任务分配 Worker，Worker 执行并返回结果，若失败则记录失败信息并中断当前循环。
  - 若成功则跳出循环，否则 F++ 继续重规划。
  - 最后 Planner 综合所有结果输出最终答案。

## 3. 实验设计
- **数据集与基准**：GAIA 基准（通用 AI 助手评测），包含三个难度级别和多种能力需求（网页浏览、多模态、文档处理、推理、编码）。
- **对比方法**：
  - 专有框架：OpenAI Deep Research、h2oGPTe Agent、Trase Agent、Langfun Agent 等。
  - 开源框架：Open Deep Research、Magnetic-One、AutoAgent、TapeAgents 等。
  - 基线：Single Agent（单智能体）、Role Playing（CAMEL 风格双智能体）。
- **评估指标**：准确率（accuracy score），采用 pass@3（GPT-4o）或 pass@1（Claude-3.7-sonnet）。
- **实现细节**：所有模型通过 API 调用，贪婪解码，默认重规划阈值为 2，屏蔽已泄露答案的网站。

## 4. 资源与算力
- **训练配置**：
  - 使用 8 块 NVIDIA H100 GPU。
  - 基于 LlamaFactory 框架，输入序列最大长度 32,768 tokens，学习率 10⁻⁵，训练 2 个 epoch。
  - 混合精度 bfloat16，有效 batch size 为 12（单设备 batch size 1 + 梯度累积 12 步）。
- **推理**：无 GPU 需求，所有模型通过 API 调用。论文未提及推理所需的具体计算资源或时间。

## 5. 实验数量与充分性
- **主要实验**：Workforce 在 GAIA 上与 15 个以上基线对比（表1），覆盖专有和开源框架。
- **OWL 实验**：对不同 Planner 模型（GPT-4o-mini、Qwen2.5-72B、Claude-3.7-sonnet 等）进行对比，以及 OWL 训练前后的 Qwen2.5-32B 结果（表3）。
- **消融实验**：
  - 轨迹过滤对性能的影响（图2a）。
  - Planner vs Worker 训练对比（图4c）：只训练 Planner 显著优于只训练 Worker。
- **分析实验**：
  - 按能力类型（图3a）和所需能力数量（图4b）的鲁棒性分析。
  - 测试时扩展（重规划次数影响，图3b）。
  - 手动错误分析（表7、8），包含 6 大类 11 小类错误。
  - 统计显著性检验（Wilcoxon 符号秩检验，附录 H）。
- **充分性**：实验设计全面，覆盖多个维度，消融充分，对比公平（控制相同工具集和模型），但 GAIA 单一基准可能限制泛化。

## 6. 主要结论与发现
- **Workforce 达到开源 SOTA**：在 GAIA 上准确率 69.70%（Claude-3.7-sonnet），超越 OpenAI Deep Research（67.36%）2.34%，并在 Level 1 任务上超越所有现有方法。
- **OWL 显著提升 Planner 能力**：Qwen2.5-32B 经 OWL 训练后准确率从 36.36% 提升至 52.73%（+16.37%），超越 GPT-4o-mini（47.27%）和 Qwen2.5-72B（49.09%），在 Level 3 任务上与 GPT-4o 持平。
- **DPO 比单纯 SFT 更有效**：SFT 在 Level 3 上反而下降 3.85%，加入 DPO 后全面回升并提升 7.69%。
- **Planner 训练比 Worker 训练更关键**：只训练 Planner 取得 45.45%，远高于只训练 Worker 的 31.51%，且联合训练仅提升 1.23%。
- **测试时扩展有效**：增加重规划次数可提升性能。
- **模块化设计带来鲁棒性**：在需要多种能力的任务上，Workforce 性能下降最小（标准差 3.05），而 Role Playing 波动很大（标准差 11.39）。

## 7. 优点
- **模块化与跨领域可迁移性**：解耦规划与执行，新域只需替换或添加 Worker，无需重新训练整体系统。
- **高效训练**：仅训练 Planner，计算开销小，效果显著。
- **开源 SOTA**：首次在 GAIA 上超越 OpenAI Deep Research，缩小了开源与商业系统的差距。
- **全面的实验分析**：包括错误归类、统计检验、鲁棒性分析，验证了方法有效性。
- **完全开源**：代码、模型、数据全部公开，促进可复现研究。

## 8. 不足与局限
- **依赖高质量工具**：性能受限于领域特定工具包的可用性和可靠性，在工具缺乏的领域可能出现执行瓶颈。
- **训练开销**：尽管仅训练 Planner，但数据收集和 RL 过程仍需大量时间和计算资源（尤其是在线搜索延迟）。
- **单一基准**：仅在 GAIA 上评估，未在更多领域（如软件工程、医疗等）验证泛化能力。
- **数据污染风险**：训练数据可能包含与 GAIA 测试集相似的问题（尽管已屏蔽部分网站），存在过拟合可能。
- **潜在危险行为**：工具使用可能引入安全风险（如访问有害内容、执行破坏性代码），论文仅简单提及但未提供具体防护措施。
- **人工评估局限**：错误分析和案例研究基于手动标注，可能主观且样本有限。

（完）
