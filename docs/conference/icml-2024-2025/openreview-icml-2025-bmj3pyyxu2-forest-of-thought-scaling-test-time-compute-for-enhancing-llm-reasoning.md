---
title: "Forest-of-Thought: Scaling Test-Time Compute for Enhancing LLM Reasoning"
title_zh: 思维森林：扩展测试时计算以增强LLM推理
authors: "Zhenni Bi, Kai Han, Chuanjian Liu, Yehui Tang, Yunhe Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BMJ3pyYxu2"
tags: ["query:mas-routing"]
score: 8.0
evidence: 多树推理框架用于多跳推理中的最优路径选择
tldr: 现有推理方法如思维链和思维树通常执行单次推理，难以修正错误路径。Forest-of-Thought通过集成多个推理树并采用稀疏激活策略选择最相关的推理路径，提升了复杂逻辑问题的准确性和效率。该方法在多个推理任务上取得显著改进，为多跳推理中的最佳框架与资源配置提供了有效方案，可指导平衡准确率、时间和成本。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 810, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1744, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 893, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bmj3pyyxu2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1422, \"height\": 1097, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 886, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 877, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 885, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 1057, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 834, \"height\": 1448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 855, \"height\": 1630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 858, \"height\": 642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 378, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bmj3pyyxu2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 414, \"height\": 271, \"label\": \"Table\"}]"
motivation: 现有推理方法易陷入错误路径，缺乏多路径集成与选择机制。
method: 提出Forest-of-Thought框架，集成多个推理树并采用稀疏激活选择最佳路径。
result: 在复杂逻辑推理任务上提高了准确率和效率。
conclusion: 为多跳推理的路径选择提供了可扩展的解决方案。
---

## Abstract
Large Language Models (LLMs) have demonstrated remarkable abilities across various language tasks, but solving complex reasoning problems remains a significant challenge. While existing methods, such as Chain-of-Thought (CoT) and Tree-of-Thought (ToT), enhance reasoning by decomposing problems or structuring prompts, they typically perform a single pass of reasoning and may fail to revisit flawed paths, compromising accuracy. To address this limitation, we propose a novel reasoning framework called Forest-of-Thought (FoT), which integrates multiple reasoning trees to leverage collective decision-making for solving complex logical problems. FoT employs sparse activation strategies to select the most relevant reasoning paths, improving both efficiency and accuracy. Additionally, we introduce a dynamic self-correction strategy that enables real-time error correction, along with consensus-guided decision-making strategies to optimize both correctness and computational resources. Experimental results demonstrate that the FoT framework, combined with these strategies, significantly enhances the reasoning capabilities of LLMs, enabling them to solve complex tasks with greater precision and efficiency.

---

## 论文详细总结（自动生成）

基于提供的论文内容，以下是对《Forest-of-Thought: Scaling Test-Time Compute for Enhancing LLM Reasoning》的详细中文总结。

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的大语言模型（LLM）推理方法（如Chain-of-Thought、Tree-of-Thought）通常只进行一次完整的推理，无法在出现错误时回溯或修正，导致在处理复杂逻辑问题时准确率受限。
- **研究动机**：人类在面对复杂问题时，会从多个角度反复思考、验证并修正错误。受此启发，论文希望引入多路径探索与动态修正机制，提升LLM的复杂推理能力。
- **整体含义**：提出 **Forest-of-Thought (FoT)** 框架，通过集成多个推理树，利用**集体决策**、**稀疏激活**、**动态自校正**和**共识引导决策**，在不进行模型微调或反向传播的前提下，显著提升推理精度与效率。

---

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 构建多个独立的推理树（如ToT或MCTSr），每棵树从不同角度解决问题。
- 使用**稀疏激活**策略，仅保留在每层生成有效中间结果的树，过滤低质量路径，减少计算开销。
- 引入**动态自校正**：根据模型预测的logits分数动态触发错误修正，可结合数学规则或知识库进行校正。
- 设计**共识引导专家决策（CGED）** 策略：先进行多数投票，若不一致则由LLM专家评估后选择最佳答案。

### 关键技术细节
- **稀疏激活**：对每个推理树Ti，每层通过验证函数F(s_l)判断输出是否有效。仅当所有层均有效时，该树才被激活参与最终聚合。
- **输入增强**：从知识库B中检索与输入最相似的问题，并将该问题对应的答案或提示拼接到输入中，增强推理起点。
- **动态自校正**：监控每步的置信度分数，低于阈值时触发校正；若存在预定义规则（如Game of 24中的数字检查），则直接应用规则修正；否则基于先前知识重新生成推理。
- **CGED决策**：当多个树产生不一致答案时，由LLM专家比较各树的推理过程，做出最终判断。
- **早期终止**：若某树已经找到符合目标（如等于24）的解，则立即停止该树后续搜索，节省计算。

### 公式与算法
- 树i的结果：s_i = T_i(ε(x))，其中ε(x)是输入增强函数。
- 激活指示器：φ_i = 1 (若所有层输出有效) 否则0。
- 自校正：若score_i < threshold，则根据规则F(s_i)或基于知识生成s'_i。
- 决策：所有激活树的结果经CGED得到最终答案。

（算法1和算法2已在原文中给出文字描述，此处不再重复。）

---

## 3. 实验设计：数据集、基准、对比方法

| 数据集 | 说明 | 基准 | 对比方法 |
|--------|------|------|----------|
| **Game of 24** | 用四个数字通过加减乘除算得24，共95个问题 | 成功率（Success Rate） | IO, CoT, CoT-SC, GoT, ToT, BoT, XoT, **FoT** |
| **GSM8K** | 小学数学应用题 | 准确率（Accuracy） | Zero-Shot-CoT, MCTSr（不同rollout数）, 不同基模型（Llama3-8B、Mistral-7B、GLM-4-9B） |
| **MATH** | 数学竞赛题（分难度Level 1-4） | 准确率 | MCTSr vs FoT（n=4） |
| **AIME 2024** | 奥林匹克级数学题 | 准确率 | GPT-4o, rStar-Math, QwQ-32B-preview等 |

此外，还进行了消融实验（自校正、输入增强、稀疏激活的影响）、决策策略对比（Majority Vote、Math Expert、CGED）、阈值分析、不同子树数量扩展规律等。

---

## 4. 资源与算力

- **未明确说明**：论文没有给出训练所使用的GPU型号、数量、训练时长等细节。所有实验均基于**推理阶段**，即对预训练模型（如Llama3-8B-Instruct、Mistral-7B、GLM-4-9B、Qwen2.5-Math-7B-Instruct、QwQ-32B-preview）进行少样本或多步推理，未涉及微调。
- 只提到了使用了Huawei Ascend AI处理器及MindSpore、CANN框架，但无具体算力统计。

---

## 5. 实验数量与充分性

- **实验组数较多**：覆盖3个主要推理基准（Game of 24、GSM8K、MATH），以及AIME2024，在多个基模型上验证。
- **消融实验充分**：分别测试了自校正、输入增强、稀疏激活三个组件的影响；测试了不同子树数量（n=2,3,4,5,8）下的性能；比较了多种决策策略；分析了不同阈值对自校正的影响；对比了不同基模型的扩展规律。
- **公平性**：与现有最新方法（如ToT, CoT-SC, XoT, rStar-Math等）在同一标准数据集上比较，实验结果客观展示了FoT的优势。
- **潜在不足**：未在更大规模模型（如70B以上）上验证；未讨论计算成本与准确率的详细trade-off曲线（仅给出了LLM调用次数）；未进行统计显著性检验。

---

## 6. 论文的主要结论与发现

1. **FoT显著提升推理准确率**：在Game of 24上，FoT（8棵子树）达到96.84%成功率，远高于ToT（74%）和XoT（85.4%）。
2. **稀疏激活降低计算成本**：在保持最高准确率（77.98%）的同时，将LLM调用次数从32.32降至26.99，提升了效率。
3. **动态自校正和输入增强是关键**：将准确率从10.58%（无校正）提升至77.98%（加入校正与增强）。
4. **多树集成优势随子树数增加而扩大**：在GSM8K上，随着子树从2棵增至8棵，准确率单调上升（如Qwen2.5-7B从93.33%升至96.89%）。
5. **CGED决策优于多数投票或专家单独判断**：在n=5时，CGED比多数投票高2个百分点。
6. **FoT在不同基模型上表现出一致的标度律**：增加激活子树数，错误率持续下降，且优于单纯增加单个树深度的做法。

---

## 7. 优点

- **创新性**：将多树集成、稀疏激活、动态自校正、共识决策有机融合，构建了统一的推理增强框架。
- **实用性**：无需重新训练模型，仅在推理阶段增加少量计算即可大幅提升性能，易于部署。
- **鲁棒性强**：在多个数据集、多种基模型上稳定提升，且对超参数（如阈值）不太敏感（0.5为最优）。
- **实验全面**：不仅报告最终准确率，还深入分析了各组件贡献、扩展规律、决策策略差异，提供了清晰的指导。
- **可解释性**：稀疏激活机制保证了推理路径的合理性，动态自校正过程可追溯，便于调试。

---

## 8. 不足与局限

- **计算成本未完全量化**：虽然给出了LLM调用次数，但未提供实际运行时间或GPU小时数，难以直接对比资源消耗。
- **未覆盖更大模型**：最大模型为QwQ-32B-preview（32B参数），未在70B、120B等更大规模模型上验证，标度律的通用性存疑。
- **实验数据集范围有限**：主要集中在数学推理任务（Game of 24、GSM8K、MATH），未涉及常识推理（如StrategyQA）、代码生成、科学推理等更广泛场景。
- **动态自校正依赖阈值**：阈值为0.5时最佳，但该阈值可能因任务不同而变化，缺乏自适应调整机制。
- **决策策略的专家依赖**：CGED中的LLM专家可能引入额外偏差，且专家判断本身可靠性未充分验证。
- **未对比其他多路径集成方法如Self-Consistency（CoT-SC）的扩展**：CoT-SC也通过多次采样投票，但FoT强调树结构探索，两者区别未深入讨论。
- **公开数据集可能存在污染**：GSM8K、MATH等可能已出现在预训练数据中，影响泛化性评估。

---

（完）
