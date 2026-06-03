---
title: "G-Designer: Architecting Multi-agent Communication Topologies via Graph Neural Networks"
title_zh: G-Designer：通过图神经网络构建多智能体通信拓扑
authors: "Guibin Zhang, Yanwei Yue, Xiangguo Sun, Guancheng Wan, Miao Yu, Junfeng Fang, Kun Wang, Tianlong Chen, Dawei Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LpE54NUnmO"
tags: ["query:mas-routing"]
score: 9.0
evidence: 动态通信拓扑设计以实现任务感知路由
tldr: 在多智能体系统中，通信拓扑的选择直接影响任务效率和成本。本文提出G-Designer，利用图神经网络为每个任务动态设计定制化的通信拓扑，避免了不必要的令牌开销。实验表明G-Designer在多种任务上自适应地找到了最优拓扑，显著提升了路由效率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 822, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 841, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 494, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 117, \"height\": 143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 107, \"height\": 143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 623, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 515, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lpe54nunmo/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 515, \"height\": 239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1307, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 661, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lpe54nunmo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 907, \"height\": 1023, \"label\": \"Table\"}]"
motivation: 固定通信拓扑无法适应不同任务需求，导致效率低下。
method: 使用图神经网络动态生成任务感知的通信拓扑。
result: G-Designer在多个基准上实现了高效且自适应的路由。
conclusion: 动态拓扑设计是实现高效多智能体路由的关键技术。
---

## Abstract
Recent advancements in large language model (LLM)-based agents have demonstrated that collective intelligence can significantly surpass the capabilities of individual agents, primarily due to well-crafted inter-agent communication topologies. Despite the diverse and high-performing designs available, practitioners often face confusion when selecting the most effective pipeline for their specific task: \textit{Which topology is the best choice for my task, avoiding unnecessary communication token overhead while ensuring high-quality solution?} In response to this dilemma, we introduce G-Designer, an adaptive, efficient, and robust solution for multi-agent deployment, which dynamically designs task-aware, customized communication topologies. Specifically, G-Designer models the multi-agent system as a multi-agent network, leveraging a variational graph auto-encoder to encode both the nodes (agents) and a task-specific virtual node, and decodes a task-adaptive and high-performing communication topology. Extensive experiments on six benchmarks showcase that G-Designer is: \textbf{(1) high-performing}, achieving superior results on MMLU with accuracy at $84.50\\%$ and on HumanEval with pass@1 at $89.90\\%$; \textbf{(2) task-adaptive}, architecting communication protocols tailored to task difficulty, reducing token consumption by up to $95.33\\%$ on HumanEval; and \textbf{(3) adversarially robust}, defending against agent adversarial attacks with merely $0.3\\%$ accuracy drop.

---

## 论文详细总结（自动生成）

# G-Designer：通过图神经网络构建多智能体通信拓扑 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基于大语言模型（LLM）的多智能体系统中，通信拓扑结构的选择对任务性能至关重要，但现有方法（如链式、树状、完全图、随机图等）均为**静态、输入无关**的设计，无法根据具体任务动态调整。实践者面临困境：对于给定任务，如何选择既能保证高质量输出、又避免不必要通信开销的拓扑？
- **研究动机**：实验发现，同一数据集内不同难度的子任务（如MMLU的“高中生物”vs“大学数学”），最优拓扑截然不同。简单任务用复杂拓扑浪费token，复杂任务用简单拓扑性能不足。因此需要一种**任务自适应**的拓扑设计方法。
- **整体含义**：本文首次提出了面向LLM多智能体系统的通信协议（MACP），要求拓扑同时满足**有效性**（高质量输出）、**复杂度自适应**（最低通信开销）、**对抗鲁棒性**（抵御攻击）。并据此设计了G-Designer，实现端到端的自动拓扑生成。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
将多智能体系统建模为图，每个智能体作为节点，智能体之间的通信作为边。引入**任务虚拟节点**（task-specific virtual node）编码查询信息，利用**变分图自编码器（VGAE）** 编码节点并解码出任务自适应的稀疏通信拓扑，最后通过策略梯度优化。

### 关键技术细节（流程）：
1. **多智能体网络构建**：
   - 每个智能体 `v_i = {Base_i, Role_i, State_i, Plugin_i}`，使用轻量文本编码器（all-MiniLM-L6-v2）将其转换为嵌入 `x_i`。
   - 任务虚拟节点 `x_task = NodeEncoder(Q)`，与所有智能体节点双向连接。
   - 提供锚定拓扑 `A_anchor`（默认简单链结构）作为先验。
   - 最终构成多智能体网络 `\tilde{G} = ( \tilde{V}, \tilde{A}_anchor )`。

2. **通信拓扑设计**：
   - **编码器**：两层GCN将节点特征映射为隐变量分布 `q(H | \tilde{X}, \tilde{A}_anchor)`，输出均值和方差。
   - **解码器（第一阶段）**：从隐变量H和任务节点`h_task`，通过双线性函数+Gumbel-Sigmoid生成草图图 `S`（稠密，表示所有潜在通信）。
   - **解码器（第二阶段）**：通过带稀疏正则化和锚定正则化的优化，将`S`精炼为稀疏通信图 `G_com`：
     - 目标函数：`argmin 1/2||S - ZWZ^T||_F^2 + \zeta ||W||_* + 1/2||A_anchor - ZWZ^T||_F^2`
     - 其中`Z`是`S`的左奇异向量，`W`可优化；稀疏正则化通过核范数实现。
   - 最终`G_com`的边为`\tilde{S}_{ij} \neq 0`且属于允许边集。

3. **多轮交互与优化**：
   - 根据`G_com`确定执行顺序`\sigma`，各智能体按顺序接收输入并生成输出。
   - K轮对话后聚合结果`a^(K)`。
   - 优化目标：最大化效用`u(G_com(Q))`，由于不可导，使用政策梯度近似：`\nabla E[u] \approx 1/M \sum u(a_m) \nabla \log P(G_m)`。
   - 总损失：`L = L_utility + L_anchor + L_sparse`。

4. **训练流程**：
   - 使用少量（40~80条）查询作为训练集，更新编码器和解码器参数。
   - 训练后固定参数，用于剩余查询的推理。

## 3. 实验设计

### 数据集/场景
- **通用推理**：MMLU（153道多选题）
- **数学推理**：GSM8K（1319道）、MultiArith（600道）、SVAMP（1000道）、AQuA（254道）
- **代码生成**：HumanEval（164道，Pass@1）
- 所有数据集采用公开标准测试集，使用准确率或Pass@1作为评价指标。

### Benchmark
- **多智能体拓扑基线**：Chain、Star、Tree、Complete Graph、Random Graph、AutoGen、MetaGPT、LLM-Debate、LLM-Blender、DyLAN、GPTSwarm。
- **单智能体基线**：Vanilla、CoT、ComplexCoT、Self-Consistency、PHP。
- **全部采用5个gpt-4基座的智能体**（部分实验扩展至10/20个）。

### 对比方法特点
- 固定拓扑：Chain/Star/Tree/Complete/Random
- 可优化拓扑：DyLAN（动态删除低分agent）、GPTSwarm（图优化+节点优化）
- 专用框架：AutoGen、MetaGPT（代码生成）、LLM-Debate（辩论）

## 4. 资源与算力

- **GPU**：文中提到“训练G-Designer在1000个智能体时仅需**小于4GB显存**”（表5），但未明确GPU型号、数量。
- **训练开销**：
  - 训练时间：在GSM8K上，G-Designer训练时间仅**0.3小时**（表2中的“Training Time”列，原文为0.3h，注：实际表格中G-Designer Training Time显示0.3h）。
  - Token消耗：训练阶段约2.7×10^4 tokens（GSM8K）；推理阶段约8.2×10^5 tokens（整体约8.5×10^5 tokens）。
- **硬件推断**：鉴于显存需求低（<4GB），推测可能使用了单张消费级GPU（如RTX 3090/4090）或T4，但论文未明确说明。
- **说明**：论文未记录具体GPU型号、数量及更详细的算力成本（如CPU核数、内存）。但强调资源友好。

## 5. 实验数量与充分性

### 实验组数
- **主实验**（表1）：在6个基准上对比了13种基线（包括单智能体和多智能体），涵盖不同难度和领域。
- **鲁棒性实验**（图5）：对5种代表方法进行系统提示攻击，每组对比攻击前后准确率。
- **消融实验**（表3）：4种变体（w/o SR、w/o Anchor、w/o NodeEncoder、w/o v_task）在MMLU和GSM8K的干净/攻击场景下测试。
- **效率分析**（表2）：对比Complete、DyLAN、GPTSwarm、G-Designer在训练/推理的token和时间成本。
- **可扩展性实验**（表6）：在5/10/20个agent下对比Chain、Complete、GPTSwarm、G-Designer的性能、token和时间。
- **案例可视化**（图6）：展示HumanEval和GSM8K上不同难度任务的拓扑设计。
- **其他**：图2展示MMLU子集token-精度权衡；图4展示多方法token-精度散点图。

### 充分性与公平性
- **充分性**：实验覆盖了主要任务类型（推理、数学、代码），对比了有代表性的基线，设置了消融和鲁棒性测试，考虑了可扩展性。整体设计较完整。
- **公平性**：所有多智能体方法使用相同数量的agent（5个，gpt-4），相同的对话轮数K=3，相同的聚合方式（summarizer agent）。但注意：
  - 部分基线（如MetaGPT）是专为代码设计，可能在其他任务上未充分调优。
  - 锚定拓扑固定为Chain，可能对某些基线（如GPTSwarm）初始结构不同，但论文已通过消融说明G-Designer远优于Chain。
  - 仅测试了gpt-4和gpt-3.5，未测试开源LLM，存在泛化偏差。

## 6. 论文的主要结论与发现

1. **高性能**：G-Designer在6个基准中的5个上取得最优结果，MMLU 84.50%、HumanEval 89.90% Pass@1，平均比GPTSwarm高约2.5个百分点。
2. **任务自适应**：拓扑复杂度随任务难度动态调整。在简单任务（strlen函数）仅保留2个agent的链结构，复杂任务（do_algebra）设计密集协作图。token消耗降低最多95.33%（HumanEval），整体比SOTA方法减少92.24%。
3. **对抗鲁棒性**：在单agent提示攻击下，G-Designer准确率仅下降0.3%（84.5%→84.2%），而Chain下降11.0%、DyLAN下降6.2%、AutoGen下降9.9%。
4. **可扩展性**：agent数量从5增至20时，G-Designer性能提升幅度最大，且token消耗仅约为GPTSwarm的6.11%。
5. **资源高效**：训练仅需40~80个查询，GPU显存需求<4GB，训练时长不到1小时。
6. **消融表明关键模块**：任务虚拟节点贡献最大（缺乏时准确率下降3%+）；稀疏正则化和锚定正则化均对最终性能与鲁棒性有正面作用。

## 7. 优点

- **创新性**：首次提出面向LLM多智能体系统的通信协议MACP，并设计了完全任务自适应的拓扑设计方法，解决了“如何为任务选择拓扑”这一实际痛点。
- **方法论亮点**：
  - 引入任务虚拟节点使拓扑感知查询内容。
  - 变分图自编码器结合双重解码（草图+精炼），平衡构建灵活性与计算效率。
  - 稀疏正则化保证拓扑轻量，锚定正则化注入先验知识。
  - 利用策略梯度绕过不可导的效用函数，使端到端优化可行。
- **实验设计优点**：
  - 多维度评估：性能、token开销、训练资源、鲁棒性、可扩展性，一应俱全。
  - 对比充分，基线覆盖主流多智能体方法。
  - 消融实验清晰验证各组件必要性。
  - 案例可视化直观展示任务自适应效果。
- **实用价值**：代码开源（https://github.com/yanweiyue/GDesigner），训练资源要求低，易于部署。

## 8. 不足与局限

- **实验覆盖不全面**：
  - 仅测试了文本推理和代码任务，未涉及对话、游戏、具身任务、多模态任务。
  - 仅使用gpt-4和gpt-3.5，未验证Llama、Mistral等开源LLM。
  - 鲁棒性仅测试了单agent系统提示攻击，未考虑多agent协同攻击、后门攻击、数据污染等更广泛场景。
- **潜在偏差风险**：
  - 训练集仅40~80个查询，可能不足以覆盖任务多样性，存在过拟合风险（尤其在MMLU的100+子任务上）。
  - 锚定拓扑默认Chain，虽然通过消融证明性能提升主要来自自适应设计，但Chain作为先验可能偏向某种结构。若锚定选择更优的初始图，结果可能进一步改善；反之若锚定很差，可能影响收敛。
- **应用限制**：
  - 方法依赖外部LLM API调用，token消耗虽少但仍有成本。
  - 虚拟节点编码仅使用MiniLM，可能无法捕捉复杂任务语义。
  - 策略梯度优化需要多次采样（M=10），每次采样需额外LLM调用，训练阶段成本累计。
  - 当前设计假设agent数量和角色池固定；动态调整agent集合或支持agent出生/死亡尚未考虑。
- **泛化性**：G-Designer在GSM8K上略低于PHP（单智能体方法），说明在某些数学推理任务上，精心设计的单智能体提示仍可能胜过复杂多智能体协作。

（完）
