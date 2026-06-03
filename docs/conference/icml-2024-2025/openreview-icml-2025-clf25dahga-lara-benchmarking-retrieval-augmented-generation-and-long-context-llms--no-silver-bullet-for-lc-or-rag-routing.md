---
title: "LaRA: Benchmarking Retrieval-Augmented Generation and Long-Context LLMs – No Silver Bullet for LC or RAG Routing"
title_zh: LaRA：检索增强生成与长上下文LLM的基准测试——长上下文或RAG路由没有银弹
authors: "Kuan Li, Liwen Zhang, Yong Jiang, Pengjun Xie, Fei Huang, Shuai Wang, Minhao Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CLF25dahgA"
tags: ["query:mas-routing"]
score: 6.0
evidence: RAG与长上下文选择基准，适用于多智能体LLM系统中的任务路由
tldr: 在LLM上下文窗口扩展的背景下，RAG与长上下文的选择存在争议。LaRA基准通过2326个测试案例、四种问答任务和三种长上下文类型，系统评估了11个LLM，揭示了最优选择取决于模型能力、上下文长度和任务类型等复杂因素。该工作为多智能体LLM架构中的高效任务路由（如选择检索或长上下文）提供了可操作指南。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-clf25dahga/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 467, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 1344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1094, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-clf25dahga/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1142, \"height\": 194, \"label\": \"Table\"}]"
motivation: RAG与长上下文LLM的优劣对比不明，缺乏系统基准来指导任务路由决策。
method: 构建LaRA基准，包含2326个测试案例，覆盖多种任务和上下文类型，评估11个LLM。
result: 最优路由策略依赖于模型能力、上下文长度和任务特性等多种因素。
conclusion: 为多智能体系统中的任务路由（如RAG vs 长上下文选择）提供了实用指导。
---

## Abstract
As Large Language Model (LLM) context windows expand, the necessity of Retrieval-Augmented Generation (RAG) for integrating external knowledge is debated. Existing RAG vs. long-context (LC) LLM comparisons are often inconclusive due to benchmark limitations. We introduce LaRA, a novel benchmark with 2326 test cases across four QA tasks and three long context types, for rigorous evaluation. Our analysis of eleven LLMs reveals the optimal choice between RAG and LC depends on a complex interplay of model capabilities, context length, task type, and retrieval characteristics, offering actionable guidelines for practitioners. Our code and dataset is provided at:https://github.com/Alibaba-NLP/LaRA

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：随着LLM上下文窗口不断扩大（如GPT-4o、Llama 3.2等支持128k tokens），是否仍有必要使用检索增强生成（RAG）来引入外部知识成为争议焦点。现有RAG与长上下文（LC）LLM的对比研究结论不一致——有的认为RAG更优，有的认为LC全面优于RAG。这种分歧源于评估基准存在缺陷：上下文长度不足、数据泄露、不当的上下文截断处理、评估指标不可靠（如F1、EM不适用于自然语言生成）以及缺乏专门为RAG vs LC设计的基准。
- **整体含义**：该研究旨在通过构建高质量的基准LaRA，系统揭示RAG与LC在不同条件下的优劣关系，为实际应用中的路由决策（选择RAG还是直接输入全文）提供可操作的指南，强调不存在适用于所有场景的“银弹”。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：构建一个自然、长文本、无数据泄露、答案确定且贴近真实需求的问答基准，在此基础上系统比较RAG与LC在多种模型、上下文长度、任务类型下的表现。
- **关键技术细节**：
  - **上下文来源**：选用三种自然长文本——小说（古登堡计划）、财务报告（2024年上市公司季报/年报）、学术论文（arXiv 2024年引用链拼接）。长度分别贴近32k和128k tokens。
  - **实体替换**：针对可能训练数据泄露的小说，使用GPT-4o识别并替换人物实体为虚构名，保证问答内容不在训练集中。
  - **任务设计**：包含四类任务——定位（Location）、推理（Reasoning）、比较（Comparison）、幻觉检测（Hallucination detection）。每类任务针对不同上下文类型设计不同的种子问题，通过GPT-4o以语境学习方式生成Q&A对，并进行多轮人工校验（采样40个，通过率≥90%）。
  - **分段生成**：为避免LLM生成时“lost in the middle”，将长文本分割为约10k tokens的片段分别生成Q&A，确保答案均匀分布于全文。
  - **评估方式**：使用GPT-4o作为评判者（judge），将查询、标准答案、模型预测输入GPT-4o判断正确性。计算Cohen’s Kappa系数（人工与LLM评价的一致性），证明评估可靠（系数接近1）。

## 3. 实验设计
- **数据集/场景**：
  - 基准：LaRA，包含2326个测试用例。
  - 上下文长度：32k（20-30k tokens）和128k（80-120k tokens）两个级别。
  - 任务：定位（Location，共276+489条）、推理（Reasoning，共230+374条）、比较（Comparison，共151+198条）、幻觉检测（Hallucination，共230+378条）。
  - 上下文类型：小说、财务报告、学术论文。
- **对比方法**：
  - 11个LLMs：开源——Llama-3.1-8B-Instruct, Llama-3.2-3B-Instruct, Llama-3.3-70B-Instruct (含Q8量化), Qwen-2.5-7B-Instruct, Qwen-2.5-72B-Instruct, Mistral-Nemo-12B；闭源——GPT-4o, GPT-4o-mini, Claude-3.5-Sonnet, Gemini-1.5-Pro。
  - RAG实现：块大小600 tokens，每个文档返回5个块，重叠100 tokens；使用GTE-large-en-v1.5嵌入和重排序；混合搜索（嵌入相似度+BM25）。
- **评估指标**：GPT-4o评判正确率（Accuracy）。

## 4. 资源与算力
- 论文中**未明确说明**使用的GPU型号、数量、训练时长等算力细节。仅提到实验使用上述11个模型进行推理（非训练），RAG系统使用通用配置。可推测主要依赖闭源API（OpenAI、Anthropic、Google）以及开源模型的推理部署，但未量化。

## 5. 实验数量与充分性
- **实验数量**：覆盖4种任务 × 2种上下文长度 × 3种上下文类型 × 11个模型，主实验共产生约 4×2×3×11 = 264 个组合（每个组合有多个测试用例）。此外还进行了：不同块数量（5/10/15/20/25/30）和块大小（200/400/600/800/1000/2000）的消融实验（图2），以及对“lost in the middle”的定位/推理任务位置分析（图6）。
- **充分性与公平性**：
  - **优点**：实验规模较大，系统性地控制了上下文长度、任务类型、模型规模等变量，消融实验探究了RAG关键参数影响。采用了LLM-as-judge并验证了与人类评价的高一致性，避免传统指标偏差。
  - **潜在不足**：RAG配置（块大小、数量、检索策略）固定为一种常见设置，未探索不同检索器或重排序器的影响（论文中说明尝试替换嵌入模型等但影响不大）。未考虑RAG中的文档重排序、查询重写等高级策略。仅使用GPT-4o作为单一评判者，可能引入偏好偏差。未对不同模型在不同上下文类型上的表现差异做统计显著性检验。

## 6. 论文的主要结论与发现
- **模型强度**：RAG对较弱模型的提升更显著（如128k下，RAG在Llama-3.2-3B上提升6.48%，在Mistral-Nemo-12B上提升38.12%）；强模型（GPT-4o, Claude-3.5）更适合LC。
- **上下文长度**：当上下文从32k增至128k时，LC性能下降更严重，RAG的优势更加明显（32k时LC平均高2.4%，128k时RAG平均高3.68%）。
- **任务性能**：
  - 定位任务：两者差距小；长上下文下RAG略优。
  - 推理任务：强模型LC更优（能利用全局信息），弱模型RAG更优。
  - 比较任务：LC显著优于RAG（平均差距14-15%），因为RAG难以同时检索到需要比较的两个部分。
  - 幻觉检测：RAG全面优于LC（LC易受噪声干扰产生幻觉），且模型大小对幻觉检测无明显优势。
- **上下文类型**：小说最难，论文最容易；结构化的文本（论文、财报）下LC优势更明显，非结构化文本（小说）下RAG是可行选择。
- **块数量与大小**：大模型性能随块数量增加而提升；小模型在中等块数量时达到峰值。块大小影响小于块数量。
- **“Lost in the middle”**：LC模型在答案位于中间时准确率下降，RAG则不受位置影响。

## 7. 优点
- **基准设计全面且严谨**：
  - 使用自然长文本，避免人工拼接；实体替换防止数据泄露；长度接近真实LLM上下文窗口上限。
  - 任务贴近真实用户需求（如定位、推理、比较、拒绝回答），而非仅“大海捞针”。
  - 分段生成Q&A确保答案均匀分布，克服“lost in the middle”带来的标注偏差。
  - 采用LLM-as-judge并通过Cohen’s Kappa验证一致性。
- **实验分析深入**：不仅给出主结果，还系统分析了模型强度、上下文长度、任务类型、上下文类型、块数量/大小、答案位置等多个因素的影响，结论可操作性强。
- **规模较大**：11个模型、2326个用例，覆盖常见闭源/开源模型，具有代表性。

## 8. 不足与局限
- **RAG配置固定**：仅采用一种检索策略（块大小600，5块），未探索更优的RAG流水线（如迭代检索、查询重写、自适应分块等）。这些改进可能改变对比结果。
- **评估依赖单一LLM**：仅使用GPT-4o作为评判者，可能存在偏差。虽然验证了与人工一致性，但未使用多个法官或校准方法。
- **上下文类型有限**：仅三种（小说、财报、论文），未覆盖技术文档、对话、法律法规等更丰富场景。
- **未考虑多文档RAG**：LaRA的上下文是单一长文档（或引用链拼接的论文集），而非多文档融合场景。实际中RAG常用于多源检索。
- **无统计显著性检验**：报告精确数值但未提供置信区间或显著性检验，部分优势（如0.15%的提升）可能不显著。
- **闭源模型评估不确定性**：GPT-4o等可能在训练时接触过类似问题（尽管LaRA采用2024年后新文档及实体替换，但仍不能完全排除），评估公平性存在潜在风险。
- **应用限制**：结论基于问答任务，不直接适用于生成式、对话式等更开放任务。实际系统还需考虑延迟、成本等因素（论文未量化）。

（完）
