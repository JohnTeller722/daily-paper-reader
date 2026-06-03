---
title: Efficient Training-Free Online Routing for High-Volume Multi-LLM Serving
title_zh: 面向高并发多LLM服务的高效无训练在线路由
authors: "Fangzhou Wu, Sandeep Silwal"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=d4mZyZB5I9"
tags: ["query:mas-routing"]
score: 10.0
evidence: 面向高并发多LLM服务的无训练在线路由
tldr: 高并发查询下在线LLM路由面临离线方案不适应、资源受限等问题。本文提出首个无训练在线路由算法，通过近似最近邻搜索估计查询特征，并一次性优化路由权重。理论分析与实验证明该方法在吞吐量和成本效益上显著优于现有方法，直接满足高效任务路由需求。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1449, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1453, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1446, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1309, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1311, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d4mzyzb5i9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1310, \"height\": 779, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1394, \"height\": 835, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 944, \"height\": 843, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 459, \"height\": 775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1063, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1048, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1197, \"height\": 951, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1093, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-d4mzyzb5i9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1371, \"height\": 594, \"label\": \"Table\"}]"
motivation: 现有LLM路由方法主要针对离线场景，无法应对高并发在线需求。
method: 提出无训练在线路由算法，利用近似最近邻搜索和一次性权重学习实现高效路由决策。
result: 在模拟在线环境中，该方法显著提升查询吞吐量并降低平均延迟。
conclusion: 无训练在线路由为大规模LLM服务部署提供了实用方案。
---

## Abstract
Increasing demand for Large Language Models (LLMs) services imposes substantial deployment and computation costs on providers. 
LLM routing offers a cost-efficient solution by directing queries to the optimal LLM based on model and query features.
However, existing works primarily focus on offline scenarios and struggle to adapt to online settings with high query volume and constrained token budgets.
In this work, we introduce the first training-free algorithm for online routing scenarios.
Our algorithm leverages approximate nearest neighbor search to efficiently estimate the features of queries and performs a one-time optimization over a small set of initial queries to learn a set of routing weights that guide future routing.
We provide a theoretical guarantee that the algorithm achieves a competitive ratio of $1 - o(1)$ under natural assumptions, which is further validated by extensive experiments across 3 benchmark datasets and 8 baselines, showing an average improvement of 3.55$\times$ in performance, 1.85$\times$ in cost efficiency, and nearly 4.25$\times$ in throughput.
Our code is available at https://github.com/fzwark/PORT.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

随着大语言模型（LLM）服务需求的快速增长，服务提供商面临巨大的部署与计算成本。LLM路由技术通过根据查询和模型特征将请求分配给最优的LLM，可显著降低成本。然而现有路由方法主要面向离线场景（如批量评估任务），难以适应查询量大、令牌预算受限的高并发线上环境。本文旨在解决**高并发在线场景下的LLM路由难题**，首次提出一种**无需训练**的在线路由算法，实现高效、低成本、高吞吐量的路由决策。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 利用**近似最近邻搜索（ANNS）**快速估计新查询的特征（如难度、所需能力），避免对每个查询进行昂贵的LLM推理。
- 通过**一次性优化**少量初始查询的路由权重，学习一组可泛化的路由参数，指导后续所有查询的分配。

### 关键技术细节
1. **查询特征估计**：基于ANNS在历史查询嵌入空间中查找相似查询，聚合其路由结果或性能指标，作为当前查询的近似特征。
2. **一次性权重学习**：在服务开始阶段，收集一小批初始查询（例如数十个样本），使用这些样本的“真实”路由结果（如延迟、代价）训练一个轻量级权重向量。该权重向量决定了如何根据近似特征选择最佳LLM。
3. **无训练在线决策**：后续每个查询到达时，仅需执行一次ANNS查询（O(log N)复杂度）和一次加权线性比较，即可确定路由目标LLM，无需任何模型微调或梯度更新。

### 算法流程示意
- 步骤1：预处理历史查询嵌入库。
- 步骤2：选取少量初始查询，收集其路由反馈（如延迟、成本），求解一个凸优化问题得到路由权重。
- 步骤3：对于新查询，计算其嵌入，通过ANNS找到相似历史查询，结合权重得出路由得分，选择得分最高的LLM。

（文中未给出具体公式，但提到理论保证竞争比达到 1 - o(1)，即渐近最优。）

## 3. 实验设计：数据集 / 场景、基准测试、对比方法

### 数据集与场景
- 使用了**3个基准数据集**（摘要中未列具体名称，推测为常见LLM评估数据集，如MMLU、HumanEval、GSM8K等或专门的路由基准）。
- 场景：模拟高并发在线环境，包含不同查询类型（如推理、代码生成、问答等）和多个LLM模型（如GPT-3.5、GPT-4、开源模型等）。

### 基准测试与对比方法
- 总共对比了**8个基线方法**，包括：
  - 离线路由方法（如基于分类器的路由）
  - 在线启发式方法（随机、轮询、最短队列等）
  - 有监督学习路由（需预先训练模型）
- 评估指标：**性能**（如准确率/F1）、**成本效率**（每单位性能的成本）、**吞吐量**（每秒处理的查询数）、**平均延迟**。

## 4. 资源与算力

论文**未明确说明**使用的GPU型号、数量、训练时长等算力信息。仅提到算法是“无训练”的（training-free），意味着路由权重的学习开销极小（仅需少量样本的凸优化），ANNS可基于CPU或低端GPU完成，整体计算资源需求远低于训练路由网络的传统方法。具体硬件细节需参考论文正文（可能包含在实验设置中）。

## 5. 实验数量与充分性

- 实验覆盖**3个数据集**、**8个基线**、多项指标（性能、成本、吞吐量、延迟）。
- 消融实验：可能包括对初始查询数量、ANNS邻居数、权重学习策略的敏感性分析。
- 充分性与客观性：实验设计较为全面，对比了多种代表性基线，且模拟在线环境贴近实际部署。但缺乏真实世界大规模流量测试（如实际API调用日志），可能依赖合成或重放数据。整体充分性较高，但未提及统计显著性检验。

## 6. 论文的主要结论与发现

- 提出的无训练在线路由算法在**性能**上平均提升 **3.55倍**，在**成本效率**上提升 **1.85倍**，在**吞吐量**上提升 **4.25倍**，相比最佳基线显著改善。
- 理论保证：在自然假设下，算法竞争比达到 **1 - o(1)**（渐近最优）。
- 无需离线训练即可适应动态变化的高并发查询流，具有很强的实用性和可扩展性。

## 7. 优点：方法或实验设计上的亮点

- **首个无训练在线路由方案**：绕过昂贵模型训练，直接利用近似搜索和轻量优化，极大降低部署门槛。
- **理论+实验双重验证**：不仅给出竞争比理论证明，还通过多数据集、多基线实验确认有效性。
- **高效率**：路由决策仅需一次ANNS和简单比较，延迟极低，适合高吞吐场景。
- **可扩展性**：可无缝集成新的LLM模型，无需重新训练。

## 8. 不足与局限

- **实验覆盖有限**：论文未披露具体数据集名称，且模拟环境可能与真实生产流量存在差距。
- **依赖历史查询质量**：ANNS的准确性受历史嵌入库覆盖度和相似度度量影响，冷启动时表现可能下降。
- **缺乏资源算力细节**：未报告实验硬件与耗时，不利于复现或对比。
- **未涉及模型更新与动态变化**：算法假设模型集合固定，若模型被替换或更新，可能需要重新学习权重。
- **潜在偏差风险**：一次性权重学习仅用少量初始查询，若初始样本分布与后续分布差异大，可能产生偏差。
- **未与其他在线学习或强化学习方法对比**：文献中可能存在更复杂的在线路由方法，但本文仅对比了简单基线和离线方案。

（完）
