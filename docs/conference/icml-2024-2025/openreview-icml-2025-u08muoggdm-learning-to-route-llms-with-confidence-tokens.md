---
title: Learning to Route LLMs with Confidence Tokens
title_zh: 学习使用置信度令牌路由大模型
authors: "Yu-Neng Chuang, Prathusha Kameswara Sarma, Parikshit Gopalan, John Boccio, Sara Bolouki, Xia Hu, Helen Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=U08mUogGDM"
tags: ["query:mas-routing"]
score: 6.0
evidence: 基于置信度的大模型路由
tldr: 针对高敏感场景下大模型输出可靠性未知的问题，Self-REF通过轻量训练使模型能够表达对自身答案的置信度。基于置信度，系统可以智能地将问题路由到其他专家或执行安全回退。实验表明该方法在多项任务中提升了整体准确率，为构建自适应路由系统提供了实用工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-u08muoggdm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1667, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u08muoggdm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u08muoggdm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u08muoggdm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u08muoggdm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 326, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1641, \"height\": 1366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1646, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u08muoggdm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 672, \"height\": 246, \"label\": \"Table\"}]"
motivation: 高敏感场景下需要知道大模型输出何时不可靠。
method: 训练模型生成置信度令牌，结合误差反馈进行自我反思。
result: 在多个基准上路由决策提升了整体准确率。
conclusion: 置信度学习可有效指导大模型路由与故障恢复。
---

## Abstract
Large language models (LLMs) have demonstrated impressive performance on several tasks and are increasingly deployed in real-world applications. However, especially in high-stakes settings, it becomes vital to know when the output of an LLM may be unreliable. Depending on whether an answer is trustworthy, a system can then choose to route the question to another expert, or otherwise fall back on a safe default behavior. In this work, we study the extent to which LLMs can reliably indicate confidence in their answers, and how this notion of confidence can translate into downstream accuracy gains. We propose Self-Reflection with Error-based Feedback (Self-REF), a lightweight training strategy to teach LLMs to express confidence in whether their answers are correct in a reliable manner. Self-REF introduces confidence tokens into the LLM, from which a confidence score can be extracted. Compared to conventional approaches such as verbalizing confidence and examining token probabilities, we demonstrate empirically that confidence tokens show significant improvements in downstream routing and rejection learning tasks.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）在关键任务（如医疗、法律）中的输出可靠性难以保证，需要一种机制让系统判断何时输出不可信，进而将问题路由到更强的模型或选择拒绝回答（安全默认行为）。现有方法如基于token概率的置信度估计或提示模型“语言化”置信度，往往不稳定或与真实正确率对齐较差。
- **整体含义**：本文旨在训练LLM自身生成可靠的置信度指示，使得下游系统能够根据置信度做出更优的路由或拒绝决策，从而提升整体系统的准确率、效率和安全性。

## 2. 论文提出的方法论

- **核心思想**：Self-Reflection with Error-based Feedback (Self-REF)，一种轻量级微调策略，通过引入两个特殊token（`<CN>`表示自信，`<UN>`表示不自信）来让LLM表达对自身答案的置信度。
- **关键技术细节**：
  1. **置信度令牌标注**：使用基础LLM对每个训练样本进行预测，根据预测是否正确，在答案后附加`<CN>`（正确）或`<UN>`（错误）token，形成增强训练数据。
  2. **Self-REF微调**：在增强数据上微调模型，训练目标包括：增加正确样本中`<CN>`的概率、错误样本中`<UN>`的概率，以及正确答案的概率。同时，对错误样本中错误答案部分的梯度进行掩码（避免增加错误答案的概率）。
  3. **置信度分数提取**：推理时，计算`<CN>` token概率除以`<CN>`+`<UN>`概率之和，得到连续置信度分数c∈[0,1]。
- **与下游任务结合**：基于阈值t，对于置信度低于t的样本，执行路由（发送给更大模型）或拒绝（不回答）。

## 3. 实验设计

- **数据集**：四个公开数据集
  - MMLU（多任务语言理解）
  - OpenbookQA（开放书籍问答）
  - GSM8K（小学数学题）
  - MedQA（医学考题）
- **场景**：
  1. **置信度路由**：本地小模型（Llama3-8B-Instruct / Mistral-7B-Instruct）进行预测，根据置信度将不确定的样本路由到更大模型（Llama3-70B-Instruct）。
  2. **拒绝学习**：构造评估集（50%样本移除正确答案），测试模型根据置信度选择是否拒绝回答（即标记为“None of the above”）。
- **对比方法**：
  - Verbalizing Uncertainty（提示模型输出置信度）
  - Verbalizing Yes/No Tokens（提示模型输出Yes/No，归一化概率）
  - Zero-shot Logits（无微调的logit概率）
  - Fine-tuned Logits（微调后的logit概率）
  - Random Route（随机路由基线）

## 4. 资源与算力

- **GPU型号**：8块Nvidia A100 GPU（80GB显存）
- **训练时间**：不同数据集和模型训练时间约为0.5~4小时（如MMLU上约4小时，OpenbookQA上约1小时）
- **微调方法**：使用LoRA适配器，秩设为2、4、8，仅对QKV层、token嵌入层和最终线性层进行参数高效微调。

## 5. 实验数量与充分性

- **实验组数**：
  - 路由任务：2种本地模型 × 4个数据集 × 多个阈值（约21个路由率水平） × 3种LoRA秩 = 大量曲线对比；另外还包含转移性实验（精调于OpenbookQA，测试于MMLU）和梯度掩码消融实验。
  - 拒绝学习任务：2种模型 × 2个数据集（MMLU和OpenbookQA），绘制ROC曲线。
  - 校准分析：使用ECE、Brier Score、Cross-Entropy三种指标对比所有方法。
  - 案例研究：提供正例和反例。
- **充分性评估**：实验设计较为完善，覆盖了路由、拒绝、校准、消融、转移性等多个维度。对比基线全面。但可能缺少在更多模型规模（如更大或更小）上的验证，以及不同路由目标模型（除Llama3-70B外）的泛化性测试。

## 6. 论文的主要结论与发现

- Self-REF在路由任务上一致优于所有基线，能以更低的路由率达到与Llama3-70B相当的准确率（例如MMLU上仅路由39%即可达到同等表现，延迟提升2.03倍）。
- 在拒绝学习任务中，Self-REF的ROC曲线面积最大，即能更好地区分哪些问题应当被拒绝。
- 校准指标（ECE等）上Self-REF通常表现最好或第二好，但校准最优不一定对应最好路由效果。
- 梯度掩码对路由性能有益；Self-REF的置信度表现出良好的跨数据集迁移能力（在OpenbookQA上训练，在MMLU上仍有竞争力）。

## 7. 优点

- **轻量级、通用性**：Self-REF仅需额外添加两个token进行LoRA微调，无需修改损失函数或额外分类器，可即插即用于任何LLM。
- **动态条件置信度**：置信度基于模型自身生成的答案（而非仅基于输入查询），更准确反映预测正确性。
- **实用价值高**：同时支持路由和拒绝两种下游应用，能有效降低成本、提升系统安全性和效率。
- **实验全面**：涵盖多数据集、多模型（8B/7B vs 70B）、多基线、消融和迁移分析，结论可靠。

## 8. 不足与局限

- **实验覆盖局限**：仅使用Llama3-70B作为路由目标，未测试其他更强模型（如GPT-4）或混合路由场景；路由目标模型未进行微调（受限于资源）。
- **校准与路由效果的弱关联**：作者指出校准好不一定路由好，但未深入解释原因或提出改进。
- **依赖训练数据**：置信度学习需要正确的答案标签，且需要足够多的错误样本，否则可能导致过拟合。
- **拒绝学习评估集构造**：仅通过移除正确答案来构造“无正确选项”样例，可能与真实场景中的拒绝需求有偏差。
- **网络传输成本未考虑**：只计算了GPU时长和延迟，未考虑不同机器间通信开销（可能影响实际路由节省）。
- **未探索细粒度或连续置信度**：目前只有两个离散token，未来可扩展为更细粒度的置信度表达。

（完）
