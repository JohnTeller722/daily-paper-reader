---
title: LLM-Assisted Semantically Diverse Teammate Generation for Efficient Multi-agent Coordination
title_zh: 基于LLM的语义多样队友生成实现高效多智能体协调
authors: "Lihe Li, Lei Yuan, Pengsen Liu, Tao Jiang, Yang Yu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Vhktpw6Vid"
tags: ["query:mas-routing"]
score: 4.0
evidence: 利用LLM生成语义多样的队友以促进多智能体协调
tldr: 训练可泛化多智能体代理需要多样化队友，但传统方法缺乏语义信息导致效率低。本文提出SemDiv，利用大语言模型在语义层面发现并学习多样化的协调行为——每次迭代生成自然语言描述的协调策略并转化为可执行策略。该方法显著提高了队友多样性生成效率和代理的泛化能力，是多智能体协调中路由策略研究的重要支撑。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1743, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1729, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1753, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 845, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1731, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1728, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1693, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1685, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhktpw6vid/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1691, \"height\": 595, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1755, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1780, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1780, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhktpw6vid/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 578, \"label\": \"Table\"}]"
motivation: 现有多样化队友生成方法缺乏语义信息，导致生成效率低且代理泛化性差。
method: 迭代利用LLM生成新的协调行为自然语言描述，并翻译为可执行策略来丰富队友池。
result: 在多智能体协调任务中，SemDiv生成的队友多样性更高，训练出的代理泛化能力显著提升。
conclusion: LLM的语义理解能力能有效提升多智能体协调中队友的多样性及代理的适应性。
---

## Abstract
Training with diverse teammates is the key for learning generalizable agents. Typical approaches aim to generate diverse teammates by utilizing techniques like randomization, designing regularization terms, or reducing policy compatibility, etc. However, such teammates lack semantic information, resulting in inefficient teammate generation and poor adaptability of the agents. To tackle these challenges, we propose Semantically Diverse Teammate Generation (SemDiv), a novel framework leveraging the capabilities of large language models (LLMs) to discover and learn diverse coordination behaviors at the semantic level. In each iteration, SemDiv first generates a novel coordination behavior described in natural language, then translates it into a reward function to train a teammate policy. Once the policy is verified to be meaningful, novel, and aligned with the behavior, the agents train a policy for coordination. Through this iterative process, SemDiv efficiently generates a diverse set of semantically grounded teammates, enabling agents to develop specialized policies, and select the most suitable ones through language-based reasoning to adapt to unseen teammates. Experiments show that SemDiv generates teammates covering a wide range of coordination behaviors, including those unreachable by baseline methods. Evaluation across four MARL environments, each with five unseen representative teammates, demonstrates SemDiv's superior coordination and adaptability. Our code is available at https://github.com/lilh76/SemDiv.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在开放多智能体环境中，智能体常需要与未见过的、具有不同协调行为的队友合作（例如自动驾驶遇到不同风格的人类驾驶员）。传统的多智能体强化学习（MARL）方法容易过度拟合训练队友的行为，导致泛化能力差。
- **关键挑战**：现有队友生成方法（如随机种子训练、添加多样性正则项、降低策略兼容性等）主要追求策略层面的差异，但生成的队友缺乏**语义信息**，导致两个问题：一是探索队友策略空间效率低（仅靠策略差异而非发现新协调行为）；二是智能体无法利用语言描述进行推理，只能通过试错适应，效率低且成本高。
- **整体含义**：若能生成**语义层面多样**的队友（即用自然语言描述不同协调行为），将显著提升智能体的适应能力和训练效率，对于开放环境中的多智能体协调具有重要理论和应用价值。

## 2. 方法论

### 核心思想
- 提出 **SemDiv**（Semantically Diverse Teammate Generation）框架，利用大语言模型（LLM）在语义层面发现并生成多样化的协调行为，进而训练对应的队友策略，并通过持续学习使智能体掌握多种协调技能。

### 关键技术细节
1. **迭代生成语义多样的协调行为**（Section 3.1）
   - 每次迭代，LLM 行为生成器基于任务描述、指令和已有行为列表，生成一个新颖的、以自然语言描述的协调行为 \( b_n \)。
   - 利用反馈机制（如行为相似性信息）指导 LLM 避免重复，确保多样性。

2. **从行为到队友策略的落地**（Section 3.2）
   - LLM 奖励生成器将行为 \( b_m \) 转化为可执行的奖励函数代码（Python 函数），并嵌入环境。
   - 使用标准 MARL 算法（如 VDN 或 MAPPO）训练队友策略 \(\pi_{tm}^m\)，优化目标为：
     \[
     J(\tilde{\pi}_{ag}, \pi_{tm}^m) = \mathbb{E}\left[ \sum_t \gamma^t (\lambda_1 r_t + \lambda_2 \hat{r}_t^m) \right]
     \]
     其中 \( r_t \) 为任务奖励，\(\hat{r}_t^m\) 为生成的奖励，\(\lambda_2\) 从 1 衰减到 0。
   - **策略验证**：检查队友是否能完成任务、是否真正展示了预期行为、是否与之前队友显著不同（通过公式 (2) 判断差异）。

3. **智能体持续学习与执行**（Section 3.3）
   - **多策略头架构**：每个智能体网络由一个共享特征提取器 \( f_{\phi_i} \) 和多个策略头 \( h_{\psi_{i,j}} \) 组成，每个策略头对应一个队友的协调模式。
   - **持续学习**：当生成新队友时，冻结旧策略头，仅更新特征提取器和新策略头，并加入正则项：
     \[
     \max_{\phi_i, \psi_{i,n+1}} J(\pi_{ag}, \pi_{tm}^{n+1}) - \alpha \frac{1}{|N_{ag}|} \sum_i \|\phi_i - \bar{\phi}_i\|_p
     \]
     防止灾难性遗忘。
   - **执行阶段**：LLM 选择器根据新队友的自然语言描述，从已有策略头中选择最匹配的一个，无需试错交互。

### 算法流程（文字说明）
```
1. 初始化空队友集合。
2. 循环直到生成足够数量队友：
   a. LLM 行为生成器提出新行为 b（自然语言）。
   b. LLM 奖励生成器将 b 转化为奖励函数代码。
   c. 使用 MARL 训练队友策略。
   d. 验证队友：是否完成任务？是否展示预期行为？是否与已有队友不同？
   e. 若有效，保存该队友，并为智能体添加新策略头，训练智能体与该队友协调。
3. 测试时，LLM 根据新队友描述选择最佳策略头。
```

## 3. 实验设计

### 使用场景 / 数据集
- 四个经典 MARL 协调环境：
  - **Level-Based Foraging (LBF)**：网格世界，两个智能体需合作收集食物。
  - **Predator-Prey (PP)**：两个捕食者需合作捕捉猎物（鹿需同时捕捉，兔子可单捕）。
  - **StarCraft Multi-Agent Challenge v2 (SMACv2)**：两个己方单位对战四个敌方单位。
  - **Google Research Football (GRF)**：两名足球运动员（Johnson 和 Turing）需通过配合得分。

### 测试队友
- 每个环境手动设计 **5 个** 具有不同协调偏好的未见队友（如 GRF 中偏好一次传球后射门、让特定球员得分等）。

### 对比的基线方法
- 两阶段种群训练方法：
  - **FCP**：不同随机种子生成队友。
  - **MEP**：添加最大熵正则项。
  - **LIPO**：最小化队友间兼容性。
- 迭代方法：
  - **Macop**：通过最小化与智能体的兼容性生成队友。
- 变体与消融：
  - **SemDiv-PBT / Macop-PBT**：使用 SemDiv 或 Macop 的队友作为第一阶段的种群。
  - **SemDiv-R1 / -R2**：选择最高 R1 或 R2 的策略头上限。
  - **SemDiv-Dist**：基于行为描述嵌入距离选择头部。
  - **LLM-Agent**：仅用 LLM 作为策略（无 MARL）。
- **Oracle**：测试队友的自我对弈性能，作为上界。

## 4. 资源与算力

- 文献明确提及每轮 OpenAI API 调用约花费 **$0.10**，整个项目约 **$300**。
- 未明确说明 GPU 型号、数量和训练时长。但给出了每个队友和智能体的训练步数（如 GRF 中队友训练 10^7 步，智能体训练 10^7 步），推测使用了常见 GPU（如 NVIDIA V100/A100）进行多轮实验。

## 5. 实验数量与充分性

- 实验覆盖了 **4 个环境**，每个环境 **5 个未见过队友**，共 **20 个测试场景**。
- 每个方法使用 **3 个随机种子**，报告均值和标准差。
- 进行了消融实验：
  - 多策略头 vs. 单策略头（*-PBT）。
  - 不同选择策略（LLM 选择 vs. 嵌入距离选择）。
  - 不同 LLM 质量（GPT-4o vs. GPT-4o-mini）。
- 分析实验：
  - 队友数量对性能的影响（图 5）。
  - 行为描述歧义的影响（图 7(a)(b)）。
- 实验设计较为充分，对比客观（使用相同队友数量、相同算法基础），但未在更多复杂真实场景（如自动驾驶、机器人）中验证。

## 6. 主要结论与发现

- SemDiv 在所有环境上显著优于所有基线，平均任务成功率 (R1) 比最佳基线 Macop 提高 **19%**，满足队友偏好成功率 (R2) 提高 **39%**。
- 语义层面的探索能发现策略层面无法生成的行为（如多次传球配合）。
- 多策略头架构比单策略头更适应多样化队友，持续学习能避免灾难性遗忘。
- LLM 选择策略头优于基于嵌入距离的方法，体现了语言推理的价值。
- 仅用 LLM 而不用 MARL 在复杂环境中性能急剧下降（GRF 中 R1 仅 0.14），说明 MARL 不可或缺。

## 7. 优点

- **创新性**：首次将 LLM 引入多智能体队友生成，在语义层面实现高效探索，突破传统仅依赖策略差异的局限。
- **可解释性**：生成的队友行为具有自然语言描述，便于人类理解与调试，也为智能体提供了语言推理的基础。
- **框架通用性**：与现有 MARL 算法兼容，可轻松集成不同算法（VDN、MAPPO）。
- **实验全面**：覆盖多个领域环境，并包含详尽的消融和鲁棒性分析。
- **工程实现**：代码开源（GitHub），便于复现。

## 8. 不足与局限

- **与 Oracle 仍有差距**：性能不如自我对弈上界，表明生成的队友可能未覆盖所有真实世界行为。
- **LLM 依赖**：需要频繁调用 LLM（行为生成、奖励生成、验证、选择），成本较高且可能受限于 LLM 的推理能力。使用更小模型（GPT-4o-mini）时性能下降。
- **环境限制**：仅在相对简单的离散/连续控制环境中测试，未在需要大量通信或与真实人类交互的场景中验证。
- **实验规模**：每个环境只测试了 5 个未见队友，可能不足以全面评估泛化性能。
- **潜在的偏差风险**：LLM 可能生成存在偏见的协调行为（如偏向某种角色），且框架未主动处理公平性问题。
- **未讨论在线适应或终身学习**：当前需要预先训练一系列策略头，无法在交互中动态学习全新协调方式。

（完）
