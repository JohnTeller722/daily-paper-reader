---
title: Guided Search Strategies in Non-Serializable Environments with Applications to Software Engineering Agents
title_zh: 非序列化环境中的引导搜索策略及其在软件工程智能体中的应用
authors: "Karina Zainullina, Alexander Golubev, Maria Trofimova, Sergei Polezhaev, Ibragim Badertdinov, Daria Litvintseva, Simon Karasik, Filipp Fisin, Sergei Skvortsov, Maksim Nekrashevich, Anton Shevtsov, Boris Yangel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NMdWQXosFs"
tags: ["query:mas-routing"]
score: 4.0
evidence: 提出引导搜索策略用于多步推理任务，涉及测试时搜索的配置选择
tldr: 大型语言模型在多步推理中性能不稳定，现有搜索技术在不支持状态序列化的环境中受限。本文研究了两种互补的引导搜索策略：基于多样性和基于状态探索，并在软件工程智能体任务上验证了有效性。实验表明这些策略能显著提升平均性能，为多步推理的资源配置提供了实用方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 693, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 753, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 755, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 755, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 752, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 757, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 852, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 864, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 847, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 853, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nmdwqxosfs/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 869, \"height\": 656, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nmdwqxosfs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1677, \"height\": 861, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nmdwqxosfs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1402, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nmdwqxosfs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nmdwqxosfs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nmdwqxosfs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1866, \"height\": 558, \"label\": \"Table\"}]"
motivation: 多步推理任务中LLM性能不稳定，需要有效的测试时搜索策略。
method: 提出了适用于非序列化环境的引导搜索策略，包括多样性引导和状态探索两种方式。
result: 在软件工程智能体任务上，引导搜索策略显著提高了成功率。
conclusion: 引导搜索是提升LLM多步推理性能的有效手段，可避免昂贵的状态恢复。
---

## Abstract
Large language models (LLMs) have recently achieved remarkable results in complex multi-step tasks, such as mathematical reasoning and agentic software engineering. However, they often struggle to maintain consistent performance across multiple solution attempts. One effective approach to narrow the gap between average-case and best-case performance is guided test-time search, which explores multiple solution paths to identify the most promising one. Unfortunately, effective search techniques (e.g. MCTS) are often unsuitable for *non-serializable* RL environments, such as Docker containers, where intermediate environment states cannot be easily saved and restored. We investigate two complementary search strategies applicable to such environments: 1-step lookahead and trajectory selection, both guided by a learned action-value function estimator. On the SWE-bench Verified benchmark, a key testbed for agentic software engineering, we find these methods to double the average success rate of a fine-tuned Qwen-72B model, achieving $40.8$\%, the new state-of-the-art for open-weights models. Additionally, we show that these techniques are transferable to more advanced closed models, yielding similar improvements with GPT-4o.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大型语言模型（LLMs）在多步推理或智能体任务中，平均性能远低于其最高潜能（即存在“average-case vs. best-case”差距）。例如，在 SWE-bench Verified 上，同一个 GPT-4o 智能体多次尝试的成功率方差很大。
- **背景**：现有引导搜索方法（如 MCTS）能够通过系统探索多条路径来提升一致性，但它们要求环境状态可序列化——即能够保存、复制和回退中间状态。然而，许多实际环境（如 Docker 容器）是非序列化的：状态不可逆、无法复制，导致 MCTS 等方法无法直接应用。
- **动机**：需要开发适用于非序列化环境的引导搜索策略，以缩小 LLM 智能体性能差距。

## 2. 方法论
### 核心思想
利用学习到的动作‑价值函数 \(Q^\pi(s,a)\) 引导搜索，在无法回退的状态下进行前向探索。

### 关键技术细节
1. **1‑步前瞻（1-step lookahead）**：
   - 在每个决策步，从基策略 \(\pi\) 中采样 \(K\) 个候选动作 \(a'_k\)。
   - 使用 critic 模型 \(Q^\pi(s,a')\) 对每个候选评分，选择最高分动作执行。
   - 无需分支或回退，只进行一次前向选择。

2. **轨迹选择（Trajectory Selection）**：
   - 生成 \(N\) 条完整轨迹（全部独立运行，可并行）。
   - 对每条轨迹的最后一步（动作 \(a_{T-1}\)，状态 \(s_{T-1}\)），用 critic 预测 \(Q^\pi(s_{T-1}, a_{T-1})\) ——该值等于轨迹终端奖励（0/1）的折扣和。
   - 选取评分最高的轨迹作为最终答案。

3. **组合策略**：两种方法可以叠加——先用 1‑步前瞻生成更优的轨迹，再对多条轨迹进行选择。

4. **Critic 模型训练**：
   - 使用 TD(\(\lambda\)) 目标（\(\lambda=0.7\) 最优）从训练数据中估计折扣奖励‑to‑go。
   - 基模型为 LLaMA3.1-70B，将 token 嵌入映射为标量输出，仅对每个智能体步末尾特殊 token 计算损失（L2 loss）。
   - 训练数据通过 bootstrapping 迭代收集（在 6500 个训练问题上生成约 8 万条轨迹），并用策略标识符条件化 critic，使其能适应不同策略。

5. **基策略**：Qwen2.5-72B 经过多轮 bootstrapping 微调（仅保留成功轨迹微调），称为 Qwen-based policy。

### 算法流程（文字说明）
- **1‑步前瞻**：初始化环境；在每个时间步循环：采样 \(K\) 个动作 → critic 评分 → 选最优动作执行 → 直到终止。
- **轨迹选择**：并行运行 \(N\) 次完整策略（可包含 1‑步前瞻）→ 收集所有轨迹 → critic 对每条轨迹的最后一步评分 → 选出最高分轨迹。

## 3. 实验设计
- **数据集/场景**：
  - 主数据集：**SWE-bench Verified**（全量 500 个问题）。
  - 消融/分析子集：**Verified-50**（随机选取 50 个问题，平衡计算效率与统计可靠性）。
- **基准方法**：
  - 基策略：Qwen-based policy (72B) 和 GPT-4o-based agent (SWE-agent)。
  - 对比协议：Default（单次运行直到自然终止）、Until Submitted（允许最多 10 次重试直到 agent 提交）、“Pass@N”（N 次中至少一次成功）、“Random sampling”（随机选一次）。
  - 对比的系统（表2）：SWE-Gym、SWE-Fixer、Lingma Agent 等。
- **指标**：成功率（SR%），并报告标准误差（SEM）或多次重复（10 个随机种子）。
- **消融与分析**：
  - Critic 超参数：\(\lambda\)（0→1 扫描）、\(\gamma\)（0.86→1 扫描）。
  - 采样温度 \(T\) 与候选数 \(K\) 的协同影响（图8）。
  - 轨迹选择中候选数 \(N\) 的缩放（图3、图10）。
  - 训练数据集大小对 critic 性能的影响（图13）。
  - 不同基模型作为 critic 的对比（LLaMA3.1-70B vs Qwen2.5-72B 等，表5）。

## 4. 资源与算力
- 论文未明确说明 GPU 型号、数量或训练时长。
- 仅给出超参数：batch size=128、sequence length=32768、优化器 AdamW、学习率 2e-6（critic）和 4e-6（基策略）、训练步数 459（critic）和 215（基策略）、4~6 个 epoch。
- 数据收集通过 bootstrapping 在多轮迭代中生成 80,000 条轨迹，需要大量推理资源，但具体 GPU 用量未报告。

## 5. 实验数量与充分性
- **实验数量**：丰富。
  - 多种方法对比（表1）：基策略、1‑步前瞻、轨迹选择（N=5,10）、组合（K=4, N=5,10）；在 Verified-50 上重复 10 次统计 SEM，在全量上报告单次或平均。
  - 参数扫描（λ、γ、T、K、N、数据集大小）。
  - 基模型选择（表5）。
  - “Until submitted” 机制对比（表4）。
  - 在 GPT-4o 上也进行了子集实验（表1、图9-11）。
- **充分性与公平性**：
  - 统计显著性通过 SEM 和多次重复体现。
  - 对比了开源和闭源模型，但 critic 从未见过 GPT-4o 轨迹，因此对 GPT-4o 的泛化能力是偏低的，但结果仍显示提升，这反而增强了说服力。
  - 消融实验覆盖了主要超参数，验证了设计选择（如 TD(λ) 优于 MC）。
  - 未进行跨域（如数学推理）验证，但问题本身是实际软件工程场景。

## 6. 主要结论与发现
1. **1‑步前瞻** 和 **轨迹选择** 在非序列化环境中均显著提升成功率，且两者组合可以翻倍（Qwen-based policy 上从 22.8% 提升至 44.07% in Verified-50）。
2. 在全量 SWE-bench Verified 上，组合策略（K=8, N=15）达到 **40.8%**，创下开源模型新 SOTA。
3. 方法可迁移至高级闭源模型 GPT-4o，同样获得约 2 倍提升（22.0% → 40.0%）。
4. Critic 训练中 TD(λ)（λ=0.7）优于纯 MC（λ=1）和一步 TD（λ=0），说明平衡偏差-方差至关重要。
5. 折扣因子 γ 越接近 1，性能越好，因为鼓励更长的规划视野。
6. 性能随测试时计算量（K 和 N）增加而持续改善，未观察到饱和（在实验范围内）。

## 7. 优点
- **方法简洁实用**：两种策略均无需修改环境，直接应用于现有 Agent 框架，且可并行化，延迟可控。
- **理论贡献**：明确定义了“非序列化环境”，指出其对传统搜索方法的限制，并提供了可行替代方案。
- **实验严谨**：多轮随机种子、SEM 统计、参数扫描、消融实验充分；在开源和闭源模型上验证泛化性。
- **实际价值**：在 SWE-bench 上达到开源 SOTA，展示了“用计算换能力”的清晰曲线。
- **Critic 训练技术**：使用 TD(λ) 降低方差，并通过策略标识符条件化使得一个 critic 可服务于多种策略。

## 8. 不足与局限
- **泛化风险**：仅在 SWE-bench Verified 一个基准上测试，未在数学推理、其他智能体环境（如 Web 导航）上验证，通用性存疑。
- **Critic 泛化短板**：critic 对未见过的策略（如 GPT-4o）的评分在中期轨迹上区分能力弱（图11 停滞），可能导致价值欺骗（value hacking）。
- **价值欺骗问题**：1‑步前瞻可能使 critic 对失败轨迹也给出较高分数（图7 中绿色 vs 红色在后期差距缩小），需要主动再训练来缓解。
- **非序列化定义的绝对性**：作者承认通过重放动作序列可近似复制状态（尽管昂贵且随机），说明非序列化并非完全不可解，只是成本高。MCTS 理论上仍可通过重放实现，但本文未探索。
- **计算成本**：组合方法（K=8, N=15）需要大量独立环境运行，资源开销大；虽然可并行，但总 token 消耗可观。
- **未研究更复杂的搜索结构**：如 Beam Search、Best‑First Search 在非序列化环境中的适配性未讨论。
- **实验完全性**：未在更大的 SWE-bench Lite 或其它排名的榜单上报告结果，仅验证了开源 SOTA。

（完）
