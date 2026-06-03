---
title: "RAGRouter: Learning to Route Queries to Multiple Retrieval-Augmented Language Models"
title_zh: RAGRouter：学习将查询路由到多个检索增强语言模型
authors: "Jiarui Zhang, Xiangyu Liu, Yong Hu, Chaoyue Niu, Fan Wu, Guihai Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4VKVUmE1I8"
tags: ["query:mas-routing"]
score: 9.0
evidence: 直接路由查询到多个RAG模型以选择最优
tldr: 针对检索增强生成中不同LLM回答质量差异的问题，本文正式定义检索增强LLM路由问题，提出RAGRouter模型，利用检索文档动态调整路由策略。实验证明RAGRouter优于静态路由方法，为LLM路由提供了直接解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 712, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 721, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1427, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4vkvume1i8/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1409, \"height\": 1140, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 595, \"height\": 558, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 1130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 589, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1303, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1045, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 915, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1175, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1072, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1438, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1438, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1095, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 544, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4vkvume1i8/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1442, \"height\": 346, \"label\": \"Table\"}]"
motivation: 不同LLM在RAG场景下响应质量不一，需要智能路由选择最优模型。
method: 提出RAGRouter，专用路由模型，根据查询和检索文档动态选择最合适的检索增强LLM。
result: 在知识密集型任务上，RAGRouter相比静态路由方法取得更高准确率。
conclusion: 动态文档感知的路由能显著提升多LLM系统的整体性能。
---

## Abstract
Retrieval-Augmented Generation (RAG) significantly improves the performance of Large Language Models (LLMs) on knowledge-intensive tasks. However, varying response quality across LLMs under RAG necessitates intelligent routing mechanisms, which select the most suitable model for each query from multiple retrieval-augmented LLMs via a dedicated router model. We observe that external documents dynamically affect LLMs' ability to answer queries, while existing routing methods, which rely on static parametric knowledge representations, exhibit suboptimal performance in RAG scenarios. To address this, we formally define the new retrieval-augmented LLM routing problem, incorporating the influence of retrieved documents into the routing framework. We propose RAGRouter, a RAG-aware routing design, which leverages document embeddings and RAG capability embeddings with contrastive learning to capture knowledge representation shifts and enable informed routing decisions. Extensive experiments on diverse knowledge-intensive tasks and retrieval settings, covering open and closed-source LLMs, show that RAGRouter outperforms the best individual LLM and existing routing methods. With an extended score-threshold-based mechanism, it also achieves strong performance-efficiency trade-offs under low-latency constraints. The code and data are available at https://github.com/OwwO99/RAGRouter.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 一、核心问题与整体含义（研究动机与背景）

- **研究动机**：检索增强生成（RAG）通过注入外部知识显著提升大语言模型（LLM）在知识密集型任务上的表现，但不同LLM在利用相同检索文档时表现出巨大的异质性（如在信息提取、整合和抗噪能力上差异明显）。传统的LLM路由方法仅依赖静态参数知识表示（假设LLM知识固定），无法捕获检索文档带来的动态知识转移，导致在RAG场景下路由决策失效。
- **核心问题**：如何有效将查询路由到多个检索增强LLM中最合适的那个，即定义并解决“检索增强LLM路由问题”，将检索文档的影响显式纳入路由框架。
- **整体含义**：提出首个RAG感知的路由方法RAGRouter，通过建模文档、查询与LLM能力的动态交互，实现超越单一最优模型和现有静态路由方法的性能，同时支持延迟约束下的效率-性能权衡。

## 二、方法论：核心思想、关键技术细节与流程

- **核心思想**：RAG场景下LLM的有效知识由参数知识（静态）和文档融合知识（动态）组成：`v'_k = v_k + v_f`。路由应基于查询与更新后知识表示的相似度，而非仅依赖静态表示。RAGRouter显式建模融合知识`v_f`，由文档、LLM的RAG能力、查询-文档交互三部分通过注意力机制融合得到。
- **架构设计**：
  - **查询编码器**（共享参数）与**文档编码器**：将查询和文档分别编码为向量`v_q`、`v_d`。
  - **交叉编码器**：编码查询-文档对，得到交互表示`v_c`。
  - **LLM知识嵌入层**：根据模型ID生成参数知识向量`v_k`。
  - **RAG能力嵌入层**：生成对应每个LLM的RAG能力向量`v_r`（可学习）。
  - **多头部注意力**：将`v_r`、`v_d`、`v_c`融合得到`v_f`，再与`v_k`相加得更新知识表示`v'_k`。
  - **路由决策**：选取与查询向量`v_q`相似度最高的候选模型。
- **优化策略**：
  - **对比学习**：以查询为锚点，构建正负样本集合。跨设置对比（CSC）从非RAG和RAG设置中选取；设置内对比（ISC）在同一设置内不同模型间选取。损失函数为InfoNCE + 温度参数τ。
  - **分类损失**：对每个模型（非RAG和RAG）计算Sigmoid相似度与真实标签的二元交叉熵损失。
  - **总损失**：`L = L_CT + λ * L_CLS`（λ=2.0，τ=0.2）。
  - 使用预训练编码器（all-mpnet-base-v2、ms-marco-MiniLM-L12-v2），冻结除最后两层的所有Transformer层以防过拟合。
- **延迟感知扩展**：引入分数阈值机制，允许用较小模型替换路由选中的最优大模型（若分数差≤θ），在牺牲微小准确率下大幅降低延迟。

## 三、实验设计：数据集、基准与对比方法

- **数据集**（5个知识密集型任务）：
  - PopQA（开放域问答，在线/本地检索）
  - MedMCQA（医学选择题，在线/本地）
  - Natural Questions（NQ，基于Wikipedia，人工添加噪声）
  - WebQuestions（WebQ，基于Freebase，添加噪声）
  - TriviaQA（TQA，事实型，添加噪声）
  - 另在跨域设置（MedMCQA→HotpotQA、NQ→MedMCQA）及摘要任务WikiASP上验证泛化性。
- **候选LLM**：15个主流模型，参数规模0.5B~72B（Qwen2.5系列、Llama-3系列、gemma-2、Yi-1.5、Ministral等），外加闭源模型Qwen2.5-Max、GPT-4o、DeepSeek-R1。
- **检索设置**：
  - PopQA/MedMCQA：本地检索（BGE-large-en-v1.5 + 2018 Wikipedia转储）和在线检索（DuckDuckGo API）。
  - NQ/WebQ/TQA：基于Wikipedia构造带四类噪声（黄金、相关、无关、反事实）的检索上下文。
- **对比方法**：
  - 单LLM基线（15个分别测试）、Oracle Single Best、随机、加权
  - 非RAG感知路由方法：Prompt LLM（GPT-4o元提示）、GraphRouter、RouterDC、KNN Router、矩阵分解（MF）
  - Oracle（理论上限，按每个查询选择正确模型）
- **评估指标**：准确率（Cover Exact Match），延迟感知路由另用Area、Peak Acc、Latency Gap-to-Match。

## 四、资源与算力

- **硬件**：单张 NVIDIA RTX 4090D GPU（24GB显存）。
- **架构参数**：路由器模型约136M参数（编码器+交叉编码器+嵌入层）。
- **训练设置**：优化器AdamW，学习率5e-5，batch size 64，训练10个epoch。
- **推理开销**：峰值GPU显存4147 MiB，平均推理时间0.011秒/实例（batch size 64）。
- **注**：论文未提及具体训练总时长，但基于单卡10 epoch可推断训练较快（约数小时量级）。

## 五、实验数量与充分性

- **实验组数**：
  - **主实验（表2）**：7个任务/检索设置下，对比13种方法（15个LLM+5种路由+规则+Oracle），报告准确率。
  - **闭源LLM实验（表3）**：额外3个闭源模型，2个数据集。
  - **延迟感知实验（表4、图4、图10）**：5个任务，每种方法扫描阈值生成曲线，报告Area/Peak Acc/Gap。
  - **消融实验**：架构组件（表5）、对比学习策略（表6）、嵌入维度（图5/表10）、分类损失权重λ（图6/表11）、候选模型集大小（表7）。
  - **跨域实验（表15）**：2个迁移设置。
  - **噪声鲁棒实验（表16）**：TriviaQA 4种子集。
  - **摘要任务实验（表17）**：WikiASP。
- **充分性评价**：实验覆盖广泛，涉及多种任务类型、检索场景、模型规模、路由策略，消融设计完整，对比方法均为现有代表性工作，整体公平客观。但论文自身承认未报告误差条（因计算成本高），且未在非常大规模候选集（>20）上测试，也未讨论模型选择和训练数据偏差的影响。

## 六、主要结论与发现

- RAGRouter在所有任务上平均准确率64.46%，超过最佳单LLM（Llama-3.3-70B，60.85%）3.61%，超过Oracle Single Best（每数据集选最优模型）3.24%，证明多模型路由可协同超越任何单一模型。
- 显著优于所有非RAG感知路由方法（GraphRouter 61.17%、MF 60.25%、KNN Router 60.44%、RouterDC 56.71%），证实建模文档与RAG能力的关键性。
- 引入闭源强模型后，RAGRouter仍优于最强模型GPT-4o（+1.67%），且仅需调用GPT-4o约44.79%查询，提升效率。
- 延迟感知机制下，RAGRouter的准确率-延迟曲线主导所有基线，在低延迟约束下获得最佳Area和Peak Acc，并能以更小延迟匹配最优单模型性能。
- 跨域、噪声检索、摘要任务上均取得一致优势，体现良好泛化性和鲁棒性。

## 七、优点

1. **问题定义创新**：首次正式定义检索增强LLM路由问题，推动RAG场景下多模型协同研究。
2. **架构设计合理**：显式分离参数知识（v_k）和融合知识（v_f），通过文档编码、交叉编码和RAG能力嵌入捕捉动态转移，符合直觉。
3. **优化策略有效**：结合跨设置和设置内对比学习，精准建模RAG导致的应答能力翻转（Positive Gain / Negative Interference），消融证实每一步均有收益。
4. **轻量高效**：路由器仅136M参数，单卡推理微秒级，易于部署；支持延迟-性能灵活权衡。
5. **实验充分全面**：覆盖多种任务、检索模式、模型尺寸（含闭源）、噪声环境、跨域迁移，验证鲁棒性和通用性。

## 八、不足与局限

1. **未报告统计显著性**：论文指出因计算成本未给出误差条，结果可能受单次运行随机性影响。
2. **候选模型数量有限**：主实验仅15个开源+3个闭源模型，更大规模候选集（如数十至上百）下的可扩展性未测试。
3. **依赖标注响应数据**：训练需对所有候选LLM在每对（查询,文档）上生成响应并标注，获取成本较高；对新加入的LLM需要重新标注或微调。
4. **任务覆盖有限**：主要聚焦知识型问答和摘要，未涉及对话、推理、代码生成等场景，RAG能力异质性可能不同。
5. **未讨论公平性与偏见**：路由可能隐含对不同模型（如闭源与开源）的偏好，未分析潜在偏差或安全风险。
6. **默认所有模型可访问**：实际部署中部分闭源模型可能有API成本或访问限制，路由策略需额外考虑成本模型（仅延迟约束）。
7. **缺乏理论分析**：对比学习的收敛性质、路由错误边界等理论保证未提供。

（完）
