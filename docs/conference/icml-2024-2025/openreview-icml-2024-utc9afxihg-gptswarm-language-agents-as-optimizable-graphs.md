---
title: "GPTSwarm: Language Agents as Optimizable Graphs"
title_zh: GPTSwarm：语言代理作为可优化图
authors: "Mingchen Zhuge, Wenyi Wang, Louis Kirsch, Francesco Faccio, Dmitrii Khizbullin, Jürgen Schmidhuber"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=uTC9AFXIhg"
tags: ["query:mas-routing"]
score: 8.0
evidence: 将LLM代理建模为可优化图，通过边优化实现代理间通信路由
tldr: 现有基于LLM的问题求解方法分散且缺乏统一形式。本文提出GPTSwarm，将LLM代理描述为可优化图——节点处理数据或查询LLM，边表示信息流。通过自动优化节点提示和边连接（即路由），GPTSwarm实现了多智能体协作的高效编排，实验证明其在多种复杂任务上优于手动设计方法，为动态多智能体路由提供了通用框架。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1708, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 794, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 794, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 778, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 646, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1730, \"height\": 1275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1364, \"height\": 1028, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1741, \"height\": 1849, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 865, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 658, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-utc9afxihg/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 649, \"height\": 632, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 872, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1796, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1791, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1752, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1437, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1730, \"height\": 2230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1753, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1749, \"height\": 2375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1755, \"height\": 1971, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-utc9afxihg/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1774, \"height\": 663, \"label\": \"Table\"}]"
motivation: 现有LLM代理提示技术分散，缺乏统一框架来优化多代理间的协作与信息路由。
method: 将LLM代理建模为计算图，提出节点优化（提示改进）和边优化（连接变更）两种自动优化器。
result: 在多个基准上，GPTSwarm自动优化后的多代理系统超越了手动设计的提示工程方案。
conclusion: 图视角使多代理路由和协作的自动优化变得可行，为复杂LLM系统设计提供了新方法论。
---

## Abstract
Various human-designed prompt engineering techniques have been proposed to improve problem solvers based on Large Language Models (LLMs), yielding many disparate code bases. We unify these approaches by describing LLM-based agents as computational graphs. The nodes implement functions to process multimodal data or query LLMs, and the edges describe the information flow between operations. Graphs can be recursively combined into larger composite graphs representing hierarchies of inter-agent collaboration (where edges connect operations of different agents). Our novel automatic graph optimizers (1) refine node-level LLM prompts (node optimization) and (2) improve agent orchestration by changing graph connectivity (edge optimization). Experiments demonstrate that our framework can be used to efficiently develop, integrate, and automatically improve various LLM agents. Our code is public.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

随着大语言模型（LLM）的广泛应用，涌现了大量人工设计的提示工程方法（如Chain of Thought、ReAct、Tree of Thought、Reflexion等）以及多智能体框架（如AutoGPT、MetaGPT等）。这些方法虽然有效，但彼此独立、代码库分散，缺乏统一的视角来描述和组合智能体系统。此外，智能体之间的协作路由（communication and orchestration）通常由人类手动设计，难以自动优化和动态调整。

本文的核心动机是：**如何统一、模块化地描述LLM智能体系统，并自动优化其结构与交互模式？** 整体含义是：通过将语言智能体形式化为可优化的计算图，我们不仅可以统一现有方法，还能自动改进节点提示（node-level prompts）和智能体间的连接拓扑（edge-level orchestration），从而提升任务性能。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 2.1 核心思想：语言智能体作为可优化计算图

- **节点（Node）**：代表基本操作，如LLM推理、工具使用、函数调用等。
- **图（Graph）**：单个智能体由一组节点和有向边构成的有向无环图（DAG），定义信息流与执行顺序。
- **复合图（Composite Graph / Swarm）**：多个智能体图通过附加边连接形成更高层次的协作图，边表示智能体间的通信通道。
- **优化对象**：图结构可以自动优化，包括**节点优化**（改进每个节点的提示）和**边优化**（改进智能体间的连接模式）。

### 2.2 关键技术细节

#### 图定义
- 单智能体图：\( G = (N, E, F, o) \)，输入 \( x \)，按拓扑序执行节点，每个节点接收前驱输出和输入，应用函数 \( f_n \)，最终输出节点 \( o \) 给出答案。
- 复合图：给定一组智能体图，通过添加跨智能体边 \( \mathcal{E} \) 得到 \( G_{\mathcal{E}} = (N', E_{\mathcal{E}}, F', o') \)，执行方式相同。

#### 边优化（Edge Optimization）
- 目标：选择最优附加边组合以最大化任务效用 \( u_\tau(G_{\mathcal{E}}) \)。
- 离散优化困难，转化为连续优化：参数化概率分布 \( D_\theta \)，每个可能边 \( e_i \) 对应一个实数参数 \( \theta_i \in [0,1] \)，表示该边被包含的概率（需保证DAG无环）。
- 优化算法：使用REINFORCE（Williams, 1992）进行策略梯度优化，梯度估计为：
  \[
  \nabla_\theta \mathbb{E}_{G\sim D_\theta}[u_\tau(G)] \approx \frac{1}{M}\sum_{i=1}^M \hat{u}_\tau(G_i) \nabla_\theta \log p_\theta(G_i)
  \]
  其中 \( M \) 为采样图数，\( \hat{u}_\tau \) 为无偏效用估计。

#### 节点优化（Node Optimization）
- 每个节点 \( n \) 有一个可优化的提示 \( p_n \) 和功能描述 \( d_n \)。
- 迭代过程：采样输入 \( x \)，执行图得到各节点输入输出对，存入历史 \( h_n \)；然后使用提示优化器 \( I \)（如OPRO风格）基于历史、当前提示和描述生成改进提示。
- 算法流程（Algorithm 3）：初始化空历史，每次迭代执行图，更新历史，对每个节点应用 \( I \) 更新提示。

## 3. 实验设计：数据集、场景、基准与对比方法

论文在四个基准上进行了实验：

| 数据集/任务 | 类型 | 主要目的 | 对比方法 |
|------------|------|----------|----------|
| **MMLU**（多选题知识问答） | 对抗性设置（k个诚实+ k个对抗智能体） | 验证边优化能否过滤有害智能体 | 单IO智能体基线、全连接图、随机连接、Multiagent Debate、DyLAN |
| **MMLU**（协作设置） | 不同角色的IO智能体 | 验证边优化能否提升协作性能 | 单IO基线 |
| **Mini Crosswords**（5×5填字游戏） | 组合三个不同智能体（ToT、Reflexion、CoT） | 验证边优化能否自动发现更优算法结构 | 各智能体单独、Best-of-Three、等期望边数的随机分布、原始ToT（GPT-4） |
| **HumanEval**（代码生成） | 单个ReAct风格智能体 | 验证节点优化能否自动改进提示 | 无优化的初始提示 |
| **GAIA**（通用AI助手基准） | 多智能体（7个ToT）加上自洽（Self-Consistency） | 展示框架的通用性和模块组合能力 | GPT-3.5、GPT-4、GPT-4-Turbo、AutoGPT、GPT-4 with Plugins |

此外，在Mini Crosswords上还进行了边优化后的节点优化联合实验。

## 4. 资源与算力

论文附录F中的Table 11详细列出了各实验的成本、token消耗和时间。主要使用API调用（GPT-3.5-Turbo和GPT-4-Turbo），未说明使用本地GPU。典型开销示例：
- Mini Crosswords边优化：$77.42，约2.82小时（GPT-3.5-Turbo）。
- HumanEval带优化：$28.46，约1.49小时。
- GAIA单智能体（ToT）：$2.21，约1.05小时。
- 未提及使用特定GPU型号或本地训练资源，所有实验均通过OpenAI API完成。

## 5. 实验数量与充分性

论文在不同数据集上开展了多组实验，涵盖了：
- **MMLU对抗性实验**：4种配置（1T1A, 3T3A, 5T5A, 7T7A），每种重复5个种子。
- **MMLU协作实验**：7个不同角色，平均5个种子。
- **Mini Crosswords**：边优化3次重复（报告标准差），节点优化1次，与多种基线对比（Best-of-Three、等边数分布、原始ToT）。
- **HumanEval**：3次重复，显示优化曲线和最终精度。
- **GAIA**：多组消融（不同智能体类型、数量、决策策略），每种5次运行。

总体实验数量较多，涵盖了对抗性、协作性、代码生成和多模态工具使用场景。但存在一些局限性：
- 部分实验只用了单一LLM后端（GPT-3.5或GPT-4），未测试其他模型。
- Mini Crosswords的测试集仅20个问题，规模较小。
- 未在更大规模的智能体系统（>10个智能体）上验证。

## 6. 论文的主要结论与发现

- **边优化能有效过滤有害智能体**：在MMLU对抗性实验中，优化后的群集性能恢复至单智能体基线水平，去除了对抗智能体的负面影响。
- **边优化能自动发现更优协作模式**：在Mini Crosswords上，优化后的群集（0.575）显著优于初始随机分布（0.465）和Best-of-Three（0.320），而且优化后分布与等期望边数的随机分布（0.510）对比，表明改进来自结构而非边缘数量。用GPT-4评估优化分布达到0.800，超越之前的SOTA ToT（0.675）。
- **节点优化能自动改进提示**：在HumanEval上，经过8次迭代优化，准确率从0.76提升至0.88。
- **框架通用性强**：在GAIA上，通过组合7个ToT智能体和自洽策略，取得平均18.45%的准确率，显著高于GPT-4-Turbo（9.7%）和AutoGPT（4.85%），接近GPT-4 with Plugins（14.6%但该基线手动选择工具）。

## 7. 优点：方法或实验设计上的亮点

- **统一性**：将多种提示工程和智能体框架统一为计算图，易于理解和复用。
- **自动优化**：首次将图结构优化（边优化）引入多智能体系统，无需人工设计编排。
- **分层优化**：节点优化和边优化可独立或联合进行，提供了灵活的改进手段。
- **实验设计巧妙**：对抗性实验清晰验证了边优化的鲁棒性；Mini Crosswords通过控制边缘数排除了计算量的影响。
- **代码开源**：方便复现和扩展。

## 8. 不足与局限

- **实验规模有限**：Mini Crosswords仅20个问题，HumanEval 164个问题，GAIA验证集较小（约165个问题）。结果可能受数据集偏差影响。
- **LLM单一性**：主要使用GPT-3.5/4，未验证在其他LLM（如开源模型）上的表现。
- **节点优化方法较简单**：当前仅通过选择历史中的正面示例作为提示演示，未使用更复杂的提示优化技术（如梯度启发式、进化等）。
- **边优化效率**：REINFORCE需要采样多个图，每个图执行多次LLM调用，成本较高。未与其他更高效的图优化方法（如贝叶斯优化）比较。
- **未考虑循环图**：当前仅限于DAG，限制了某些需要反馈循环的场景（如Reflexion本身需要迭代，但论文中将其实现为链式DAG）。
- **可扩展性**：当智能体数量很大（>100）时，潜在边数组合爆炸，优化可能不实用。论文未讨论扩展性解决方案。
- **没有理论保证**：优化算法不保证全局最优，且实用函数可能噪声较大。

（完）
