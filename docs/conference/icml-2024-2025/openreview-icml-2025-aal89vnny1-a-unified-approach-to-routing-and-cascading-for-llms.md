---
title: A Unified Approach to Routing and Cascading for LLMs
title_zh: LLM路由与级联的统一方法
authors: "Jasper Dekoninck, Maximilian Baader, Martin Vechev"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AAl89VNNy1"
tags: ["query:mas-routing"]
score: 7.0
evidence: LLM在智能体系统中的路由与级联
tldr: 针对现有LLM路由与级联策略缺乏最优性证明和组合能力的问题，本文提出了一种统一的最优策略，通过形式化推导证明了其最优性，并揭示了策略有效的条件。实验表明该策略在多种设置下显著改善了成本-性能权衡。该工作为LLM模型选择提供了理论基础和实用指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-aal89vnny1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1546, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aal89vnny1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 606, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aal89vnny1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1711, \"height\": 574, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1596, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 697, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1326, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1639, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1260, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1555, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aal89vnny1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 793, \"height\": 301, \"label\": \"Table\"}]"
motivation: 现有LLM路由和级联策略缺乏最优性理论，且无法结合两者优势以优化成本-性能。
method: 推导出级联的最优策略，并提出统一框架结合路由与级联，给出形式化最优性证明。
result: 在多个基准上验证了统一策略的优越性，相比单独路由或级联实现了更好的成本-性能平衡。
conclusion: 统一路由与级联策略为LLM系统选择提供了理论保障和实践优势。
---

## Abstract
The availability of a wide range of large language models (LLMs) embedded in various agentic systems has significantly increased the potential of model selection strategies to improve the cost-performance tradeoff. Existing strategies involve either routing, where a single model is chosen per query, or cascading, which sequentially runs increasingly larger models until a satisfactory answer is found. However, current approaches face three key limitations: they (1) lack formal proofs of optimality, (2) fail to identify the conditions under which these strategies are most effective to improve the cost-performance tradeoff, and (3) are unable to combine both paradigms for further improvements. To address these issues, we first derive a novel optimal strategy for cascading and prove the optimality of an existing routing strategy. Further, we propose *cascade routing*, a unified framework that integrates routing and cascading into a theoretically optimal strategy. Through our analysis, we identify good quality estimators as the critical factor for the success of model selection paradigms.  Finally, in our experiments, we show that cascade routing consistently outperforms the individual approaches by a large margin and we analyze quality estimators to determine when routing and/or cascading are useful paradigms for model selection.

---

## 论文详细总结（自动生成）

# 大语言模型路由与级联的统一方法：详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：随着大语言模型（LLM）在各类智能体系统中的广泛应用，如何从多个不同能力/成本的模型中选择最合适的模型来处理每个查询，以优化“成本-性能权衡”，成为一个关键问题。
- **现有策略**：主要有两种——**路由（Routing）**：为每个查询直接选择一个单一模型；**级联（Cascading）**：按序运行多个模型（通常从小到大），直到某个模型给出足够好的答案。
- **三大局限**：
  1. 现有策略缺乏形式化的**最优性证明**；
  2. 未能识别这些策略最有效的**条件**；
  3. **无法结合两种范式**以获得进一步改进。
- **核心目标**：提出一个统一框架，理论上最优地整合路由与级联，并揭示**质量估计（Quality Estimation）** 是决定模型选择成败的关键因素。

## 2. 论文提出的方法论

### 核心思想
将模型选择问题建模为**线性优化问题**：在给定的成本预算下最大化输出质量。分别推导了路由、级联和统一框架“级联路由（Cascade Routing）”的最优策略。

### 关键技术细节

- **路由的形式化（§2）**：
  - 定义路由策略 \( s: X → Δ_k \)，将查询映射到模型上的概率分布。
  - 优化目标：\(\max_s \mathbb{E}_x[\sum_i s_i(x) \hat{q}_i(x)]\)，约束：\(\mathbb{E}_x[\sum_i s_i(x) \hat{c}_i(x)] \le B\)。
  - **最优策略**：对每个查询，选择最大化 \( \hat{q}_i(x) - λ\hat{c}_i(x) \) 的模型（ λ 为权衡参数）；若多个模型并列，则在最便宜和最贵之间随机化（ γ 控制）。
  - 使用**先验质量估计（ex-ante）**，即查询前预测模型表现。

- **级联的形式化（§3）**：
  - 重新解释级联为一系列路由问题：每次决定是否继续运行下一个模型，需要比较所有可能的“超级模型（Supermodel）”（即已运行模型的序列）。
  - 超级模型的质量定义为 \( \mathbb{E}[\max(\hat{q}_1,...,\hat{q}_i)]\)，成本为各模型成本之和。
  - **最优级联策略**：同样使用线性权衡，但每步的 λ 可不同，并同时利用**先验质量估计**和**事后质量估计（post-hoc）**（基于已获得的模型输出更新估计）。
  - 证明阈值策略仅在强简化假设下等价于最优策略。

- **级联路由（Cascade Routing）**（§4）：
  - 统一框架：在每一步，**可以从任意未运行的模型中选择下一个模型**，而非只能按固定顺序，且可跳过模型。
  - **最优性**：同样形式化为序列路由问题，使用 λ 和 γ 参数。
  - **模型顺序**：选中的超模型内部按成本升序运行，先运行便宜的。
  - **剪枝**：利用“负边际增益引理（Lemma 1）”：如果一个模型的加入降低了超模型的成本-质量权衡，则所有包含该超模型的集合都可以被剪枝，从而将搜索空间从指数级降低到实际可管理。

### 算法流程（文字说明）

- **路由算法（Algorithm 1）**：对每个查询，计算每个模型的权衡值 \( τ_i = \hat{q}_i - λ\hat{c}_i\)；选出达到最大值的模型集合；若随机数小于 γ 则选其中最便宜的，否则选最贵的。
- **级联算法（Algorithm 2）**：在每一步 j，对所有超级模型 M₁:j-1, …, M₁:k 计算超模型质量和成本，然后调用路由算法；若选中的是已运行的超模型则停止，否则继续运行下一个模型 mⱼ。
- **级联路由算法（Algorithm 3）**：在每一步 j，考虑所有包含已运行模型的超模型集合；计算每个超模型的质量和成本；调用路由选出最优超模型；从中选出尚未运行的最便宜模型执行。

## 3. 实验设计

### 数据集 / 场景

| 场景 | 具体数据集 | 说明 |
|------|------------|------|
| RouterBench | MMLU, GSM8k, MBPP 等 7 个基准，11 个模型（GPT-4 到 Mistral-7B） | 专门评估路由和级联的基准，可控制噪声水平。 |
| SWE-Bench | 真实软件工程任务（GitHub issue 解决） | 事后质量估计可基于测试用例精确获得。 |
| 数学+代码 | Minerva Math + LiveCodeBench，使用 Qwen2.5 系列模型 | 先验质量估计可借助来源特征准确获得。 |
| 分类 | ARC-Challenge, MMLU-Pro, MixEval | 使用 LLAMA、GEMMA、MISTRAL 模型族，质量估计基于 logits。 |
| 开放推理 | MMLU-Pro, GSM8k | 同上，使用 logits 作为质量估计特征。 |

### Benchmark 设置

- **RouterBench**：0-shot 和 5-shot 设置；模型数量（3, 5, 11）；噪声水平（low, medium, high）。
- **SWE-Bench**：10 个提交模型（如 SWE-agent, Claude 等），成本基于运行时间。
- **数学+代码**：5 个 Qwen2.5 模型，成本基于 token 数乘参数规模。
- **分类/开放推理**：每个模型族 3 个模型，成本基于 API 价格。

### 对比方法

- **线性插值（Linear Interpolation）**：简单基线。
- **路由（Routing）**：本文 §2 的最优路由。
- **级联（Baseline）**：传统阈值级联（如 FrugalGPT 等）。
- **级联（Ours）**：本文 §3 的最优级联。
- **级联路由（Ours）**：本文 §4 的统一方法。

### 评估指标
- 主要指标：**AUC（曲线下面积）**，通过变化成本预算得到质量-成本曲线。

## 4. 资源与算力

**论文未明确说明**具体使用的 GPU 型号、数量及训练时长。文中提到：
- 路由和级联的质量估计器使用**逻辑回归**模型，训练在较小验证集上（RouterBench 用 5% 数据约 2000 样本）。
- 在分类/开放推理任务中使用了 Together API 进行模型推理，成本按 API 价格计算。
- 消融实验中给出了不同变体的平均运行时（毫秒级），但未提及硬件配置。
- 总体来说，本工作侧重于算法框架和理论证明，计算资源需求相对较低，主要开销来自多次调用 LLM 进行推理。

## 5. 实验数量与充分性

### 实验数量
论文共包含**四大类实验**（RouterBench、SWE-Bench、数学+代码、分类/开放推理），每类实验内有多组子实验：
- RouterBench：3×3×2 = 18 组（模型数×噪声水平×参数设置（0-shot/5-shot）），另加额外噪声扫面（图 2）。
- SWE-Bench：2 种模型数量（5 和 10）。
- 数学+代码：5 个模型。
- 分类/开放推理：3 个模型族 × 2 任务类型 ≈ 6 组，每个任务又包含多个基准（MMLU, ARC, MixEval 等）。
- 消融实验（Appendix）：4 种变体对比，加上运行时分析（最多 80 个模型）。

### 充分性与公平性
- **充分性**：实验覆盖了多种任务类型（分类、推理、编码、数学）、多种模型族（GPT, LLAMA, GEMMA, MISTRAL, Qwen2.5 等）、多种噪声水平、多种模型数量。还包含了消融和运行时分析。
- **公平性**：所有方法使用相同的数据集分割和评估流程；置信区间通过 bootstrap 计算（Appendix E），报告了 95% 置信区间；多个基准下 cascade routing 均显著优于或至少不差于基线。
- **潜在偏差**：RouterBench 的噪声设置是人工添加的（高斯噪声），可能不完全反映真实估计噪声；现实基准中质量估计器（如 logits）可能并非最优，因此结论对估计器质量敏感。

## 6. 论文的主要结论与发现

1. **最优性**：首次给出路由和级联的最优性证明，并推导出新的级联策略（Ours）优于传统阈值级联。
2. **级联路由统一框架**：Cascade Routing 在理论上是最优的，且在实际中始终优于单独的路由或级联，性能提升可达 8%~14%（相对 AUC）。
3. **质量估计至关重要**：
   - 路由依赖**先验质量估计**（ex-ante），级联依赖**事后质量估计**（post-hoc）。
   - 当这两种估计都较准确时，cascade routing 优势最大。
   - 在估计噪声很高时，增益缩小，但仍不差于基线。
4. **模型数量**：可用模型越多，cascade routing 的相对优势越大。
5. **鲁棒性**：即使在事后质量估计不准确（如 SWE-Bench 的二元反馈）或先验估计不准确时，cascade routing 仍然比单独方法稳定。

## 7. 优点

- **理论贡献**：严格证明了路由、级联和级联路由的最优性，填补了先前工作缺乏形式化最优性保证的空白。
- **统一框架**：cascade routing 是第一个同时结合路由任意选择 + 级联序列回溯的范式，且可剪枝以保证计算可行。
- **实践指导**：通过理论和实验揭示了质量估计的重要性，为未来模型选择系统的设计提供了方向。
- **广泛实验**：涵盖多种任务、模型和噪声设置，结果可信。
- **代码开源**：提供了代码仓库（github.com/eth-sri/cascade-routing），便于复现。

## 8. 不足与局限

- **依赖质量估计器的准确性**：实验中使用了简化的估计模型（逻辑回归、线性模型、logits 特征等），真实场景中构建高精度估计器本身是一个困难问题。论文指出，当估计误差很大时，cascade routing 的优势很小（但仍不差）。
- **实验未覆盖所有具体场景**：例如未测试多模态任务、长文本生成、实时在线场景。此外，成本仅考虑 API 费用或延迟，未考虑内存或功耗。
- **计算开销**：虽然通过剪枝降低了搜索复杂度，但在模型数量很多（>80）时，正常变体的运行时可能达秒级，需要贪心变体（Greedy）来加速。
- **消融实验仅限 RouterBench**，未在真实基准上测试不同变体的影响。
- **潜在偏差**：RouterBench 的噪声设置是人工的，可能无法完全代表真实估计噪声的分布；现实基准中的估计器（如 logits）可能不适用于所有模型或任务。
- **最优性证明依赖于某些假设**（例如质量估计是随机变量且已知方差，成本可线性估计等），实际中这些假设未必完全满足。

（完）
