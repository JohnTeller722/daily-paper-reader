---
title: "Router-R1: Teaching LLMs Multi-Round Routing and Aggregation via Reinforcement Learning"
title_zh: Router-R1：通过强化学习教会LLM多轮路由与聚合
authors: "Haozhen Zhang, Tao Feng, Jiaxuan You"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DWf4vroKWJ"
tags: ["query:mas-routing"]
score: 8.0
evidence: 基于强化学习的多轮路由与聚合框架，用于多个LLM
tldr: Router-R1提出了一种基于强化学习的多轮路由与聚合框架，将多LLM路由视为序贯决策过程。路由器本身是一个具备推理能力的LLM，通过内部思考与外部动作交替，动态选择并聚合多个LLM的输出。在复杂任务上，Router-R1显著优于单轮路由方法，展示了多轮决策在LLM路由中的优势。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dwf4vrokwj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dwf4vrokwj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dwf4vrokwj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dwf4vrokwj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 1033, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 1347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1427, \"height\": 1356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1404, \"height\": 942, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1364, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1352, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dwf4vrokwj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 375, \"label\": \"Table\"}]"
motivation: 现有LLM路由器仅进行单轮一对一的映射，无法处理需要多个LLM互补的复杂任务。
method: 使用强化学习训练一个LLM路由器，使其能进行多轮思考与动作，动态选择并聚合多个LLM。
result: 在多个基准任务上，Router-R1超越单轮路由和固定聚合方法。
conclusion: 多轮路由与聚合能有效提升LLM系统处理复杂任务的能力。
---

## Abstract
The rapid emergence of diverse large language models (LLMs) has spurred the development of LLM routers that assign user queries to the most suitable model. However, existing LLM routers typically perform a single-round, one-to-one mapping (\textit{i.e.}, assigning each query to a single model in isolation), which limits their capability to tackle complex tasks that demand the complementary strengths of multiple LLMs. In this paper, we present \textbf{Router-R1}, a reinforcement learning (RL)-based framework that formulates multi-LLM routing and aggregation as a sequential decision process. Router-R1 instantiates the router itself as a capable LLM, leveraging its reasoning ability to interleave "think" actions (internal deliberation) with "route" actions (dynamic model invocation), and integrates each response into its evolving context. To facilitate learning, we employ a lightweight rule-based reward comprising format rewards, final outcome rewards, and a novel cost reward for optimizing the balance between performance and cost, opening a pathway toward enhancing performance-cost trade-offs via RL. Router-R1 also conditions only on simple model descriptors such as pricing, latency, and example performance, enabling strong generalization to unseen model selection. Experiments on seven general and multi-hop QA benchmarks show that Router-R1 outperforms several strong baselines, achieving superior performance while maintaining robust generalization and cost management.

---

## 论文详细总结（自动生成）

# Router-R1：通过强化学习教会LLM多轮路由与聚合

## 一、核心问题与整体含义（研究动机和背景）

**研究动机：**
- 当前LLM路由器仅执行**单轮、一对一**的映射：给定一个查询，选择一个模型，收集其输出后停止。
- 这种单次路由策略无法处理需要多个LLM**互补优势**的复杂任务（如多跳问答），因为复杂推理往往需要协调多个模型进行多轮交互。
- 现有方法（如基于梯度的单次路由）难以扩展到多轮选择和聚合，因为离散的模型选择过程不可微。

**整体含义：**
- Router-R1提出将多LLM路由与聚合建模为**序贯决策过程**，使路由器自身成为一个具备推理能力的LLM，能交替进行内部思考（think）和外部模型选择（route），逐步构建答案。

## 二、方法论

### 核心思想
1. **路由器作为LLM**：将路由器本身实例化为一个具备推理能力的LLM，利用其内在推理能力进行长期思考和目标模型选择。
2. **多轮交互**：框架允许路由器在推理过程中动态决定是进行内部思考还是调用特定LLM，通过多轮交互逐步聚合信息。
3. **强化学习优化**：采用PPO算法优化路由策略，目标函数包含KL散度约束：
   \[
   \max_\pi \mathbb{E}_{x \sim \mathcal{D}, y \sim \pi(\cdot|x; \mathcal{P})} \left[ r_\phi(x, y) - \beta \log \frac{\pi(y|x; \mathcal{P})}{\pi_{\text{ref}}(y|x; \mathcal{P})} \right]
   \]

### 关键技术细节
1. **奖励函数设计**（规则式）：
   - **格式奖励**：回答必须符合预定义格式（如包含`<think>...</think>`、`<search>...</search>`、`<answer>...</answer>`等标签），格式错误则奖励设为-1。
   - **最终结果奖励**：基于精确匹配（Exact Match）计算答案正确性。
   - **成本奖励**：与所选LLM的参数规模和输出token数量成反比，激励选择低成本模型。
   - **整体奖励**：`r = R_format + (1 - α)R_outcome + αR_cost`，其中α控制性能-成本权衡。且采用层次化奖励：若格式奖励为-1，则其他奖励归零。

2. **训练提示模板**：结构化提示包含：
   - 必须先在`<think>...</think>`内进行推理。
   - 若需要外部信息，通过`<search> Candidate LLM: Query </search>`调用特定模型。
   - 外部响应通过`<info>...</info>`返回。
   - 最终答案放在`<answer>...</answer>`中。
   - 提示中提供模型描述列表（参数规模、特长等），使路由器能基于描述选择模型。

3. **训练流程**：
   - 最大路由步骤：4步。
   - 训练时，外部模型的响应（`<info>`标签内）不参与损失计算。
   - 训练数据集：来自NQ和HotpotQA各7K样本，共14K样本。

### 算法流程（文字描述）
1. 输入查询。
2. 路由器进行内部思考（`<think>`），判断是否需要外部知识。
3. 若需要，则通过`<search>`指定目标LLM和子查询，调用该模型获取信息。
4. 将获取的信息插入上下文（`<info>`）。
5. 重复2-4步最多4次。
6. 若认为足够，直接输出最终答案（`<answer>`）。
7. 强化学习：根据格式、正确性和成本计算奖励，更新策略。

## 三、实验设计

### 数据集
- **通用问答**：Natural Questions (NQ)、TriviaQA、PopQA
- **多跳问答**：HotpotQA、2WikiMultiHopQA、Musique、Bamboogle
- 共7个数据集，覆盖单跳和多跳场景。

### 评估指标
- 主要指标：Exact Match (EM) 和 F1-Score
- 成本指标：未归一化的原始成本奖励

### 对比方法（baselines）
- **基础baselines**：直接推理、CoT、SFT、RAG（Wikipedia-18 + E5检索器）、Search-R1
- **单轮路由器baselines**：Prompt LLM、Largest LLM、KNN Router、MLP Router、BERT Router、RouterDC、GraphRouter
- **增强版单轮路由器**：Prompt LLM*、KNN Router*（先分解查询再路由）
- **额外baseline**：FrugalGPT

### 实验规模
- 训练数据集：14K样本（NQ和HotpotQA各7K）。
- 评估：每个数据集随机采样500个测试实例（Bamboogle约120个）。
- 基础模型：Qwen2.5-3B-Instruct 和 LLaMA-3.2-3B-Instruct。
- 路由池：6个模型（Qwen2.5-7B、LLaMA-3.1-8B/70B、Mistral-7B、Mixtral-8x22B、Gemma-2-27B）。
- 未见过模型测试：Palmyra-Creative-122B、LLaMA3-ChatQA-1.5-8B。

## 四、资源与算力

根据论文：
- 基础模型训练在**NVIDIA A6000 GPU**上进行。
- 路由LLM通过**NVIDIA NIM APIs**访问。
- 训练步骤：最大225步，batch size 64。
- 未明确说明使用多少张GPU、训练总时长等具体算力消耗。

## 五、实验数量与充分性

### 实验数量
- **主实验**：7个QA数据集上的EM和F1对比，两个基础模型，共约14个主要结果表。
- **成本分析实验**：4个不同α值（0.6,0.7,0.8,0.9）在4个数据集上的性能与成本对比。
- **泛化能力实验**：加入2个未见模型，在4个数据集上评估。
- **消融与分析**：LLM API调用次数分析、训练收敛曲线（奖励和策略熵）。
- **额外分析**：模型描述敏感性分析（简化描述不影响性能）、训练中引入新模型的效果。

### 充分性与公平性
- 对比方法涵盖单轮路由器、增强路由器、基础方法，共十余种。
- 训练和评估设置一致，使用相同的路由池和评估指标。
- 所有baseline在相同数据集上训练/微调（如需要）。
- 实验覆盖in-domain（NQ、HotpotQA）和out-of-domain（其余5个）场景。
- 总体而言实验较充分，但主要聚焦于问答任务，缺乏对其他任务类型的验证。

## 六、主要结论与发现

1. **Router-R1在所有7个数据集上一致优于所有baselines**，实现了SOTA性能。
2. **多轮路由显著优于单轮路由**：即使增强版单轮路由器（分解查询再路由）也无法匹敌。
3. **泛化能力强**：在未见数据集上表现稳健，且能通过模型描述泛化到未见LLM，无需重训练。
4. **成本可控**：通过调整成本系数α，Router-R1能实现性能-成本的有效平衡，形成自适应路由策略（先小模型后大模型）。
5. **训练高效**：仅需14K样本即可学会有效路由策略，约100步收敛。
6. **格式奖励的重要性**：无格式奖励时训练不稳定，产生无意义输出。

## 七、优点

1. **方法创新性**：首次将多LLM路由建模为序贯决策过程，使路由器本身成为可推理的LLM，实现了思考与路由的自然交织。
2. **奖励函数简洁有效**：规则式奖励（格式+结果+成本）避免了复杂的人工标注或训练奖励模型，层次化设计防止奖励破解。
3. **泛化能力突出**：仅基于简单模型描述即可推广到未见LLM，适应快速演化的模型生态。
4. **成本意识**：通过成本奖励实现性能-成本的灵活权衡，支持资源感知路由。
5. **实验全面**：覆盖多种类型问答任务，对比丰富基线，并进行了详细的消融和分析。

## 八、不足与局限

1. **任务范围有限**：仅评估了问答任务，未在对话、摘要、代码生成等其他领域验证，可能导致路由动态不同。
2. **奖励函数过于简单**：规则式奖励可能无法捕捉事实一致性、长期对话连贯性等更复杂的指标，需考虑加入学习式或人工奖励。
3. **推理延迟**：多轮交互和多模型调用增加了推理延迟，可能不适合实时应用。
4. **模型描述依赖**：泛化到新LLM依赖描述词，描述可能无法完全捕捉深层行为，尤其在缺乏历史性能时。
5. **成本归一化稳定性**：跨域训练时响应长度差异可能导致成本尺度不一致，需要任务级归一化。
6. **实验统计**：未报告误差线或置信区间，固定种子运行，缺乏对随机变异的量化。
7. **资源计算**：未详细披露训练所需的GPU数量、时间等，可复现性细节有待补充。

（完）
