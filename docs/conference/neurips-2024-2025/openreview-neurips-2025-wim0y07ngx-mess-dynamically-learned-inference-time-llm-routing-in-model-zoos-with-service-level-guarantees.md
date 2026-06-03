---
title: "MESS+: Dynamically Learned Inference-Time LLM Routing in Model Zoos with Service Level Guarantees"
title_zh: MESS+：具有服务级别保证的动态学习推理时代LLM路由
authors: "Herbert Woisetschläger, Ryan Zhang, Shiqiang Wang, Hans Arno Jacobsen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wIM0y07NGX"
tags: ["query:mas-routing"]
score: 6.0
evidence: 动态LLM路由，具有服务级别保证的模型动物园
tldr: MESS+提出了一种随机优化算法，用于在模型动物园中实现成本最优的大语言模型请求路由，同时提供严格的SLA合规保证。该方法通过学习LLM的请求满意度概率，在保证服务质量的前提下最小化运营成本。实验表明，MESS+能有效平衡成本与服务级别协议要求，适用于实际部署。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 565, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1298, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 431, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 2063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wim0y07ngx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 1539, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 691, \"height\": 792, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 934, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1150, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 725, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1438, \"height\": 705, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1433, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 661, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1432, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1432, \"height\": 826, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wim0y07ngx/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1434, \"height\": 828, \"label\": \"Table\"}]"
motivation: 在LLM模型动物园中，如何自动选择最合适的模型以满足用户需求并最小化成本是一个挑战。
method: 提出MESS+随机优化算法，学习LLM的请求满意度概率，实现成本最优的路由决策，并提供SLA合规保证。
result: 在多个基准测试中，MESS+在满足SLA的同时显著降低了路由成本。
conclusion: MESS+是一种有效且实用的LLM路由方法，适用于模型选择场景。
---

## Abstract
Open-weight large language model (LLM) zoos provide access to numerous high-quality models, but selecting the appropriate model for specific tasks remains challenging and requires technical expertise. Most users simply want factually correct, safe, and satisfying responses without concerning themselves with model technicalities, while inference service providers prioritize minimizing operating costs. These competing interests are typically mediated through service level agreements (SLAs) that guarantee minimum service quality. 
We introduce MESS+, a stochastic optimization algorithm for cost-optimal LLM request routing while providing rigorous SLA compliance guarantees. MESS+ learns request satisfaction probabilities of LLMs in real-time as users interact with the system, based on which model selection decisions are made by solving a per-request optimization problem. Our algorithm includes a novel combination of virtual queues and request satisfaction prediction, along with a theoretical analysis of cost optimality and constraint satisfaction.
Across a wide range of state-of-the-art LLM benchmarks, MESS+ achieves an average of $2\times$ cost savings compared to existing LLM routing techniques.

---

## 论文详细总结（自动生成）

# MESS+ 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在包含多个开源大语言模型（LLM）的“模型动物园”中，如何自动为每个用户请求选择最合适的模型，**在最小化运营成本的同时，严格保证服务级别协议（SLA）要求的最低请求满意率**。
- **背景**：
  - 开源 LLM 数量激增（如 Llama、Granite、Qwen 等），每个家族有多个模型，用户难以选择。
  - 用户关心响应质量（正确、安全），但缺乏技术知识；服务提供商希望降低成本；双方通过 SLA 约束服务质量。
  - 现有方法（如 RouteLLM、RouterDC）缺乏形式化的 SLA 保证，往往过度使用大模型导致成本偏高。
- **整体含义**：提出首个**随机优化框架**，能够在线学习模型满意度，通过每请求决策权衡成本与 SLA 约束，实现成本最优且满足服务质量下限。

## 2. 论文提出的方法论

### 核心思想
基于 Lyapunov 漂移-惩罚框架，结合 **虚拟队列**（记录累积的 SLA 违反量）和 **请求满意度预测器**（在线学习），将请求路由建模为每请求优化问题，在保证长期 SLA 满足的前提下最小化平均运营成本。

### 关键技术细节
- **请求满意度预测器**：使用 ModernBERT 作为骨干，顶部加多标签分类头（每标签对应一个模型）。通过 SGD 在线训练，交叉熵损失函数 + L2 正则化。探索时查询所有模型获得真实标签，更新预测器。
- **虚拟队列**：队列长度 \(Q_t\) 更新公式：  
  \(Q_{t+1} = \max\{0,\, Q_t + \alpha - s_{m^*,t}\}\)，其中 \(\alpha\) 是 SLA 目标满意率，\(s_{m^*,t}\) 是选择的模型的实际满意度。队列长度反映累积 SLA 不足。
- **每请求优化问题**：
  \[
  \min_{y_{m,t}} \; V \sum_m y_{m,t} E_{m,t} + Q_t (\alpha - \sum_m y_{m,t} \hat{s}_{m,t})
  \]
  其中 \(V\) 控制成本与 SLA 满足速度的权衡，\(E_{m,t}\) 是模型运营成本，\(\hat{s}_{m,t}\) 是预测满意度。只选择一个模型，解为选择最小化该目标的模型。
- **探索-利用策略**：以概率 \(p_t = \min(1, c/4\sqrt{t})\) 探索（查询所有模型，训练预测器，并返回最大模型输出）；否则利用（使用预测器求解上述问题）。
- **理论保证**：
  - **约束满足**（定理1）：虚拟队列长度有界，SLA 违反随 \(T\) 减小至 \(O(1/\sqrt{T})\)。
  - **成本最优性**（定理2）：平均成本接近最优静态策略差额为 \(O(M/\sqrt[4]{T} + 1/V + M F_{\min})\)，其中 \(F_{\min}\) 是预测器最小损失。

## 3. 实验设计

### 数据集 / 场景
- **模型动物园**：
  - 主实验：Llama 3.2 1B、Llama 3.1 8B、Llama 3.3 70B（3个模型）。
  - 扩展实验：Qwen 2/2.5 模型（0.5B、1.5B、7B、32B，4个模型）；混合 Llama+Qwen 等。
- **评估基准**：8 个 benchmark（零样本）：
  - 推理：ARC Easy、ARC Challenge、Winogrande
  - 问答：BoolQ、LogiQA、PiQA、SciQ、SocialIQA
- **成本度量**：每次推理能耗（兆焦耳，MJ）作为运营成本。
- **对比方法**：
  - 单模型基线（三个 Llama 分别单独服务）
  - “Educated Guessing”：已知平均统计信息的随机路由，满足 SLA。
  - RouteLLM：基于 BERT 路由，仅支持两个模型（设为 1B 和 70B）。
  - RouterDC：支持多模型，基于对比学习。

### 实验设计特点
- 针对每个基准设定不同的 \(\alpha\) 值（反映模型在该任务上的能力）。
- 调节超参数使所有对比方法满足 SLA 并尽可能成本最优。
- 每个实验重复 3 次不同随机种子。

## 4. 资源与算力

- **硬件**：2 × NVIDIA H100 GPU（每张 80GB VRAM）。
- **模型分配**：
  - GPU1：小模型（1B、8B）+ 预测器
  - GPU2：大模型（70B）
- **训练时长**：文中未明确给出具体训练时长，但包含在线学习（每请求少量 SGD 步骤）。代码已开源，可复现。
- **其他**：使用 vLLM 作为推理后端，LM-Eval Harness 进行评估。

## 5. 实验数量与充分性

- **主实验**：8 个 benchmark，包含完整指标（成本、满意度、模型调用比例）。
- **参数分析**：
  - 对不同的 \(V\) 值（0.0001, 0.001, 0.01）进行实验，展示成本-收敛权衡。
  - 对探索参数 \(c\)（0.01, 0.1, 1.0）进行预测器训练成本分析。
- **额外场景**：
  - 稀疏用户反馈（仅 20% 请求提供反馈）。
  - 大规模模型动物园（4 个 Qwen 模型）。
  - 非平稳基准（拼接 ARC Challenge、PiQA、Winogrande）。
  - 窄成本 spread（缩小模型间成本差异）。
  - 稀疏队列更新（仅 20% 请求更新虚拟队列）。
  - 混合模型族（Llama + Qwen）。
- **充分性评价**：实验覆盖多种现实场景（不同模型数、不同反馈密度、非平稳分布、不同成本结构），且每组实验重复三次，误差棒在表格中给出。对比方法超参数经过调整以保证公平。总体实验设计**充分且客观**。

## 6. 论文的主要结论与发现

- **成本最优性**：MESS+ 在所有 benchmark 上平均成本最低，相比 RouteLLM 和 RouterDC 节省约 **2× 成本**，比 Educated Guessing 节省约 **20%**。
- **SLA 满足**：MESS+ 严格满足 \(\alpha\) 要求（满意率紧贴 \(\alpha\)），而其他方法往往过度满足（大量使用70B模型）导致成本飙升。
- **V 的作用**：较小 \(V\) 能更快达到 SLA 但成本较高；较大 \(V\) 收敛慢但更节能。MESS+ 通过调整 \(V\) 可灵活权衡。
- **鲁棒性**：
  - 稀疏反馈（20%）下性能几乎不变。
  - 大型模型动物园（4个）仍保持成本优势（比 RouterDC 优 1.6×）。
  - 非平稳基准下表现稳定。
- **理论验证**：约束违反随请求数减小至 \(O(1/\sqrt{T})\)，成本接近最优解。

## 7. 优点

- **首次引入形式化 SLA 保证**：将请求路由建模为带约束的随机优化问题，提供理论收敛和约束满足证明。
- **在线学习无需人工标注偏好数据**：利用用户交互实时学习满意度预测器，省去繁琐数据集构造。
- **灵活的权衡控制**：参数 \(V\) 可调节成本与收敛速度，适应不同业务需求。
- **低开销**：预测器引入额外成本仅占平均推理调用成本的 **4.65%**。
- **全面实验验证**：涵盖多种模型组合、反馈稀疏性、非平稳分布等现实挑战，结果稳定可靠。
- **代码开源**：便于复现和进一步研究。

## 8. 不足与局限

- **假设用户满意度标签立即可得**：实际中用户反馈可能延迟/缺失/Mr。论文虽测试了稀疏反馈（20%），但完全无反馈场景未涉及。
- **探索阶段需查询所有模型**：同时调用多个模型获得真实满意度，在实际中可能带来高昂成本或用户体验问题（如多输出混淆）。
- **预测器训练依赖完整标签**：探索时需知道每个模型是否满足当前请求，这在用户仅能评价一个输出时不可行。
- **未考虑多轮对话或连续交互**：实验基于单轮 benchmark 样本，实际应用场景更复杂。
- **分布假设**：理论分析假设请求 i.i.d.，虽在非平稳实验展示鲁棒性，但理论未覆盖。
- **基准局限性**：仅使用标准 NLP 基准（零样本），未在真实用户反馈或复杂任务（如编程、生成式）上评估。
- **成本度量单一**：仅考虑能源消耗，未涵盖 API 调用费、延迟等。

（完）
