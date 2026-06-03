---
title: Can Graph Learning Improve Planning in LLM-based Agents?
title_zh: 图学习能否提升LLM智能体中的规划能力？
authors: "Xixi Wu, Yifei Shen, Caihua Shan, Kaitao Song, Siwei Wang, Bohang Zhang, Jiarui Feng, Hong Cheng, Wei Chen, Yun Xiong, Dongsheng Li"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=bmoS6Ggw4j"
tags: ["query:mas-routing"]
score: 6.0
evidence: 图学习用于任务规划与子任务路由
tldr: 该论文探索了利用图学习改进LLM智能体的任务规划，将子任务视为图结构，通过选择连接路径或子图来实现任务路由，从而提升协调效率。实验结果表明图学习方法在任务规划上优于传统提示方法，为多智能体协调路由提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1163, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1322, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1381, \"height\": 1111, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1299, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1299, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1398, \"height\": 865, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1400, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bmos6ggw4j/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 1229, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 847, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1308, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1434, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1334, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 1079, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 450, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1309, \"height\": 729, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1449, \"height\": 2034, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 2034, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1235, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bmos6ggw4j/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 285, \"label\": \"Table\"}]"
motivation: 任务规划中的子任务可以自然建模为图，但现有方法主要关注提示设计而非图学习。
method: 提出基于图学习的任务规划方法，将子任务视为节点，依赖关系为边，选择路径或子图进行路由。
result: 实验显示图学习方法在任务规划准确率和效率上优于传统提示方法。
conclusion: 图学习为LLM智能体的任务规划和路由提供了一种有效且正交的研究方向。
---

## Abstract
Task planning in language agents is emerging as an important research topic alongside the development of large language models (LLMs). It aims to break down complex user requests in natural language into solvable sub-tasks, thereby fulfilling the original requests. In this context, the sub-tasks can be naturally viewed as a graph, where the nodes represent the sub-tasks, and the edges denote the dependencies among them. Consequently, task planning is a decision-making problem that involves selecting a connected path or subgraph within the corresponding graph and invoking it. In this paper, we explore graph learning-based methods for task planning, a direction that is orthogonal to the prevalent focus on prompt design. Our interest in graph learning stems from a theoretical discovery: the biases of attention and auto-regressive loss impede LLMs' ability to effectively navigate decision-making on graphs, which is adeptly addressed by graph neural networks (GNNs). This theoretical insight led us to integrate GNNs with LLMs to enhance overall performance. Extensive experiments demonstrate that GNN-based methods surpass existing solutions even without training, and minimal training can further enhance their performance. The performance gain increases with a larger task graph size.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在大语言模型（LLM）智能体中，任务规划（task planning）需要将复杂的用户自然语言请求分解为可执行的子任务，并确定它们的调用顺序。子任务及其依赖关系可以自然地建模为一张**任务图**（task graph），其中节点代表子任务，边代表依赖关系。任务规划本质上是在任务图上选择一个连通路径或子图。
- **现有方法局限**：当前主流方法主要聚焦于**提示设计**（prompt design），如链式思维、树式思维等。然而，论文通过理论分析发现：
    - Transformer 的**注意力机制偏置**和**自回归损失**（auto-regressive loss）会阻碍 LLM 在图上进行有效决策。
    - LLM 在处理图结构时存在幻觉（hallucination）、缺乏图同构不变性、稀疏注意力限制表达能力等问题。
- **本文核心主张**：引入**图学习（Graph Learning）** 方法，特别是图神经网络（GNN），从根本上弥补 LLM 在图决策上的不足，并提出一种将 GNN 与 LLM 结合的任务规划新范式。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：保持 LLM 在自然语言理解与分解方面的优势，同时利用 GNN 在**图结构决策**上的擅长，实现两步协作：
    1. **LLM 分解阶段**：LLM 将用户请求转换为一系列具体的、可执行的步骤（step descriptions）。
    2. **GNN 检索阶段**：基于任务图和步骤描述，GNN 为每个步骤选择最合适的任务节点，并按图依赖关系生成调用路径。
- **技术细节**：
    - **任务图构建**：每个任务节点附带文本描述（如“Translation: 将文本从一种语言转换为另一种语言”）；边表示资源或时序依赖。
    - **特征嵌入**：使用预训练小语言模型（如 e5-335M）将步骤描述和节点描述嵌入为向量。
    - **GNN 变体**：
        - **无训练方法**：采用参数自由的**简化图卷积（SGC）**，通过图卷积平滑节点特征，然后基于余弦相似度匹配步骤和节点。
        - **有训练方法**：使用可训练 GNN（如 GraphSAGE、GAT 等），并采用**贝叶斯个性化排序（BPR）损失**进行优化。损失函数为：
          \[
          \ell = \sum_{(x_{\text{step}}, v, v')} -\log \sigma(\langle h_v, x_{\text{step}} \rangle - \langle h_{v'}, x_{\text{step}} \rangle)
          \]
          其中 \(v\) 是正样本（正确任务），\(v'\) 是负样本（文本相似但错误的任务）。
    - **推理流程**：对每个分解步骤，GNN 从当前节点的邻居中选择与步骤嵌入最相似的节点，依次生成完整路径。

## 3. 实验设计

- **数据集**：
    - **TaskBench**：包含 HuggingFace（23 个子任务）、Multimedia（40）、Daily Life（40）三个场景。
    - **RestBench**：TMDB（电影 API，46 个任务）。
    - **UltraTool**：更大规模（260 个任务），用于验证可扩展性。
- **基准方法**：
    - **LLM 直接推理**：仅使用 LLM 同时完成分解和任务检索。
    - **GraphSearch**（基于图搜索的提示方法）：包括 GreedySearch、AdaptiveSearch、BeamSearch，由 LLM 评估候选任务。
- **对比方法**：
    - **无训练方法**：对比 LLM 直接推理、GraphSearch 变体、SGC。
    - **有训练方法**：对比 TAPE（LLM→LM→GNN）、GraphToken（GNN 编码图输入到 LLM）、以及多种 GNN（GCN、GAT、GraphSAGE、GIN、Graph Transformer）。
- **评价指标**：Node F1、Link F1、Accuracy（任务级成功率）、Token 消耗数。
- **LLM 选择**：闭源（GPT-3.5-turbo、GPT-4-turbo）和开源（CodeLlama-7B/13B、Mistral-7B、Vicuna-13B、Baichuan2-13B）。

## 4. 资源与算力

- 文中明确提供了计算资源信息（详见附录表 13）：
    - **GNN 训练**：在单个 NVIDIA A100-80G GPU 上，仅训练 GNN 通常耗时 **2~4 分钟**；LM+GNN 联合训练耗时 **6~12 分钟**。
    - **LLM 微调**（LoRA）：使用 1~2 张 A100-80G，训练 2 个 epoch 需 **10~20 小时**。
    - 对比之下，**本文方法在训练效率上具有显著优势**。

## 5. 实验数量与充分性

- **实验数量**：非常充分。涉及：
    - 4 个基准数据集（含一个大规模图数据集 UltraTool）。
    - 7 种不同 LLM（含不同参数规模）。
    - 5 种以上 GNN 架构。
    - 无训练和训练两种模式。
    - 额外消融实验：与改进提示（2-shot、PlaG）的正交性、与微调 LLM 的正交性、参数预测实验、案例分析。
- **充分性与公平性**：实验设计规范，所有方法在相同设置下比较，指标全面（F1、Acc、Token 消耗）。结果具有统计意义，且提供了错误案例分析和诊断。因此实验充分、客观、公平。

## 6. 论文的主要结论与发现

- **主要结论**：
    1. LLM 在任务规划中因注意力偏置和自回归损失导致图决策能力受限，表现为节点/边幻觉。
    2. 引入 GNN 进行任务检索可以**显著提升规划性能**，且**无训练版本（SGC）** 已优于大多数强基线。
    3. **有训练版本**（如 GraphSAGE）进一步提升性能，且**性能增益随任务图规模增大而增大**（在 UltraTool 上提升 9% 以上）。
    4. 本文方法与**提示工程和 LLM 微调正交**，可叠加使用获得更优效果。
- **其他发现**：GNN 还能帮助 LLM 更准确地填充任务参数（参数 F1 提升 3%~23%）。

## 7. 优点

- **理论创新**：首次从理论上剖析了 Transformer 在图上决策的局限性（稀疏注意力、缺乏同构不变性、自回归损失引入虚假关联），为改进提供依据。
- **方法简洁高效**：无需重训 LLM，只需轻量 GNN（无训练或极短训练），就能显著提升规划准确率和效率（Token 消耗减少 5~10 倍）。
- **实用性强**：支持训练-免费部署，适用于任务不断变化的场景；训练模式也仅需分钟级。
- **广泛兼容**：可与任意 LLM（闭源/开源）及多种提示策略结合，易于集成。

## 8. 不足与局限

- **方法直接简单**：当前 GNN 仅用于一步检索，未探索更复杂的图决策算法（如强化学习、树搜索），可能还有提升空间。
- **任务图构建需人工**：手动定义节点和边依赖，缺乏自动化生成机制，限制了在不同领域的快速迁移。
- **依赖分解步骤质量**：若 LLM 分解步骤含糊或错误，GNN 检索会级联出错（案例分析已指出）。
- **大图可扩展性仍需验证**：虽然在 UltraTool（260 节点）上有效，但未测试更大规模（如上千节点）下的表现。
- **实验局限性**：主要基于工具调用场景（HuggingFace、API），未在更开放的环境（如对话系统、机器人规划）中验证。

（完）
