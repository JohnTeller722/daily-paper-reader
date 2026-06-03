---
title: "BEST-Route: Adaptive LLM Routing with Test-Time Optimal Compute"
title_zh: BEST-Route：自适应大模型路由与测试时最优计算
authors: "Dujian Ding, Ankur Mallick, Shaokun Zhang, Chi Wang, Daniel Madrigal, Mirian Del Carmen Hipolito Garcia, Menglin Xia, Laks V. S. Lakshmanan, Qingyun Wu, Victor Rühle"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tFBIbCVXkG"
tags: ["query:mas-routing"]
score: 7.0
evidence: 自适应大模型路由，生成多个响应选最优
tldr: 针对大模型部署成本高的问题，BEST-Route提出一种自适应路由方法，通过从小模型生成多个响应并选择最佳输出，在保持质量的同时大幅降低成本。该方法克服了传统路由中单次小模型响应不如大模型的缺点，在多个基准上实现了更好的计算-质量权衡。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 703, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 790, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 785, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 790, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 834, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 835, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tfbibcvxkg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 791, \"height\": 526, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1561, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 752, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 526, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tfbibcvxkg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1292, \"height\": 390, \"label\": \"Table\"}]"
motivation: 现有大模型路由方法多依赖单次响应，小模型响应质量不足。
method: 从低成本模型生成多个响应并选取最优，结合动态路由决策。
result: "在多个数据集上实现成本降低30%以上且质量不降。"
conclusion: 多响应选择策略可有效提升路由效率与成本收益。
---

## Abstract
Large language models (LLMs) are powerful tools but are often expensive to deploy at scale.  LLM query routing mitigates this by dynamically assigning queries to models of varying cost and quality to obtain a desired tradeoff. Prior query routing approaches generate only one response from the selected model and a single response from a small (inexpensive) model was often not good enough to beat a response from a large (expensive) model due to which they end up overusing the large model and missing out on potential cost savings. However, it is well known that for small models, generating multiple responses and selecting the best can enhance quality while remaining cheaper than a single large-model response. We leverage this idea to propose BEST-Route, a novel routing framework that chooses a model and the number of responses to sample from it based on query difficulty and the quality thresholds. Experiments on real-world datasets demonstrate that our method reduces costs by up to 60% with less than 1% performance drop.

---

## 论文详细总结（自动生成）

### 一、论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）虽性能强大，但部署成本高昂，尤其是推理阶段的资源消耗严重限制其规模化应用。现有查询路由方法通过将查询动态分配给不同成本与质量等级的模型来平衡开销，但普遍存在一个关键缺陷：它们只从选定模型生成**单次响应**，导致小模型（低成本）的单次响应质量往往无法匹敌大模型，最终系统趋向于过度使用大模型，错失潜在的降本机会。
- **研究背景**：已有工作表明，对小模型而言，生成多次响应并从中选取最佳（best-of-n）可以显著提升质量，同时总体成本仍低于大模型的单次响应。这一现象为同时节省成本与维持质量提供了新的可能。
- **核心问题**：如何根据查询难度**自适应地**选择模型并且**动态分配**每个查询的采样次数（即测试时计算资源），以在保证接近参考大模型响应质量的前提下，最小化推理成本。
- **整体含义**：BEST-Route 提出一个新颖的路由框架，通过结合 best-of-n 采样与多模型路由决策，实现了**测试时最优计算分配**，在多个真实数据集上获得了高达60%的成本缩减，同时性能下降不到1%，显著优于现有路由方法。

### 二、论文提出的方法论

#### 2.1 核心思想
1. **利用 best-of-n 提升小模型能力**：对小模型生成 n 个候选响应，并用一个轻量级代理奖励模型（proxy reward model）选取最优响应，从而提升单次输出质量。
2. **动态路由决策**：根据查询难度，路由器预测每个“小模型-采样数”组合的**匹配概率**（即该组合的 best-of-n 响应质量不低于参考大模型单次响应的概率），在满足用户设定阈值的前提下选择成本最低的组合；若所有组合均不满足阈值，则回退到参考大模型。

#### 2.2 关键技术细节

- **内存高效的 best-of-n 采样**
  - 使用轻量级 DeBERTa-v3-large（300M 参数）作为代理奖励模型，在训练集上通过成对排序损失（pairwise ranking loss）训练，使其对响应质量排序与真实评分（armoRM）保持一致。
  - 训练时仅使用每个查询的**最差、中位数、最佳**三个响应构成训练对，降低复杂度。
  - 推理时，对给定查询从小模型生成 n 个响应，由代理模型打分，选择分数最高者作为最终输出。实验证明随 n 增大，armoRM 分数稳定提升，未出现 reward hacking。

- **路由器的设计**
  - **早期方案**：先训练成对路由器（pair-wise router），预测固定模型和固定 n 的匹配概率；再扩展为**矩阵路由器**（K × N个独立分类头）。
  - **最终方案（多头路由器 Multi-Head Router）**：为降低开销，采用共享的 BERT-style 骨干网络（DeBERTa-v3-small, 44M）对查询 q 编码得到共享表示 h<sub>q</sub>，然后为每个“模型 k、采样数 n”组合训练一个独立的线性分类头 Head<sub>k,n</sub>，输出匹配概率 p<sub>k,n</sub>(q) = σ(w<sub>k,n</sub><sup>⊤</sup> h<sub>q</sub> + b<sub>k,n</sub>)。
  - 训练损失采用二元交叉熵。

- **算法流程（Algorithm 1）**
  1. **计算匹配概率**：用多头路由器预测所有 (M<sub>i</sub>, n) 组合的匹配概率。
  2. **筛选与成本估算**：保留概率≥用户阈值 t 的组合；成本估算 = n × 平均输出长度 × 输出单价 + 输入长度 × 输入单价。
  3. **选择最优组合**：若存在有效组合，则选取估算成本最低的组合；否则回退到参考模型 M<sub>ref</sub>（单次调用）。
  4. **执行采样**：对选定模型生成 n 个样本，用代理奖励模型选出最佳响应返回。

### 三、实验设计

- **数据集**：
  - **主数据集**：共10K指令样本（8K训练、1K验证、1K测试），来自 MixInstruct（问答）、RewardBench 和 CodeUltraFeedback（编程）、BeaverTails（安全），覆盖问答、编程、安全三大场景。
  - **OOD 数据集**：MT-Bench（Zheng et al., 2023）用于评估分布外泛化能力。
- **模型池**：共 8 个 LLM，包括参考模型 GPT-4o，以及 GPT-3.5-turbo、Llama-3.1-8B、Mistral-7B、Mistral-8x7B、Phi-3-mini、Phi-3-medium、Codestral-22B。每个查询生成 20 个响应。
- **评估指标**：
  - **响应质量**：主指标为 armoRM 分数（Wang et al., 2024a）；辅助指标 BLEU、ROUGE。
  - **效率**：推理成本（USD），包含输入/输出 token 单价（表6）。
  - **延迟**：路由器与 LLM 本身的耗时对比。
- **基准方法**：
  - **N-class Routing**：BERT 路由器预测最佳单模型。
  - **N-label Routing**：BERT 路由器预测所有可行模型，选择最便宜的。
  - **Clustering-based Routing**：K-Means 聚类后为每个簇分配最优模型。
  - **Model Cascades**（附录 B.2）：按成本升序依次调用，使用一致性分数决定停止。
- **实验数量与充分性**：
  - 主性能对比（图3、表1）在不同成本缩减率（10%~60%）下比较 BLEU/ROUGE 和 armoRM。
  - 路由器有效性验证（图6、表2）通过分析模型使用分布变化说明自适应能力。
  - 延迟测量（图7）对比路由开销与 LLM 推理时间。
  - OOD 评估（表3）在 MT-Bench 上重复对比。
  - 替代指标评估（表4）采用 BLEU/ROUGE。
  - 与 Model Cascades 对比（图8、表8）。
  - 成本估算误差（表7）验证估算准确性。
  - 消融分析（图4、图5）分别展示 best-of-n 带来的增益及与单模型 best-of-n 策略的对比。
- **公平性与客观性**：基准方法均来自公开文献；训练/验证/测试划分固定；采用多次生成的 armoRM 分数作为 ground truth 以避免单次偶然性；报告多个指标并做 OOD 测试。

### 四、资源与算力

- **训练硬件**：路由器训练和代理奖励模型训练使用 **NVIDIA A100 GPU（80GB RAM）**，但论文未明确给出训练时长或 GPU 数量。
- **推理计算**：所有 LLM 推理均通过付费 API（OpenAI、AzureML、Mistral AI）执行，路由器推理在 A100 上完成。延迟数据表明，路由器开销极低（例如 n=20 时路由+采样的总延迟 <1s，远低于 LLM 本身的 18.7 倍以上）。

### 五、实验数量与充分性

- **充分性评价**：实验覆盖了**三个主要任务类型**（问答、编程、安全），使用了**两个独立数据集**（主测试集和 OOD 的 MT-Bench），对比了**多种基线**（路由类和级联类），采用了**多个评估指标**（armoRM、BLEU、ROUGE、成本、延迟），并进行了**路由器使用分布分析**和**成本估算误差验证**。整体实验设计较为系统、全面，且训练/测试划分明确，结果统计可信。
- **缺项**：缺乏对路由器在不同阈值下的灵敏度分析（虽已有不同成本缩减率的结果）；未进行严格的多轮随机种子重复实验报告（但采用固定划分和多次采样评分可缓解偶然性）；对极大模型池（>10个模型）的可扩展性未测试，作者自己承认这一点。

### 六、论文的主要结论与发现

1. **BEST-Route 显著优于现有路由方法**：在 60% 成本缩减下，质量仅下降 0.8%（armoRM），而最强基线 N-label 路由在同一成本缩减下质量下降超过 5%。
2. **best-of-n 采样是提升小模型路由竞争力的关键**：对比仅使用 n=1 的静态路由，BEST-Route 通过动态调整采样数，在相同质量水平下进一步降低成本。
3. **路由器能有效识别查询难度并分配资源**：分析模型使用分布表明，简单查询多由低成本模型处理，困难查询则分配给大模型，验证了自适应机制的有效性。
4. **开销极低**：路由器的延迟远小于 LLM 推理本身，实际部署时可忽略不计。
5. **泛化能力强**：在 MT-Bench 以及 BLEU/ROUGE 指标下，BEST-Route 依然保持优势，说明不依赖特定评分模型或数据集分布。

### 七、优点

1. **创新性**：首次将 best-of-n 采样正式融入多模型路由框架，实现测试时计算资源的自适应分配，突破了传统路由“单次响应”的瓶颈。
2. **工程实用性**：多头路由器共享骨干网络，训练和推理开销小；代理奖励模型采用轻量级模型，避免使用昂贵 LLM 作为 judge。
3. **性能卓越**：在保持几乎无损（<1% 质量下降）的情况下，成本降低高达 60%，且明显优于同类方法。
4. **充分的验证**：多数据集、多指标、跨分布泛化实验设计，结果稳健。
5. **可调节性强**：用户可自由设置匹配概率阈值，在成本-质量曲线上任意位置达到目标平衡。

### 八、不足与局限

1. **依赖代理奖励模型准确性**：best-of-n 的质量受代理模型 ranking 能力限制，若出现 reward hacking 或与 ground truth 偏离，可能导致次优选择。虽然实验未观察到明显问题，但风险依然存在。
2. **模型池规模有限**：论文仅使用 8 个模型（含参考模型），对于包含数百个模型的平台，路由器训练成本和多头设计可能面临扩展性挑战。
3. **成本估算依赖平均输出长度**：使用训练集平均长度代替真实长度，虽误差很小，但对特定长度偏离大的查询可能引起决策偏差。
4. **未涉及实时流量调度**：路由决策仅基于单次查询，未考虑查询并发时整体延迟和吞吐优化。
5. **缺乏更广泛的风险分析**：论文未讨论该方法在安全敏感场景（如医疗、法律）中的适用性，也未分析 adversarial 输入对路由决策的影响。

（完）
