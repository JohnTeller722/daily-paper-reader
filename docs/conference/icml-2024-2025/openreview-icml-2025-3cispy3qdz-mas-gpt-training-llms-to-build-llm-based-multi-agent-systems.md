---
title: "MAS-GPT: Training LLMs to Build LLM-based Multi-Agent Systems"
title_zh: MAS-GPT：训练LLM构建基于LLM的多智能体系统
authors: "Rui Ye, Shuo Tang, Rui Ge, Yaxin Du, Zhenfei Yin, Siheng Chen, Jing Shao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3CiSpY3QdZ"
tags: ["query:mas-routing"]
score: 7.0
evidence: 生成包含智能体路由配置的MAS代码
tldr: 本文简化了构建基于LLM的多智能体系统的流程，将其转化为生成任务。通过一致性数据构建管道，训练MAS-GPT模型直接根据用户查询输出可执行的MAS代码，其中隐式定义了智能体间的路由与交互。该方法降低了手动路由配置成本，实验表明生成系统性能接近甚至超越人工设计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1710, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1716, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 1055, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1666, \"height\": 2324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3cispy3qdz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1668, \"height\": 561, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 758, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1743, \"height\": 1443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1735, \"height\": 880, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1727, \"height\": 1765, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1227, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3cispy3qdz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1585, \"height\": 1336, \"label\": \"Table\"}]"
motivation: 现有MAS构建依赖手动配置或调用高级LLM，成本高且适应性差。
method: 将MAS构建视为生成任务，训练MAS-GPT输出可执行代码。
result: MAS-GPT能生成与查询匹配的MAS代码，性能可达到手动配置水平。
conclusion: 生成式方法为多智能体路由设计提供了高效自动化途径。
---

## Abstract
LLM-based multi-agent systems (MAS) have shown significant potential in tackling diverse tasks.
However, to design effective MAS, existing approaches heavily rely on manual configurations or multiple calls of advanced LLMs, resulting in inadaptability and high inference costs.
In this paper, we simplify the process of building an MAS by reframing it as a generative language task, where the input is a user query and the output is a corresponding MAS.
To address this novel task, we unify the representation of MAS as executable code and propose a consistency-oriented data construction pipeline to create a high-quality dataset comprising coherent and consistent query-MAS pairs.
Using this dataset, we train MAS-GPT, an open-source medium-sized LLM that is capable of generating query-adaptive MAS within a single LLM inference. The generated MAS can be seamlessly applied to process user queries and deliver high-quality responses. Extensive experiments on 9 benchmarks and 5 LLMs show that the proposed MAS-GPT consistently outperforms 10+ baseline MAS methods on diverse settings, indicating MAS-GPT's high effectiveness, efficiency and strong generalization ability.
The codes are released at \url{https://github.com/rui-ye/MAS-GPT}.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有基于LLM的多智能体系统（MAS）构建方式主要依赖手动配置（如MetaGPT、ChatDev）或多次调用高级LLM进行自适应调整（如GPTSwarm、AFlow），导致**适应性差**（MAS固定、无法随查询变化）和**推理成本高**（需要多轮LLM调用、依赖验证集）。
- **目标**：将构建MAS的过程简化为一个生成式语言任务——输入用户查询，直接输出可执行的MAS，使构建MAS像查询ChatGPT一样简单高效。
- **整体含义**：提出MAS-GPT，一种经过训练的LLM，能在单次推理中生成查询自适应的MAS，显著降低部署复杂度，提升泛化能力，推动MAS的大规模实际应用。

## 2. 方法论
### 核心思想
- 将构建MAS重新定义为生成任务，用一个LLM（MAS-GPT）根据用户查询生成对应的可执行MAS代码，随后该MAS直接处理查询得到最终答案。
### 关键技术细节
1. **统一MAS表示为可执行代码**：将MAS描述为Python函数（forward函数），其中：
   - 每个agent的prompt定义为变量
   - LLM调用定义为函数调用
   - agent间交互通过字符串拼接实现
2. **一致性导向的数据构建管道**（四个步骤）：
   - **(1) 构建查询池和MAS池**：从开源基准收集可验证的查询；实现40+种MAS设计（包括已有方法如多智能体辩论、自一致性、自精炼等，以及手动设计）。
   - **(2) 评估查询-MAS对**：对每个查询和每个MAS进行推理，得到正确/错误分数（1/0）。
   - **(3) 面向间一致性（Inter-Consistency）的选择**：对相似查询分组（基于元数据或嵌入），每组选择累积正确率最高的MAS作为代表，提高数据一致性，帮助模型学习可泛化模式。
   - **(4) 面向内一致性（Intra-Consistency）的精炼**：利用高级LLM（GPT-4o）调整MAS使其更贴合查询（如修改agent指令），并生成推理过程（reasoning）解释查询与MAS之间的逻辑关联；仅保留得分不下降的精炼MAS。
3. **监督微调（SFT）**：使用精炼后的(query, reasoning, MAS code)三元组，基于Qwen2.5-Coder-32B-Instruct进行微调，训练MAS-GPT。

## 3. 实验设计
### 数据集/场景
- **训练**：来自MATH、GSM8K、MBPP、MMLU、SciQ，涵盖数学、代码、通用QA。
- **测试**：共9个基准，包括：
  - 数学：MATH, GSM8K, GSM-Hard, AIME-2024
  - 代码：HumanEval, HumanEval+
  - 通用QA：MMLU
  - 科学：GPQA, SciBench（其中AIME-2024、HumanEval+、GPQA、SciBench属于域外）
### 对比方法
- 10+基线：Single, Chain-of-Thought, Self-Consistency, LLM-Debate, Self-Refine, Quality-Diversity, SPP, AgentVerse, GPTSwarm, DyLAN；以及任务特定方法AFlow（在MATH上优化）、ChatDev。
### 评估指标
- 数学和QA：用LLM提取答案并与真实答案比较。
- 代码：用测试用例计算pass rate。
### 使用的LLM
- 作为MAS驱动LLM（执行生成的MAS）：Llama-3-70B-Instruct, Qwen2.5-72B-Instruct, GPT-4o-mini, o1-preview, DeepSeek-R1。

## 4. 资源与算力
- **训练配置**：16个A100 GPU，有效batch size 32，训练3个epoch，学习率1e-5。
- 文中未明确说明训练总时长，但提到“一次训练，推理可无限次使用”。
- 注意：MAS-GPT本身为32B参数，推理成本远低于之前需要多次调用高级LLM的方法。

## 5. 实验数量与充分性
- **主实验结果**：在8个基准（域内+域外）上用Llama-3-70B驱动，与10个基线对比，MAS-GPT平均准确率65.47%，高于第二的61.58%（Self-Consistency）（表1）。
- **不同LLM背板**：用Qwen2.5-72B和GPT-4o-mini验证，MAS-GPT均获最佳平均（表3）。
- **强推理LLM增强**：在AIME-2024上，MAS-GPT提升o1-preview 13.3%、DeepSeek-R1 10.0%（图4a）。
- **与任务特定方法对比**：超越AFlow（图4b）；在代码任务上优于ChatDev（附录表9）。
- **成本-性能权衡**：MAS-GPT以最低推理次数达到最高性能（图4c）。
- **消融实验**：验证间一致性选择、内一致性精炼（调整MAS和引入推理过程）均有效（表4）。
- **缩放分析**：数据量越大、模型越大，性能越好（图5）。
- **生成MAS新颖性**：约70-90%的测试时生成MAS在训练集中未见过（表5），并提供了三个案例展示查询针对性、泛化性和新颖性。
- **评估充分性**：实验覆盖多个领域、多种LLM、多种基线，包含域外泛化测试，消融设计合理，整体充分且客观公平。

## 6. 主要结论与发现
- MAS-GPT在9个基准上一致优于所有基线方法，平均提升显著（如比第二名高3.89%）。
- 具有强泛化能力：在域外基准（GPQA、SciBench）上同样表现优异。
- 能进一步增强顶级推理模型（o1、DeepSeek-R1）的推理能力。
- 单次推理即可生成高质量MAS，成本远低于现有自适应方法。
- 数据管道中的间一致性选择和内一致性精炼对模型学习至关重要。
- 模型规模和数据量均有可扩展性。

## 7. 优点
- **创新性**：首次将MAS构建转化为生成任务，用训练好的LLM直接输出可执行MAS，避免了手动或多次LLM调用。
- **通用性与效率**：训练一次后，推理时仅需一次LLM调用（32B模型），即可获得适配任意查询的MAS，且性能超越传统方法。
- **数据管道设计**：间一致性保证相似查询对应相同高效MAS，内一致性增强查询-MAS对齐，使模型学到可泛化模式。
- **实验广泛**：涵盖多领域、多LLM、多基线，包括域外测试，结果可靠。
- **开源代码**：提供完整代码库，便于复现与扩展。

## 8. 不足与局限
- **MAS库多样性有限**：初始MAS池仅40+设计，可能未覆盖所有有效模式；训练数据因使用映射策略（多个查询映射到同一个强MAS）可能引入偏差。
- **缺少工具集成**：当前仅支持代码执行，未集成多模态处理、网络搜索等工具，限制了MAS能力。
- **仅使用SFT**：未探索强化学习（RL）等方法，模型无法自主探索和优化MAS生成。
- **计算成本**：虽然推理成本低，但数据构建和训练仍需要较高资源（16×A100），且依赖高级LLM（GPT-4o）进行精炼。
- **泛化边界**：虽在域外任务表现良好，但实验主要限于数学、代码、科学QA，尚需在更多真实世界任务（如对话、规划）中验证。
- **评估方式**：部分基准采用LLM提取答案，可能引入额外误差；代码任务使用静态测试用例，未考虑动态环境。

（完）
