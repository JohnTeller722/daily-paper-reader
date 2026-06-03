---
title: Learning to Route Among Specialized Experts for Zero-Shot Generalization
title_zh: 学习在专用专家之间路由以实现零样本泛化
authors: "Mohammed Muqeeth, Haokun Liu, Yufan Liu, Colin Raffel"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=r0qcGcFL4U"
tags: ["query:mas-routing"]
score: 8.0
evidence: 学习在专用专家模型之间进行路由
tldr: 该论文提出PHATGOOSE方法，通过后训练的自适应令牌级门控机制，在大量专用专家模型中选择性地路由，从而显著提升零样本泛化能力。该方法避免了以往需要额外训练数据的限制，实现了灵活高效的专家路由，为多智能体系统中的智能体路由提供了可迁移的思路。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-r0qcgcfl4u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 781, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r0qcgcfl4u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1259, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r0qcgcfl4u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1719, \"height\": 441, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 813, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1721, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 493, \"height\": 2265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1524, \"height\": 1879, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1492, \"height\": 1472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1522, \"height\": 1877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r0qcgcfl4u/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1492, \"height\": 1470, \"label\": \"Table\"}]"
motivation: 大量专用语言模型难以有效复用，需一种路由机制实现零样本泛化。
method: 提出PHATGOOSE，通过后训练自适应令牌级门控学习路由。
result: 在多个零样本任务上优于现有路由方法，提升了泛化性能。
conclusion: 学习路由策略可有效利用专家库，推动零样本泛化。
---

## Abstract
Recently, there has been a widespread proliferation of "expert" language models that are specialized to a specific task or domain through parameter-efficient fine-tuning. How can we recycle large collections of expert language models to improve zero-shot generalization to unseen tasks? In this work, we propose $\textbf{P}$ost-$\textbf{H}$oc $\textbf{A}$daptive $\textbf{T}$okenwise $\textbf{G}$ating $\textbf{O}$ver an $\textbf{O}$cean of $\textbf{S}$pecialized $\textbf{E}$xperts (**PHATGOOSE**), which learns to route among specialized modules that were produced through parameter-efficient fine-tuning. Unlike past methods that learn to route among specialized models, PHATGOOSE explores the possibility that zero-shot generalization will be improved if different experts can be adaptively chosen for each token and at each layer in the model. Crucially, our method is *post-hoc* - it does not require simultaneous access to the datasets used to create the specialized models and only requires a modest amount of additional compute after each expert model is trained. In experiments covering a range of specialized model collections and zero-shot generalization benchmarks, we find that PHATGOOSE outperforms past methods for post-hoc routing and, in some cases, outperforms explicit multitask training (which requires simultaneous data access). To better understand the routing strategy learned by PHATGOOSE, we perform qualitative experiments to validate that PHATGOOSE's performance stems from its ability to make adaptive per-token and per-module expert choices.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- 随着参数高效微调（PEFT）技术的普及，涌现了大量针对特定任务或领域优化的“专家”语言模型（如LoRA模块）。这些专家模型通常由不同贡献者独立训练并共享，但如何有效回收利用这些专家模块以提升基座模型在**未见过任务上的零样本泛化能力**，是一个重要且待解决的问题。
- 现有方法（如基于输入嵌入检索单一专家）效果有限，落后于“oracle”路由（始终选择对当前查询最好的专家）。论文假设：**在不同层、对不同 token 自适应地选择不同专家**，可能比只选一个专家能实现更好的零样本泛化。
- 因此，论文提出了 **PHATGOOSE**（Post-Hoc Adaptive Tokenwise Gating Over an Ocean of Specialized Experts），一种后训练的自适应令牌级门控路由方法。

## 2. 方法论

- **核心思想**：在每个PEFT模块前训练一个**sigmoid门控**（一个线性层加sigmoid），该门控根据当前激活值决定是否使用该模块。训练门控时冻结基座模型和PEFT模块参数（后训练，post-hoc）。之后，利用各个门控向量构建**top-k路由**：在推理时，对每个token，计算该token激活与各门控向量的余弦相似度，选出k个得分最高的专家，并将它们的输出加权和（softmax权重）作为最终输出。
- **关键技术细节**：
  - 假设使用LoRA作为PEFT方法（但可推广到其他PEFT）。LoRA在每个线性层引入一对低秩矩阵B、A，输出变为 `W u + BA u`。PHATGOOSE在此基础上增加门控向量v，使得输出变为 `W u + BA u · σ(v^T u)`。训练门控时仅更新v，其余参数冻结。
  - 训练门控仅需100步，使用与训练PEFT模块相同的数据集和目标。
  - 推理路由：标准化门控向量和激活向量，计算余弦相似度得分，取top-k（实验中k=2），再softmax缩放权重，得到最终输出。
- **与联合训练（joint training）对比**：单独后训练门控优于同时训练门控和专家模块，原因可能是联合训练导致专家参数适应门控缩放，削弱了跨模块组合能力。

## 3. 实验设计

- **数据集/场景**：
  - 基座模型：LM-adapted T5.1.1 XL（3B参数）。
  - 专家池1：**T0 Held-In**（T0训练所用的36个prompted数据集）。
  - 专家池2：**FLAN**（FLAN集合中的166个零样本prompted数据集）。
  - 零样本评测基准：
    - **T0HO**（T0的held-out数据集，仅用于T0专家池）。
    - **BIG-bench Hard (BBH)**（23个任务，移除1个无法tokenize的任务）。
    - **BIG-bench Lite (BBL)**（24个任务，移除7个无法tokenize的任务）。
- **对比方法**：
  - 满足问题设定（分布式、无数据访问）的基线：**Retrieval**（基于Sentence-BERT查询嵌入检索最相似专家）、**Average Activation**（用平均激活值替代学习到的门控向量）、**Arrow**（用LoRA外积的主右奇异向量作为门控）、**Merged Experts**（简单平均所有LoRA模块）。
  - 不满足问题设定但作为参考：**Multitask**（显式多任务训练，如T0-3B和FLAN-T5 XL）、**Oracle**（任务级别选择性能最好的专家，非零样本）、**Best Individual**（所有任务平均性能最好的专家，非零样本）。
- **评价指标**：在零样本设置下报告准确率（平均）。

## 4. 资源与算力

- 论文**未明确说明**使用了多少GPU型号、数量及训练总时长。但描述了训练细节：
  - 每个LoRA专家：rank=16，训练1000步，batch size 1024（max-length=512序列），AdamW优化器，学习率5e-3，warmup ratio 0.06，每100步验证。
  - 门控训练：额外100步，相同超参数。
- 因此，总计算量相对较小（仅需在每个专家训练后增加100步门控训练），但具体集群算力未披露。

## 5. 实验数量与充分性

- **实验数量**：涵盖两个专家池（36和166个专家）、三个零样本基准（T0HO、BBH、BBL），总共**6个主要实验设置**。在T0 Held-In设置下，与至少8种方法对比；在FLAN设置下，与至少7种方法对比。
- **充分性**：实验设计较为全面，覆盖了同领域主流路由方法、消融（Average Activation、联合训练）、以及不满足设定但提供上界的Oracle和Best Individual。定性分析部分还做了路由分布与Oracle对齐的相关性分析、以及个别案例可视化。
- **公平性**：对比方法均在同一基座模型（LM-adapted T5.1.1 XL）上训练或适用，但Multitask基线（T0-3B和FLAN-T5 XL）使用了不同训练数据集和模型变体，论文对此作了说明并建议谨慎比较，整体公平性较好。

## 6. 主要结论与发现

- PHATGOOSE在**所有符合问题设定的方法中表现最佳**，并且在T0 Held-In设置下，甚至超过了显式多任务训练（T0-3B）和Oracle路由（非零样本上界）。
- **适应令牌级和模块级路由**是性能提升的关键：相比检索单一专家或简单平均，组合多个专家能够更好地泛化。
- **定性分析**显示：PHATGOOSE学习到的路由策略与Oracle路由并不高度相关（Pearson r=-0.2），表明它发现了与Oracle不同的有效组合方式；例如在CB数据集上，PHATGOOSE几乎从不选Oracle专家，但性能反而更高。
- 当专家池从36扩展到166时，PHATGOOSE虽然仍优于其他路由方法，但整体性能提升有限，且在部分知识密集型任务上下降，推测是因为知识记忆任务更依赖特定专家，而推理任务更能从多专家组合中获益。

## 7. 优点

- **方法新颖且实用**：提出post-hoc门控训练，无需同时访问多个数据集，仅需少量额外计算，符合分布式、去中心化模型开发场景。
- **实验设计较全面**：覆盖多种专家池、基准、基线方法，并有消融和定性分析。
- **结果亮眼**：在多个设置下超越现有路由方法，甚至持平或超越多任务训练，说明路由组合专家是零样本泛化的有效途径。
- **可推广性**：适用于任何插入模块的PEFT方法（LoRA、IA³、Adapter等），不要求模块同构。

## 8. 不足与局限

- **专家池扩大后的性能瓶颈**：当专家数增加时，所有路由方法（包括PHATGOOSE）并未获得一致提升，部分任务性能下降，论文未给出有效解决方案。
- **计算资源未详述**：未给出总GPU小时数，难以量化额外开销。
- **实验场景局限**：仅测试了T5系列（encoder-decoder架构），未在更流行的decoder-only LLM（如LLaMA）上验证。
- **超参数选择固化**：top-k固定为2，门控训练步数固定为100，未探讨这些超参数的影响。
- **未处理异构模块**：虽然理论上适用，但实验仅用了同构LoRA（相同rank），异构模块场景下可能面临更多挑战。
- **定性分析深度有限**：仅通过KL散度和两个案例展示路由分布，缺乏更系统的可解释性分析。

（完）
