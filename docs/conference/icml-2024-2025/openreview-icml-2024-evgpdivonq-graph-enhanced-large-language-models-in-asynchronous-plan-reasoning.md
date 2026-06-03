---
title: Graph-enhanced Large Language Models in Asynchronous Plan Reasoning
title_zh: 图增强大语言模型在异步规划推理中的应用
authors: "Fangru Lin, Emanuele La Malfa, Valentin Hofmann, Elle Michelle Yang, Anthony G. Cohn, Janet B. Pierrehumbert"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=eVGpdivOnQ"
tags: ["query:mas-routing"]
score: 6.0
evidence: 使用图增强提示解决异步计划推理以优化时间成本，与多跳推理配置相关
tldr: 大语言模型在处理需并行化优化的异步计划推理时表现不佳。本文构建了AsyncHow基准，并提出PLaG方法——将图结构与自然语言提示结合，引导LLM进行顺序与并行推理。实验表明PLaG显著提升了LLM在异步规划上的性能，但模型仍存在特定退化问题，为多跳推理中的配置选择提供了经验性依据。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 809, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 755, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1741, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 755, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 751, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 825, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1757, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1013, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1045, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1641, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1396, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-evgpdivonq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 849, \"height\": 660, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1395, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1768, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 1740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1237, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1114, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-evgpdivonq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1768, \"height\": 283, \"label\": \"Table\"}]"
motivation: LLM在需要顺序和并行规划的异步任务中推理能力不足，缺乏有效提示策略。
method: 提出Plan Like a Graph (PLaG)，将问题转为图结构并融入自然语言提示以增强LLM的异步规划能力。
result: 在AsyncHow基准上PLaG达到最优性能，但LLM在规划细节上仍有显著退化。
conclusion: 图提示可提升LLM异步规划能力，但模型对图结构的依赖和脆弱性仍需进一步研究。
---

## Abstract
Planning is a fundamental property of human intelligence. Reasoning about asynchronous plans is challenging since it requires sequential and parallel planning to optimize time costs. Can large language models (LLMs) succeed at this task? Here, we present the first large-scale study investigating this question. We find that a representative set of closed and open-source LLMs, including GPT-4 and LLaMA-2, behave poorly when not supplied with illustrations about the task-solving process in our benchmark AsyncHow. We propose a novel technique called *Plan Like a Graph* (PLaG) that combines graphs with natural language prompts and achieves state-of-the-art results. We show that although PLaG can boost model performance, LLMs still suffer from drastic degradation when task complexity increases, highlighting the limits of utilizing LLMs for simulating digital devices. We see our study as an exciting step towards using LLMs as efficient autonomous agents. Our code and data are available at https://github.com/fangru-lin/graph-llm-asynchow-plan.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文内容，以下是对该论文的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

-   **核心问题**：大语言模型（LLMs）在处理**异步规划**任务时表现如何？异步规划要求同时进行**顺序推理**（线性执行）和**并行推理**（同时执行）以优化时间成本。例如，在制作菜肴时，预热烤箱可以与其他步骤并行，而揉面和添加馅料则必须顺序进行。找到一个最优的异步计划对人类来说具有挑战性，对LLM来说更是一项复杂的组合推理任务。
-   **研究背景**：LLMs在规划任务上展现出一定潜力，但现有研究多关注于生成可行的步骤序列，而非寻找**最优**的、能够并行处理以最小化总时间的计划。以往研究表明，LLMs在没有外部符号处理器（如规划器）辅助时，难以独立生成最优计划。本论文旨在填补这一空白，首次大规模研究LLMs在自然语言描述的异步规划任务上的推理能力。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

-   **核心思想**：提出一种名为 **“Plan Like a Graph” (PLaG)** 的提示技术。其核心思想是将自然语言描述的异步规划问题显式地或隐式地转换为**有向无环图（DAG）** 问题，利用LLMs在图数据上的推理能力来提升规划性能。
-   **关键技术细节**：
    -   **任务形式化**：论文将异步规划任务形式化为在DAG上寻找**最长路径**的问题。DAG的节点代表任务步骤，边代表顺序约束，边权重代表该步骤所需时间。找到总时间最短的最优计划等同于找到从开始节点到结束节点的最长加权路径。
    -   **PLaG方法**：该方法包含两种变体：
        -   **显式图（Explicit Graph）**：在提示词中直接提供任务的图结构表示（如邻接表、边列表、邻接矩阵、压缩稀疏行CSR格式）。
        -   **构建图（Build a Graph, BaG）**：在提示词中要求LLM**自行生成**任务的图结构表示，然后再基于该图进行推理。
    -   **提示结构**：PLaG将图结构信息整合到标准的少样本（k-shot）或思维链（Chain-of-Thought, CoT）提示模板中，引导模型进行“构造图 -> 基于图进行计算”的推理步骤。
-   **公式或算法流程（文字说明）**：
    -   优化目标：找到最小化总时间的计划 \( P^* \)。
    -   等价于在DAG \( G = \langle V, E, w \rangle \) 上寻找最长路径 \( G^* \)。其中 \( V \) 是节点（步骤），\( E \) 是有向边（顺序约束），\( w(e_{i,j}) \) 是边权重（步骤 \( v_i \) 的耗时）。
    -   算法：\( G^* = \arg\max_{G' \subseteq G} \sum_{e_{i,j} \in E'} w(e_{i,j}) \)，该路径满足约束且从开始节点到结束节点。
    -   对于串联-并联图，该问题的时间复杂度为 \( O(|V|+|E|) \)，即线性复杂度。

### 3. 实验设计：数据集、基准、对比方法

-   **数据集/基准**: 论文自动构建了一个新的基准测试集 **AsyncHow（Asyncronous WikiHow）**。
    -   包含 **1.6K** 个高质量的自然语言异步规划问题实例。
    -   数据来源：基于**WikiHow**（生活常识任务）和**ProScript**（部分有序脚本数据集）。
    -   生成流程：使用GPT系列模型进行步骤时间估计、依赖关系标注，并通过确定性最长路径算法计算最优答案，经人工和自动化质量校验后形成基准。
    -   **任务复杂度度量**：定义为 \( |V| + |E| \)（节点数加边数）。
-   **基准方法**：
    -   **基础方法**：零样本（Zero-shot）、零样本+思维链（Zero-shot+CoT）、少样本（k-shot）、少样本+思维链（k-shot+CoT）。
    -   **高级方法**（部分实验）：思维链自洽性（CoT-SC）、思维树（ToT）。
-   **对比方法**：
    -   **PLaG（显式图）**：在提示中提供预先计算好的图表示。
    -   **PLaG（BaG）**：在提示中要求模型自己构建图。
-   **评估指标**：**准确率**，即模型正确计算出最优计划所需的最短时间。

### 4. 资源与算力

-   **实验资源**：论文主体部分没有明确给出具体的GPU型号、数量或训练时长。但在附录的补充信息中（A.16节），提到了部分实验细节：
    -   **数据生成**：使用Azure OpenAI API（GPT-3.5-turbo, GPT-4）。
    -   **实验推理**：
        -   GPT模型：使用Azure OpenAI API。
        -   Command模型：使用Cohere API。
        -   LLaMA-2-70B-chat：使用Huggingface推理API。
        -   Mistral-7B-Instruct：使用**2块V100 GPU和1块A100 GPU**进行推理。
    -   **其他**：论文未提及模型的训练（fine-tuning）资源，所有实验均基于API调用或预训练模型的直接推理。

### 5. 实验数量与充分性

-   **实验数量**：论文进行了非常详尽的实验，包括：
    -   在**5个不同规模/闭源/开源的LLM**（GPT-4, GPT-3.5, Command, LLaMA-2-70B-chat, Mistral-7B-Instruct）上进行全基准测试。
    -   对比了**6种不同的提示策略**（Zero-shot, Zero-shot+CoT, k-shot, k-shot+CoT, PLaG显式, PLaG BaG）。
    -   **消融实验**：通过比较任务复杂度对性能的影响、分离“时间比较”、“时间求和”和“约束推理”三种子技能，以及对比不同图表示和文本提示的效果。
    -   **分布外探测**：使用合成数据集测试模型在更高复杂度任务上的表现。
    -   **延迟/成本分析**：比较了不同方法的token消耗。
    -   **鲁棒性测试**：测试了不同文本表达方式（包括简洁表达）对性能的影响。
-   **充分性与公平性**：实验设计非常充分和客观。论文严格遵循了统计显著性检验（McNemar检验），确保了使用PLaG的改进是可靠的。消融实验清晰地揭示了影响性能的关键因素。跨不同模型（从顶尖的商业模型到较小的开源模型）和不同提示设置（包括无图提示）的广泛对比，保证了结论的稳健和客观。

### 6. 论文的主要结论与发现

-   **核心发现**：在没有详细任务解决过程说明的情况下，所有LLM在异步规划任务上表现都很差。
    -   即使提供了少样本+CoT的解决方案说明，仅GPT-4能达到尚可但远非完美的性能（65.7%）。
-   **PLaG的有效性**：提出的PLaG方法能在所有复杂度水平上**持续且显著地**提升所有测试模型（特别是GPT-3.5和GPT-4）的性能，达到了SOTA水平。
    -   对于最强大的模型（GPT-4），**PLaG（BaG）** 表现最佳（77.7%）。
-   **性能下降**：尽管PLaG带来了提升，但随着任务复杂度（\( |V| + |E| \)）的增加，所有模型的性能都会出现**剧烈下降**。这表明LLM作为通用智能体或在模拟数字设备上仍存在根本局限性。
-   **模型差距**：
    -   商业模型（GPT系列）远超开源模型。
    -   Mistral-7B-Instruct在多数设置下表现优于更大的LLaMA-2-70B-chat。
    -   GPT-4在需要“约束推理”和“时间求和”的复杂场景下优势明显；而GPT-3.5在简单的“时间比较”场景下不弱。
-   **图表示的影响**：显式提供图结构能提升性能，但不同图类型（邻接表、边列表等）对不同模型和任务复杂度的性能有影响。
-   **语言分界**：模型在自然语言描述的规划任务（AsyncHow）上的表现，显著差于纯粹的数字逻辑/图搜索任务（合成数据集），说明将自然语言转化为可计算程序是主要瓶颈之一。PLaG通过提供结构化表示来弥合这一差距。

### 7. 优点：方法或实验设计上的亮点

-   **问题定义与形式化**：首次将自然语言中的异步规划问题严谨地形式化为DAG上的最长路径问题，并提出了相应的任务复杂度度量（\( |V| + |E| \)），为分析LLM性能提供了清晰的理论基础。
-   **新基准（AsyncHow）**：构建了一个高质量、开源、来自真实世界任务的基准，填补了该领域的数据空白。自动生成流程（特别是使用LLM进行标注和通过确定性算法计算答案）具有可复制性和扩展性。
-   **方法简单有效**：PLaG是一种无需微调的提示技术，可以直接应用于任何LLM，成本低、易于实现，且提升效果显著。通过“构建图”（BaG）的方式，提示模型进行更深层次的推理，是个很有启发性的思路。
-   **全面的消融和诊断分析**：通过分解子技能、分析不同复杂度、进行分布外探测（使用合成数据）等，深入剖析了LLM失败的原因（如时间单位转换错误、并行化不充分等），展现了很强的分析深度。
-   **实验严谨性**：统计显著性检验、对无效回答的处理（视为错误）、成本分析等细节，增强了实验结论的可靠性。

### 8. 不足与局限

-   **理想化假设**：实验设定假设“无限资源”（如无限代理和工具），这在现实中不成立。当资源有限时，问题复杂度会上升至NP难。论文在附录中讨论了Petri网作为扩展，但实验未覆盖。
-   **任务简化**：仅以“时间”为单一优化目标，忽略了现实中其他重要因素（如成本、用户偏好、质量风险等）。
-   **数据生成偏差**：数据集部分依赖GPT模型进行标注，虽然经过质量审核，但可能存在引入自身偏差的风险。论文也提到，复杂任务的稀疏性和可能的标注偏差（如高复杂度任务时间单位更一致）可能部分解释了性能波动。
-   **应用局限性**：论文明确指出，即使采用PLaG，LLM在处理复杂异步规划时性能仍急剧下降，这动摇了其作为通用智能体或数字设备模拟器的可靠性和可扩展性。该方法更适合作为辅助工具或提示策略，而非终极解决方案。
-   **可解释性问题**：虽然PLaG提升了性能，但没有深入探讨LLM内部是如何利用图结构进行推理的。“构建图”比“显式给出图”效果更好的原因，论文也只是提出了猜想（提示位置效应），未进行进一步验证。
-   **语言和领域限制**：实验仅基于英文的日常生活任务。模型对自然语言中简洁/经济表达式的鲁棒性差，其表现高度依赖于提示措辞，存在泛化问题。

（完）
