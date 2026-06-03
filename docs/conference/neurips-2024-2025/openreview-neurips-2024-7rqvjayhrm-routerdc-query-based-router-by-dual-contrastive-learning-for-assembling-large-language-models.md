---
title: "RouterDC: Query-Based Router by Dual Contrastive Learning for Assembling Large Language Models"
title_zh: RouterDC：基于双重对比学习的查询路由，用于组装大语言模型
authors: "Shuhao Chen, Weisen Jiang, Baijiong Lin, James Kwok, Yu Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=7RQvjayHrM"
tags: ["query:mas-routing"]
score: 6.0
evidence: 基于查询的路由器，使用双重对比学习组装多个LLM
tldr: RouterDC提出了一种基于查询的双重对比学习路由器，用于在多个大语言模型中选择最适合当前查询的模型。通过样本-LLM和样本-样本对比损失，路由器学习更精准的模型选择策略。实验表明，RouterDC显著优于单个顶级模型及其他路由方法，有效聚合了多个LLM的互补能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 700, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 704, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 968, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 398, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 610, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 385, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 332, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 474, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 382, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 475, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 428, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 430, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 427, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1397, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1401, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-7rqvjayhrm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 519, \"height\": 382, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1299, \"height\": 562, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1429, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1090, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1109, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1198, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 587, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1427, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 615, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1228, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-7rqvjayhrm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1334, \"height\": 198, \"label\": \"Table\"}]"
motivation: 现有路由方法在多个LLM表现相近时效果不佳，需要更精细的选择策略。
method: 提出RouterDC模型，包含编码器和LLM嵌入，使用双重对比损失（样本-LLM和样本-样本）训练。
result: 在多个LLM组装任务上优于单个最佳模型和其他路由方法。
conclusion: RouterDC证明对比学习能有效提升查询路由的准确性和鲁棒性。
---

## Abstract
Recent works show that assembling multiple off-the-shelf large language models (LLMs) can harness their complementary abilities. To achieve this, routing is a promising method, which learns a router to select the most suitable LLM for each query. However, existing routing models are ineffective when multiple LLMs perform well for a query. To address this problem, in this paper, we propose a method called query-based Router by Dual Contrastive learning (RouterDC). The RouterDC model, which consists of an encoder and LLM embeddings, is trained by two proposed contrastive losses (sample-LLM and sample-sample losses). Experimental results show that RouterDC is effective in assembling LLMs and largely outperforms individual top-performing LLMs as well as existing routing methods on both in-distribution (+2.76\%) and out-of-distribution (+1.90\%) tasks. The source code is available at https://github.com/shuhao02/RouterDC.

---

## 论文详细总结（自动生成）

# RouterDC：基于双重对比学习的查询路由，用于组装大语言模型——详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：多个现成的大语言模型（LLM）在不同任务上各有优劣，组装它们可以发挥互补能力。现有路由方法（如 ZOOTER）通过 KL 散度对齐路由器输出与 LLM 得分分布，但当多个 LLM 对同一查询表现都很好时，得分差异很小，softmax 归一化后信号弱，导致路由效果不佳。
- **核心问题**：如何有效训练一个路由器，使其能在多个 LLM 均适合回答某查询时，仍能正确选择其中一个，并兼顾训练稳定性和泛化能力。
- **整体含义**：提出一种基于查询的双重对比学习路由器（RouterDC），通过样本-LLM 对比损失和样本-样本对比损失，更精细地学习每个查询与 LLM 的匹配关系，从而高效组装多个 LLM，提升性能。

## 2. 论文提出的方法论

### 核心思想
- 路由器由一个小型语言模型编码器（mDeBERTaV3-base，86M 参数）和 T 个可学习的 LLM 嵌入向量组成。对于每个查询，编码器提取查询嵌入，与各 LLM 嵌入计算余弦相似度，经 softmax 得到选择概率。
- 训练时使用两种对比损失：
  1. **样本-LLM 对比损失**：根据 LLM 在训练查询上的得分，选择 top-K+ 个 LLM 作为正样本，bottom-K− 个（得分<0.5）作为负样本，拉近查询嵌入与正样本 LLM 嵌入的距离，推远与负样本的距离。
  2. **样本-样本对比损失**：先对训练查询进行无监督聚类（t-SNE + k-means），然后在每个 mini-batch 中，拉近同组查询嵌入的距离，推远不同组查询嵌入的距离，以提高训练稳定性和嵌入的聚类结构。

### 关键技术细节
- **得分设计**：对开放式生成任务（如 GSM8K），重复采样 M=10 次后计算正确率；对多项选择题（如 MMLU），基于选项概率计算得分，错误答案得分为 0 以惩罚。
- **训练目标**：总损失为两种对比损失的加权和，超参数 λ 默认设为 1。
- **训练过程**：不反向传播梯度通过 LLM，仅更新编码器和 LLM 嵌入，参数高效（<100M）。
- **推理**：对于测试查询，选择与查询嵌入余弦相似度最大的 LLM 进行推理，只需调用一次 LLM，效率高。

### 算法流程（文字说明）
1. 对每个训练样本，计算所有 LLM 的得分。
2. 对训练查询进行聚类，得到 N 个组。
3. 每个 mini-batch：
   - 根据得分确定每个查询的正负 LLM 集合，计算样本-LLM 对比损失。
   - 从同一 mini-batch 中随机选择一个同组查询和 H 个不同组查询，计算样本-样本对比损失。
   - 联合优化。

## 3. 实验设计

### 数据集与场景
- **候选 LLM**：7 个开源 7B/8B 模型（Mistral-7B、MetaMath-Mistral-7B、zephyr-7b-beta、Chinese-Mistral-7B、dolphin-2.6-mistral-7b、Llama-3-8B、dolphin-2.9-llama3-8b）。
- **训练数据**：五个任务（MMLU、GSM8K、CMMLU、ARC-C、HumanEval）的部分训练集（每个任务 70% 用于训练，30% 用于测试）。训练集合并为总训练集。
- **分布内测试**：上述五个任务的测试集。
- **分布外测试**：PreAlgebra、MBPP、C-EVAL 三个 OOD 任务。
- **额外 OOD 测试**：JavaScript 代码生成任务（远距离 OOD）。

### 基准方法（baselines）
- **候选 LLM 本身**：7 个 LLM 单独性能。
- **Voting**：所有 LLM 输出进行多数投票（集成方法）。
- **CosineClassifier**：将路由视为多类分类，训练余弦分类器（等价于 K+=1, K- = T-1, λ=0）。
- **ZOOTER**：基于 KL 散度对齐奖励得分的现有方法。
- **LoraRetriever**：基于任务聚类（使用聚类索引替代任务标签）的路由方法。

### 评价指标
- 准确率（%）和推理时间（分钟）。

## 4. 资源与算力

- 论文明确说明使用的 GPU：NVIDIA A100 80GB。
- 训练轮数：1000 步，mini-batch 大小 64，学习率 5e-5，优化器 AdamW。
- 训练时间：约 28.3 分钟（文中提到 RouterDC 训练仅需 28.3 分钟）。
- 未说明 GPU 数量（可能是单卡或少量卡），也未给出总 GPU 时数。模型参数规模：编码器 86M，LLM 嵌入可忽略，总计 <100M。

## 5. 实验数量与充分性

- **主要实验**：在 5 个分布内任务和 3 个分布外任务上比较准确率，同时报告推理时间。
- **消融实验**：
  - λ 的影响（从 0 到 10）。
  - 聚类数 N 的影响（2~30）。
  - 负样本数 H 的影响（0~5）。
  - K+ 和 K- 的联合影响（热力图）。
  - 样本-样本损失的有效性（训练/测试曲线对比，t-SNE 可视化）。
  - 任务标签 vs 无监督聚类对比。
  - 训练样本数量影响（10~100 样本/任务）。
  - 单任务设置（HumanEval 单独训练测试）。
  - 远端 OOD 任务（JavaScript）。
  - 鲁棒性测试：移除一个 LLM 后的性能变化。
  - 成本效益分析（在 RouterBench 基准上）。
  - 对 ZOOTER 添加样本-样本损失的效果。
- **实验充分性**：实验覆盖了多种任务、多种超参数、消融和鲁棒性分析，设计较为全面，且对比公平（均使用相同数据划分和评价工具）。但未报告多次运行的标准差或误差条，可能影响统计显著性判断。

## 6. 论文的主要结论与发现

- RouterDC 在分布内任务上平均准确率 58.54%，比最佳单个 LLM（dolphin-2.9-llama3-8b，54.56%）高出 3.98%，比现有最佳路由方法 LoraRetriever（55.77%）高出 2.77%。
- 分布外任务上平均准确率 45.85%，比最佳单个 LLM（43.95%）高出 1.90%，且优于所有路由方法。
- 样本-LLM 对比损失比 KL 散度对齐损失更适合路由，特别是当多个 LLM 表现良好时。
- 样本-样本对比损失有效提高了训练稳定性和聚类结构，并提升了最终性能。
- RouterDC 对超参数 λ、N、H 不敏感，且仅需少量训练样本（30 样本/任务即可超过 SOTA）。
- 路由器对单个 LLM 丢失具有鲁棒性（可依靠其他正样本 LLM 备份）。
- 推理效率高（约 6× 快于 Voting），训练参数少、计算开销低。

## 7. 优点

- **方法创新**：首次将双重对比学习引入 LLM 路由，克服了现有 KL 散度方法的缺陷。
- **参数高效**：编码器仅 86M 参数，训练时不需反向传播 LLM，计算和存储成本低。
- **实验全面**：涵盖分布内、分布外、单任务、远端 OOD、成本效益、鲁棒性等多角度评估。
- **分析深入**：通过 t-SNE 可视化、相似度矩阵、训练曲线等揭示了路由器的行为和损失函数的影响。
- **实用性**：推理只调用一次 LLM，效率高；对超参数不敏感，易于实际应用。

## 8. 不足与局限

- **LLM 规模局限**：仅测试了 7B/8B 级别的模型，未涉及更大模型（如 70B 或 GPT-4 系列），评估范围有限。
- **未报告统计误差**：所有结果均为单次运行，缺少多次重复的标准差或置信区间，难以判断显著性。
- **计算资源细节不足**：未明确 GPU 数量、总训练时长、显存占用等，可复现性受限。
- **依赖无监督聚类**：聚类质量可能影响样本-样本损失的效果，文中仅使用 k-means，未探讨其他聚类方法。
- **未考虑对话上下文**：路由器仅针对单一查询，未扩展至多轮对话场景。
- **公平性/偏差问题**：未讨论路由选择可能导致对某些查询的偏见或公平性问题。

（完）
