---
title: Towards Modular LLMs by Building and Reusing a Library of LoRAs
title_zh: 通过构建和复用LoRA库走向模块化大语言模型
authors: "Oleksiy Ostapenko, Zhan Su, Edoardo Ponti, Laurent Charlin, Nicolas Le Roux, Lucas Caccia, Alessandro Sordoni"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=0ZFWfeVsaD"
tags: ["query:mas-routing"]
score: 6.0
evidence: 提出用于LLM适配器库的零样本路由机制Arrow，类比于代理路由策略
tldr: 随着大语言模型参数高效适配器数量激增，如何复用它们提升新任务性能成为问题。本文研究如何构建适配器库，并提出模型聚类MBC方法，以及零样本路由机制Arrow——动态选择最相关适配器来处理新输入。该方法在零样本和监督泛化中均表现优异，其路由思想可直接迁移至多智能体系统中的任务分发与专家路由。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 787, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 770, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-0zfwfevsad/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 879, \"height\": 539, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 746, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 687, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 656, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1682, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1656, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1664, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1655, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1654, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1771, \"height\": 2067, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-0zfwfevsad/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 2075, \"label\": \"Table\"}]"
motivation: 如何有效构建和复用大量LLM适配器以提升新任务性能是未解难题。
method: 提出基于模型聚类的库构建方法MBC，以及零样本路由机制Arrow动态选择适配器。
result: 在多个NLU任务上，Arrow路由策略在零样本和微调场景均优于现有基线。
conclusion: 模块化适配器库结合智能路由可实现高效的任务泛化，为智能体路由提供了借鉴。
---

## Abstract
Given the increasing number of parameter-efficient adapters of large language models (LLMs), how can we reuse them to improve LLM performance on new tasks? We study how to best build a *library* of adapters given multi-task data and devise techniques for both *zero-shot* and *supervised* task generalization through *routing* in such library. We benchmark existing approaches to build this library and introduce model-based clustering, $\texttt{MBC}$, a method that groups tasks based on the similarity of their adapter parameters, indirectly optimizing for transfer across the multi-task dataset. In order to reuse the library, we present a novel zero-shot routing mechanism, $\texttt{Arrow}$, which enables dynamic selection of the most relevant adapters for new inputs without the need for retraining. We experiment with several LLMs, such as Phi-2 and Mistral, on a wide array of held-out tasks, verifying that MBC-based adapters and Arrow routing lead to superior generalization to new tasks. Thus, we make steps towards creating modular, adaptable LLMs that can match or outperform traditional joint training.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 核心问题与整体含义（研究动机和背景）

随着大量参数高效适配器（如LoRA）在大语言模型上的广泛使用，如何有效构建并复用这些适配器以提升模型在新任务上的性能，成为一个重要问题。现有方法通常需要对适配器和路由机制进行联合训练，但现实中适配器往往是独立、异步训练的（如用户从在线中心下载或贡献），缺乏统一的训练范式。本文旨在研究：**在独立训练的适配器库基础上，能否通过后验路由实现零样本或监督式任务泛化，从而构建模块化的大语言模型**。

## 2. 方法论

### 核心思想
论文提出两阶段框架：**先构建适配器库，后复用（路由）**。构建阶段关注如何将多任务数据压缩成一组可复用的适配器；复用阶段关注如何在不重新训练的情况下为新输入选择最合适的适配器。

### 关键技术细节

- **构建库的三种方式**：
  - **私有适配器（Private）**：每个任务独立训练一个LoRA，直接用于路由。
  - **共享适配器（Shared）**：在所有任务上训练单个LoRA。
  - **模型聚类（Model-Based Clustering, MBC）**：首先为每个任务独立训练LoRA，然后利用LoRA参数之间的余弦相似度对任务进行聚类（K-means），最后在每个聚类上联合训练一个LoRA。MBC的训练分为两阶段：第一阶段用少量步骤训练私有LoRA用于聚类；第二阶段用剩余步骤训练每个簇的适配器，总计算量与直接训练私有LoRA相当。

- **路由方法**（主要针对零样本）：
  - **μ路由**：均匀路由，等效于对适配器参数取平均。
  - **TP路由**：训练一个任务分类器（基于T5编码器），根据输入预测任务，然后选择对应适配器。
  - **CM路由**：对每个适配器，利用其训练数据的隐藏表示均值作为原型，计算输入隐藏状态与每个原型的余弦相似度作为路由权重。
  - **Arrow路由（↗↗）**：对每个LoRA适配器的参数矩阵AiBi^T进行SVD分解，取右第一奇异向量作为该适配器的**原型**。路由时，计算输入隐藏状态h与每个原型（向量）的绝对点积作为logits，选择top-k进行softmax。该方法无需访问训练数据，且可逐层、逐token路由。

- **LoRA组合**：将选中的适配器参数按路由权重线性加权融合，作为最终适配器。

## 3. 实验设计

### 数据集
- **多任务训练集**：Flan v2中的256个任务（排除SNI任务）。
- **零样本评估**：10个常见任务，包括常识推理（WinoGrande、HellaSwag、PIQA）、问答（BoolQ、OpenbookQA、ARC easy/hard）、编程（HumanEval、MBPP）、通用推理（BBH）。同时也在12个SNI任务上进行了零样本测试。
- **监督适应评估**：12个从SNI中抽取的类别，每个任务最多10,000个训练样本，1,000个验证样本。评估指标为Rouge-L。

### 基线方法
- **Base**：无适配器的原始模型。
- **Shared**：单LoRA联合训练。
- **FullFT**：全模型微调。
- **Poly / MHR**：联合训练多个“潜在技能”适配器及路由。
- **Private-μ / Private-↗↗**：私有适配器库+均匀路由或Arrow路由。
- **MBC-μ / MBC-↗↗**：MBC库+对应路由。
- **LoraHub / π-tuning**：监督设置下的对比方法。

### 模型
- Phi-2（2.8B）
- Mistral 7B
- 额外有StableLM 3B（附录）

### 超参数
- LoRA rank=4，dropout=0.05，α=16，lr=1e-4。
- MBC使用10个簇（通过验证集确定最佳数量）。
- 零样本路由使用top-4，温度1。

## 4. 资源与算力

论文**未明确说明**使用的GPU型号、数量或总训练时长。仅提到多任务训练使用256个任务，每个任务训练若干epoch，但对于具体计算资源（如多少张GPU、多久）没有披露。从MBC方法描述可知，第一阶段每个任务独立训练2 epoch，第二阶段每个簇训练剩余步骤，总计算量与直接训练私有LoRA相同（即256个任务各训练N步 vs 先部分步数再10个簇各训练N步）。

## 5. 实验数量与充分性

论文进行了较为充分的实验，包括：
- **零样本实验**：在10个常见任务和12个SNI任务上，使用Phi-2和Mistral两个模型，对比多种库构建方式和路由方法，有Table 1、Table 5、Figure 3等。
- **监督适应实验**：在12个SNI任务上，以100%和10%数据量进行，对比多种方法，包括No Library、Shared、Poly、MBC-μ、MBC-Poly等，见Table 3、Table 7、Table 8。
- **消融实验**：对比不同聚类方法（随机任务、随机样本、嵌入聚类、MBC），见Table 2；分析簇数量对性能影响，Figure 4；分析Arrow路由的动机（图5和附录8.1验证norm ratio）。
- **上游性能评估**：在256个训练任务的验证集上评估Arrow和μ路由，并与Oracle对比（Figure 3右）。
- **额外模型**：StableLM 3B（Table 4）。
- **少样本（0.5%数据）** 适应实验（Table 6附录）。

实验覆盖了多模型、多任务、不同数据量，消融和对比例子充分，公平性较好（如MBC的总计算量与其他方法匹配）。但零样本评估主要在英语NLP任务，未涉及多语言或视觉等模态。

## 6. 主要结论与发现

- **私有适配器+Arrow路由**（Private-↗↗）可以在零样本设置下**匹配甚至超越**全微调（FullFT）和共享训练（Shared）的性能，说明异步独立训练的适配器可以通过后验路由有效复用。
- **MBC库**（模型聚类）在零样本和监督适应中均优于其他库构建方法（私有库、共享库、随机聚类），尤其是在均匀路由下（MBC-μ）效果显著。
- **Arrow路由**在私有库上显著优于均匀路由和TP/CM路由，缩小了与MBC的差距；但在MBC库中，均匀路由已足够好，Arrow提升有限。
- **路由对于大规模库（256适配器）重要**，对于小规模库（10个）效果不如大规模明显（因为小库多样性低，均匀近似最优）。
- **适配器参数的相似性**与任务间正迁移相关性高，可用于指导任务聚类和路由原型。

## 7. 优点

- **方法简洁有效**：MBC和Arrow均基于现有LoRA参数，无需额外数据或复杂训练，易于实现。
- **框架统一**：同时覆盖了适配器库构建和复用，适用于零样本和监督场景。
- **大规模验证**：跨3个模型（Phi-2、Mistral、StableLM）、多种任务类型（推理、QA、代码）、多种数据量进行实验。
- **路由机制创新**：Arrow利用SVD分解获得任务原型，无需数据就能进行逐token、逐层路由，具有高效、可扩展的特点。
- **强调模块化与协作**：展示了独立训练的适配器可以组合使用，支持去中心化、异步训练的场景。

## 8. 不足与局限

- **局限于LoRA**：方法仅验证了LoRA适配器，未扩展到其他参数高效方法（如Prefix Tuning、Adapters、Prompts等），通用性有待检验。
- **实验覆盖有限**：仅在中型模型（2.8B–7B）和英文NLP任务上测试，未在大规模模型（如70B+）或多语言/多模态基准上验证。
- **缺少计算开销细节**：未明确报告训练所需GPU型号、数量和训练时长，难以精确评估方法的实际成本。
- **Arrow路由的局限性**：在MBC小库上提升不明显，且路由基于绝对点积，可能忽略负相关特征。此外，未讨论路由的计算开销（SVD分解成本低，但每token计算点积仍需开销）。
- **未充分探讨任务间干扰**：虽然聚类目标是为了减少干扰，但论文未直接分析聚类内任务间干扰的大小，仅通过下游性能间接说明。
- **实验结果有不一致之处**：例如在MBC库中，Arrow路由对Phi-2有轻微的0.3%提升，但对Mistral反而下降（Table 1）；附录Table 5中MBC-↗↗也低于MBC-μ。作者解释为小库中均匀路由已足够，但未深入分析原因。
- **隐私假设的简化**：私有库假设每个任务数据独立且不共享，但实际中任务可能来自同一用户，隐私边界不清晰。

（完）
