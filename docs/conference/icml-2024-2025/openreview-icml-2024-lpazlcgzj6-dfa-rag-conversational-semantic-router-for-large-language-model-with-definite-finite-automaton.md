---
title: "DFA-RAG: Conversational Semantic Router for Large Language Model with Definite Finite Automaton"
title_zh: DFA-RAG：基于确定性有限自动机的对话语义路由器
authors: "Yiyou Sun, Junjie Hu, Wei Cheng, Haifeng Chen"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=LpAzlcGzJ6"
tags: ["query:mas-routing"]
score: 4.0
evidence: 使用确定性有限自动机作为语义路由器引导LLM响应，与LLM系统中的路由机制相关
tldr: 传统大语言模型在需要遵守预定指南的场景（如情感支持）中难以生成合规回应。本文提出DFA-RAG框架，通过学习对话数据构建确定有限自动机，嵌入LLM作为语义路由器，引导回复沿确定性路径生成。该方法在保持对话流畅性的同时提高了回复规范性和符合性，展示了结构化的路由机制在LLM对话中的价值。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 742, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1755, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1708, \"height\": 1701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1713, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1715, \"height\": 1930, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1383, \"height\": 1850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1449, \"height\": 1752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lpazlcgzj6/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1566, \"height\": 2127, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-lpazlcgzj6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1717, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-lpazlcgzj6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 833, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-lpazlcgzj6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 561, \"label\": \"Table\"}]"
motivation: LLM在需要遵循预定规则的特殊场景中难以生成合规回复，需要有效的路由机制。
method: 从训练对话中学习确定有限自动机，并将其嵌入LLM作为语义路由器，结合检索增强生成实现路径引导。
result: 实验表明DFA-RAG在情感支持和客服等场景下有效提升了回复的规范性和对话连贯性。
conclusion: 结构化自动机可作为LLM语义路由的有效手段，为受控对话生成提供新思路。
---

## Abstract
This paper introduces the retrieval-augmented large language model with Definite Finite Automaton (DFA-RAG), a novel framework designed to enhance the capabilities of conversational agents using large language models (LLMs). Traditional LLMs face challenges in generating regulated and compliant responses in special scenarios with predetermined response guidelines, like emotional support and customer service. Our framework addresses these challenges by embedding a Definite Finite Automaton (DFA), learned from training dialogues, within the LLM. This structured approach acts as a semantic router which enables the LLM to adhere to a deterministic response pathway. The routing is achieved by the retrieval-augmentation generation (RAG) strategy, which carefully selects dialogue examples aligned with the current conversational context. The advantages of DFA-RAG include an interpretable structure through human-readable DFA, context-aware retrieval for responses in conversations, and plug-and-play compatibility with existing LLMs. Extensive benchmarks validate DFA-RAG's effectiveness, indicating its potential as a valuable contribution to the conversational agent.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机

- **问题**：大语言模型在需要严格遵循预定响应规则（如情感支持、客户服务）的对话场景中，容易生成不合规或误导性内容。
- **动机**：现有方法（如微调）受限于开源需求、过拟合风险，而检索增强生成（RAG）对样本选择敏感，且难以捕捉对话流程中的结构化路径。因此，需要一种既能保持LLM灵活性又能确保合规性的对话路由机制。

## 2. 方法：核心思想与关键技术

- **核心思想**：从训练对话中学习一个确定性有限自动机（DFA），作为语义路由器，引导LLM沿预定路径生成响应，同时利用RAG策略检索与当前上下文对齐的对话示例。
- **关键步骤**：
  1. **标签提取**：使用LLM（如GPT-4）将对话中的每一句话压缩为少量标签（如`#battery #issue`），遵循简洁和聚焦核心元素原则。
  2. **DFA构建**：
     - 将对话转换为带轮次信息的标签序列，按轮次分别构建前缀树。
     - 算法递归地选择当前轮次中最频繁的标签作为分支，处理标签顺序可变性。
     - 通过状态合并（基于相似度得分ϕ_sim，阈值λ=0.1）减少冗余，形成最终DFA。
  3. **DFA引导的生成**：
     - 用户输入先由LLM转换为标签。
     - 在DFA上导航至匹配状态，若δ(q,u)=∅则退回上一有效状态。
     - 从状态关联的对话ID集合中随机选取最多5个示例，构造提示模板进行上下文学习。
- **公式**：状态相似度ϕ_sim(q,q') = [∑_{t∈T(q)∩T(q')} |I(δ(q,t))|·|I(δ(q',t))|] / [∑_{t∈T(q)} |I(δ(q,t))| · ∑_{t∈T(q')} |I(δ(q',t))|]，其中I()返回经过该状态的对话ID集合。

## 3. 实验设计

- **数据集**：六组领域对话数据集
  - Twitter来源：AmazonHelp（50K）、DeltaSupport（20K）、AskPlayStation（10K）、AirbnbHelp（3K）、NikeSupport（1K）
  - MultiWOZ来源：CambridgeInfo（8K），包含多领域任务（火车、出租车、酒店等）
- **基准方法**：
  - 生成质量评估：随机采样（RandSamp）、BM25稀疏检索、RAG（text-embedding-3-small）、FT-LLM（直接微调）、DFA-RAG（本文方法）
  - 任务导向对话评估：与两类基线对比——基于对话状态的方法（HDSA、MarCo等）和端到端方法（AuGPT、MTTOD等）
- **评估指标**：生成质量采用GPT-4评判的“胜率”（Win Rate）；任务完成采用“Inform”率和“Success”率。

## 4. 资源与算力

论文未明确说明使用的GPU型号、数量或训练时长。仅提及使用GPT-4和GPT-3.5的API（gpt-4-1106-preview和gpt-3.5-turbo-1106）进行推理和评估，微调基线（FT-LLM）通过OpenAI API完成，未报告具体算力开销。

## 5. 实验数量与充分性

- **生成质量实验**：在两个基础模型（GPT-4、GPT-3.5）上，对6个数据集各比较6种方法，共6×6×2=72组对比，报告平均胜率。
- **任务导向实验**：在MultiWOZ数据集上比较了10种基线方法，报告Inform和Success率。
- **消融与分析**：提供了DFA可视化（图5、附录D）、对话生成示例（附录C）以及状态合并阈值的设置说明。
- **充分性评价**：实验覆盖多个领域、不同规模数据集，对比方法全面（包括RAG变体、微调、任务导向系统），且采用GPT-4作为客观评判器（与人类评估一致性85%），实验设计较为充分和公平。但缺少对超参数（如构建DFA的阈值τ=5）的灵敏度分析，且未进行人工评估验证。

## 6. 主要结论与发现

- DFA-RAG在生成质量上优于所有基线：在GPT-4上平均胜率74.3%，GPT-3.5上75.9%，均高出最佳基线（RAG）约4个百分点。
- 在任务导向对话中，DFA-RAG取得Inform 93.3%、Success 90.0%，与使用真实对话状态的最优方法（MarCo）相当，且优于所有端到端方法。
- 微调（FT-LLM）因数据量不足表现不佳，RAG优于随机采样和BM25，但DFA-RAG通过结构化路由进一步提升。

## 7. 优点

- **可解释性**：DFA结构人类可读，可直观展示对话流程。
- **上下文感知检索**：按对话轮次和标签路径分段检索，而非将整段对话作为整体，更精准。
- **即插即用**：可与任意预训练LLM（如GPT-3.5、GPT-4）直接集成，无需重新训练。
- **处理OOD输入**：当用户输入不匹配DFA路径时，回退至最近有效状态仍能生成相关响应，增强了鲁棒性。

## 8. 不足与局限

- **算力未报告**：缺少训练和推理的GPU资源、时间细节，不利于复现和资源估算。
- **超参数敏感度未知**：未分析阈值τ（构建树的最小ID数）、λ（状态合并）以及示例数量（5）对性能的影响。
- **标签提取依赖LLM**：使用GPT-4提取标签，其本身可能引入噪声或偏差，且成本较高。
- **领域假设限制**：方法假设对话中存在明确的工作流（DFA），在完全无结构或高度动态的对话中可能失效。
- **人工评估缺失**：虽然GPT-4评估者与人类一致性高，但未直接进行人工评估验证。
- **对比基线有限**：在任务导向对话中未与最新端到端模型（如TOATOD后续工作）直接比较；生成质量评估仅使用胜率，未使用其他自动指标（如BLEU、ROUGE）。

（完）
