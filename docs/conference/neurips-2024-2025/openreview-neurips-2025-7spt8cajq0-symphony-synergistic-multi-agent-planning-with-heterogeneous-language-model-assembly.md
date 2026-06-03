---
title: "SYMPHONY: Synergistic Multi-agent Planning with Heterogeneous Language Model Assembly"
title_zh: SYMPHONY：异质语言模型组装的协同多智能体规划
authors: "Wei Zhu, Zhiwen Tang, Kun Yue"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7Spt8cAJq0"
tags: ["query:mas-routing"]
score: 7.0
evidence: 利用异质大语言模型组装的协同多智能体规划，实现高效任务路由
tldr: 单智能体MCTS规划面临探索不足、分支多样性低的问题。本文提出SYMPHONY，一种协同多智能体规划框架，通过组装异质大语言模型来生成搜索分支并评估奖励，从而增强探索能力。实验表明该方法在复杂推理任务上显著优于单智能体基线，为多智能体LLM架构中的高效任务路由提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7spt8cajq0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7spt8cajq0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7spt8cajq0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7spt8cajq0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1136, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7spt8cajq0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1141, \"height\": 612, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 433, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 489, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 486, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 574, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 981, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 919, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1455, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7spt8cajq0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1182, \"height\": 220, \"label\": \"Table\"}]"
motivation: 单智能体MCTS探索能力有限，分支多样性不足导致规划次优。
method: 构建多智能体框架，利用异质LLM协同生成分支并评估奖励。
result: 在多个推理基准上取得优于单智能体方法的性能。
conclusion: 多智能体组装可显著提升LLM规划中的探索和任务路由效率。
---

## Abstract
Recent advancements have increasingly focused on leveraging large language models (LLMs) to construct autonomous agents for complex problem-solving tasks. However, existing approaches predominantly employ a single-agent framework to generate search branches and estimate rewards during Monte Carlo Tree Search (MCTS) planning. This single-agent paradigm inherently limits exploration capabilities, often resulting in insufficient diversity among generated branches and suboptimal planning performance.
To overcome these limitations, we propose  $\textbf{SY}$nergistic $\textbf{M}$ulti-agent $\textbf{P}$lanning with $\textbf{H}$eter$\textbf{O}$geneous la$\textbf{N}$gauge model assembl$\textbf{Y}$ ($\textbf{SYMPHONY}$),  a novel multi-agent planning framework that integrates a pool of heterogeneous language model-based agents. 
By leveraging diverse reasoning patterns across agents, SYMPHONY enhances rollout diversity and facilitates more effective exploration.
Empirical results across multiple benchmark tasks show that SYMPHONY achieves strong performance even when instantiated with open-source LLMs deployable on consumer-grade hardware. When enhanced with cloud-based LLMs accessible via API, SYMPHONY demonstrates further improvements, outperforming existing state-of-the-art baselines and underscoring the effectiveness of heterogeneous multi-agent coordination in planning tasks.

---

## 论文详细总结（自动生成）

# 论文《SYMPHONY: Synergistic Multi-agent Planning with Heterogeneous Language Model Assembly》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

当前基于大语言模型（LLM）的自主智能体在复杂任务（如问答、代码生成、网页导航）中广泛应用，主流方法是将Monte Carlo Tree Search（MCTS）与单一LLM结合，通过反复查询同一模型生成搜索分支并估计奖励。然而，这种单智能体范式存在严重局限性：模型输出高度相似，缺乏分支多样性，导致探索能力不足，容易陷入局部最优，在多步推理和工具使用等复杂任务中表现欠佳。此外，为找到正确解可能需要大量采样，带来高昂的计算开销。

因此，论文提出SYMPHONY（Synergistic Multi-agent Planning with Heterogeneous Language Model Assembly），一种异质多智能体规划框架，通过组装多个具有不同预训练来源和推理风格的LLM，在MCTS中引入结构化的多样性，增强探索能力，提升规划性能。

## 2. 论文提出的方法论

### 2.1 核心思想
将MCTS与异质LLM智能体池结合，每个智能体在节点扩展、评估、反思等环节由UCB动态调度，并通过池式记忆共享和熵调制置信度评分实现协同，克服单模型采样多样性不足的缺陷。

### 2.2 关键技术细节

- **异质智能体池**：维护一组LLM（如Qwen2.5-7B、Mistral-7B、Llama-3.1-8B，或GPT-4、Qwen-Max、DeepSeek-V3等），每个智能体独立生成候选动作，带来互补的搜索视角。
- **UCB调度策略**：将智能体选择建模为多臂赌博机问题，使用上置信界公式动态调度：
  \[
  UCB(M_i^{(k)}) = \bar{Q}(M_i^{(k)}) + \alpha \cdot \sqrt{\frac{\ln N_{\text{total}}}{N(M_i^{(k)}) + 1}}
  \]
  其中 \(\bar{Q}\) 为历史效用均值，\(N\) 为调用次数，\(\alpha\) 控制探索–利用权衡。
- **池式记忆共享**：当轨迹失败时，由UCB选择的智能体生成自然语言反思，广播至整个智能体池，各智能体通过FIFO策略更新提示级记忆，无需参数更新即可实现行为调整。
- **熵调制置信度评分（EMCS）**：节点评估时，估计值 \(Z(s_t)\) 与置信度 \(C(s_t)\) 由智能体输出；最终奖励 \(R(s_t) = Z(s_t) \cdot (1 - E(s_t))\)，其中 \(E(s_t) = -C \ln C - (1-C)\ln(1-C)\)，熵最大时（\(C=0.5\)）惩罚最大，从而抑制不确定节点的贡献。

### 2.3 算法流程（文字描述）

1. 初始化智能体池、搜索树根节点 \(s_0\)，累计效用和调用计数。
2. 重复K次Rollout，每轮深度D：
   - **选择**：用UCT公式从当前节点选择待扩展节点。
   - **调度**：用UCB公式从池中选择一个智能体。
   - **扩展**：调度智能体生成n个候选动作，环境反馈新状态。
   - **评估**：再次调度智能体，用EMCS计算节点奖励。
   - **模拟**：执行低成本Rollout估计未来回报。
   - **反思与记忆共享**：若轨迹失败，调度智能体生成反思并广播更新所有智能体提示。
   - **反向传播**：将奖励沿访问路径更新Q值和访问次数。

## 3. 实验设计

### 3.1 数据集与场景
- **HotpotQA**：多跳问答，采用oracle反馈设置，评估Exact Match（EM）。
- **WebShop**：模拟电商平台，评估平均得分（Score）和成功率（SR）。
- **MBPP**：代码生成任务（Python和Rust），评估Pass@1。

### 3.2 Benchmark与对比方法
对比方法涵盖四大类：
- **线性推理**：CoT、CoT-SC
- **反馈驱动**：ReAct、Reflexion
- **结构化搜索**：ToT、RAP、LATS、Beam Retrieval
- **多智能体**：MASTER、MetaGPT、AgentVerse、AgentCoder

所有基线在统一设置下使用GPT-4作为骨干模型，SYMPHONY则分别用开源模型（SYMPHONY-S）和云端API模型（SYMPHONY-L）进行评测。

## 4. 资源与算力

论文明确说明：
- **SYMPHONY-S**：使用三个开源模型（Qwen2.5-7B、Mistral-7B、Llama-3.1-8B），可在三块RTX 4090（24GB）上运行，内存充裕。
- **SYMPHONY-L**：调用GPT-4（API）、Qwen-Max、DeepSeek-V3等云端模型。
- 未说明训练时长，仅提及推理效率和token消耗。在HotpotQA上，SYMPHONY-L平均每问题仅消耗7,906 token，远低于LATS（173,290）和MASTER（10,937）。

## 5. 实验数量与充分性

论文进行了多组实验：
- **主实验**：在三个数据集上对比所有基线，每种设置重复3次取均值。
- **消融实验**：移除UCB调度、记忆共享、EMCS三个组件，验证各模块贡献。
- **多样性分析**：量化不同智能体池配置下的分支多样性（4-Unique占比）与性能关联。
- **效率与成本分析**：比较搜索树节点扩展数、token消耗、模型调用频率。
- **超参数调优**：探索UCB系数α、MCTS参数n和K的影响。
- **鲁棒性分析**（附录F）：在WebShop上测试GPT-4与弱模型组合的效果，以及单智能体/推理模型的扩展。

实验设计较为全面，对比公平（统一基线设置），统计指标清晰，结果客观。

## 6. 主要结论与发现

- SYMPHONY在三个任务上均显著优于所有基线，包括单智能体方法（LATS、Reflexion）和多智能体方法（MASTER）。
- 异质智能体池显著提升分支多样性：在MBPP上，全三模型组合的4-Unique比例超过80%，而单模型低于20%。
- 消融实验表明，调度、记忆共享、EMCS各组件均不可或缺，去除任一组件均导致性能下降。
- SYMPHONY-L在无需昂贵模型主导调用下（GPT-4仅占40%调用），性能仍超越GPT-4-only基线，体现成本效益。
- 搜索树更紧凑：SYMPHONY-S在HotpotQA上平均仅扩展16.39个节点（LATS需66.65个节点，K=50），且性能更高。
- 即使在消费级硬件上（SYMPHONY-S），也取得与云端模型可比的强性能，具有实用价值。

## 7. 优点

1. **创新性**：首次将异质LLM池与MCTS系统性地结合，通过多模型固有差异性替代单一模型随机采样，从根本上提升分支多样性。
2. **模块化设计**：智能体池、调度、记忆共享、EMCS可独立替换，易于集成新模型。
3. **成本效率**：通过智能调度降低对昂贵模型的依赖，同时减小搜索树规模，推理成本显著低于现有树搜索方法。
4. **实验严谨**：包含多样性定量分析、消融、效率、超参数等全面实验，并附录了理论证明（严格改进性）和案例研究。
5. **可复现性**：公开代码（附匿名链接），提供详细超参数设置（附录D）。

## 8. 不足与局限

1. **环境依赖**：假设结构化环境提供可靠反馈（如oracle评估），难以直接推广到开放、动态、噪声场景。
2. **手动超参数**：依赖人工调节的轨迹数K、扩展宽度n、UCB系数α、agent组成等，缺乏自适应机制，增加应用门槛。
3. **未显式处理公平性与鲁棒性**：未考虑模型偏差放大、对抗输入、伦理风险等问题，在高风险应用中需额外防范。
4. **模型池同质化风险**：虽然论文强调异质性，但未深入探讨智能体选择策略如何应对池中模型性能差异大导致的不稳定。
5. **扩展性**：池式记忆共享采用FIFO缓冲区，随着任务积累可能遗忘长程经验，缺乏更高效的记忆架构。

（完）
