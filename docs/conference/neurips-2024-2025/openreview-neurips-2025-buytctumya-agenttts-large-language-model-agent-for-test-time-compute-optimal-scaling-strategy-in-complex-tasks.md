---
title: "AgentTTS: Large Language Model Agent for Test-time Compute-optimal Scaling Strategy in Complex Tasks"
title_zh: AgentTTS：面向复杂任务测试时计算最优扩展策略的大型语言模型智能体
authors: "Fali Wang, Hui Liu, Zhenwei DAI, Jingying Zeng, Zhiwei Zhang, Zongyu Wu, Chen Luo, Zhen Li, Xianfeng Tang, Qi He, Suhang Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BuYtcTUMyA"
tags: ["query:mas-routing"]
score: 8.0
evidence: 优化多阶段任务计算资源分配，类似子任务路由
tldr: 测试时扩展研究多局限于单阶段任务，而真实世界多为多阶段复杂任务。本文提出AgentTTS智能体，为多阶段任务中每个子任务选择合适模型并分配预算，实现计算最优扩展。实验表明该方法在精度与成本平衡上超越固定分配策略，为多跳推理等场景的资源配置提供指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1300, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1156, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1159, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 722, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 579, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1458, \"height\": 1612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1323, \"height\": 1358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1302, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1301, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1158, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1160, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1304, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1291, \"height\": 1045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1451, \"height\": 2056, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-buytctumya/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 976, \"height\": 712, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 768, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 712, \"height\": 563, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 966, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-buytctumya/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 279, \"label\": \"Table\"}]"
motivation: 多阶段复杂任务中各子任务需要不同能力模型和预算，现有扩展策略未考虑此异构性。
method: 提出AgentTTS框架，将模型选择和预算分配建模为组合优化问题，并利用LLM智能体进行决策。
result: 在多个多阶段推理任务上，AgentTTS在相同计算预算下获得更高准确率。
conclusion: 自适应资源分配是多阶段LLM系统提升效率的关键。
---

## Abstract
Test-time scaling (TTS) enhances the performance of large language models (LLMs) by allocating additional compute resources during inference. However, existing research primarily investigates TTS in single-stage tasks; while many real-world problems are multi-stage complex tasks, composed of a sequence of heterogeneous subtasks with each subtask requires LLM of specific capability. Therefore, we study a novel problem: the test-time compute-optimal scaling in multi-stage complex tasks, aiming to select suitable models and allocate budgets per subtask to maximize overall performance. TTS in multi-stage tasks introduces two fundamental challenges: (i) The combinatorial search space of model and budget allocations, combined with the high cost of inference, makes brute-force search impractical. (ii) The optimal model and budget allocations across subtasks are interdependent, increasing the complexity of the compute-optimal search. To address this gap, we conduct extensive pilot experiments on four tasks across six datasets, deriving three empirical insights characterizing the behavior of LLMs in multi-stage complex tasks. Informed by these insights, we propose AgentTTS, an LLM-agent-based framework that autonomously searches for compute-optimal allocations through iterative feedback-driven interactions with the execution environment. Experimental results demonstrate that AgentTTS significantly outperforms traditional and other LLM-based baselines in search efficiency, and shows improved robustness to varying training set sizes and enhanced interpretability.

---

## 论文详细总结（自动生成）

# AgentTTS 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有测试时扩展（Test-time Scaling, TTS）研究主要聚焦于单阶段任务（如数学推理、代码生成），而现实世界中大量应用是**多阶段复杂任务**（如检索-生成问答、瀑布式软件开发、多智能体任务自动化），每个子任务需要不同能力的模型，且子任务间存在相互依赖。
- **核心问题**：在多阶段复杂任务中，给定总计算预算，如何为每个子任务选择合适的模型并分配计算预算，以最大化整体任务性能？这一问题面临两大挑战：
  1. **组合搜索空间巨大**：模型选择和预算分配的组合导致搜索空间指数级增长，穷举搜索不可行。
  2. **子任务间相互依赖**：前序子任务的预算分配会影响后续子任务的最优模型和预算，增加了搜索复杂度。
- **整体含义**：提出一种高效的搜索策略，能够处理大且相互依赖的搜索空间，实现计算最优的测试时扩展。

## 2. 论文提出的方法论

### 核心思想
基于三个从初步实验中总结出的经验洞察（Insight），设计一个LLM智能体框架，通过迭代反馈驱动与环境交互，自动搜索计算最优的模型与预算分配。

### 关键技术细节
- **三个洞察**：
  - **洞察1**：不同子任务对模型大小（大/小）有不同偏好。例如，检索任务偏好大模型，而问答任务小模型在有限预算下更优。
  - **洞察2**：增加测试时计算量初期提升性能，但达到最优预算后继续增加会带来边际递减甚至负收益（如融合瓶颈）。
  - **洞察3**：前序子任务的预算分配影响后序子任务的缩放行为和最优配置。例如，高检索质量可减少下游问答所需的计算量。

- **AgentTTS框架**：包含三个核心组件：
  - **Agent**：基于LLM（如GPT-o3-mini），负责生成候选试验和搜索指南。初始阶段依据洞察1生成初始候选试验；后续阶段依据洞察2和洞察3生成新的指南和候选。
  - **Environment**：执行候选试验的实际运行环境，将配置转换为可执行脚本，在小训练集上运行并返回性能反馈。
  - **Archive**：存储历史试验、反馈和生成的指南，支持迭代学习。

- **算法流程**（Algorithm 1）：
  1. 初始化：Agent根据洞察1为每个子任务选择初始模型（比较不同模型在固定预算下的性能），生成第一批候选试验。
  2. 环境执行候选试验并返回性能反馈。
  3. 循环直到停止条件：
     - Agent根据反馈和洞察2/3生成探索指南（如确定最优采样范围、平衡子任务间分配）。
     - 更新存档。
     - Agent根据新指南生成下一批候选试验。
     - 环境执行并反馈。
  4. 返回存档中性能最佳的试验。

- **计算预算度量**：以最小模型（3B）在最低计算消耗任务上单次推理的FLOPs为单位，将不同模型和任务的预算归一化（定理1）。默认使用推理FLOPs作为成本度量。

## 3. 实验设计

### 数据集/场景（6个数据集，4类任务）
| 任务类型 | 数据集 | 子任务 |
|---------|--------|--------|
| 检索式问答 | 2WikiMultiHopQA, HotpotQA | 检索 + 问答 |
| 知识图谱问答 | CWQ, WebQSP | 知识检索 + 问答 |
| 任务自动化 | TaskBench | 任务分解 + 工具选择 + 参数预测 |
| 自动软件开发 | ChatDev | 编码 + 静态测试 + 动态测试 |

### 对比基线
- **传统方法**：随机搜索（Random Search）、贝叶斯优化（Bayesian Optimization, BO）
- **LLM-based方法**：LLM_ZS（零样本直接生成）、MLCopilot（基于相似任务经验）、AgentHPO（通用超参优化智能体）
- 所有方法均适配为多阶段预算分配问题。

### 评估指标
- 检索F1（Ret_F1）、精确匹配（EM）、参数F1（p-F1）、一致性（Consistency）等。

### 设置
- 50次搜索迭代，训练集50样本，测试集500样本。
- 使用GPT-o3-mini作为搜索智能体。
- 默认总预算 = 所有子任务使用最大模型单次推理所需最小预算之和。

## 4. 资源与算力

- **文中明确说明**：每轮试验在单块**NVIDIA H100 80GB HBM3 GPU**上运行。
- **未明确说明**：所使用的GPU总数、并行训练方式或总计算时长（仅报告了各方法搜索时间，如AgentTTS在2Wiki上搜索2.5小时，ChatDev上64.3小时）。
- **预算度量**：采用推理FLOPs归一化，但未报告具体FLOPs总量。

## 5. 实验数量与充分性

- **主实验**：6个数据集上对比5种基线，报告搜索轨迹和最终测试集性能（图3、表1）。
- **消融实验**：在2WikiMultiHopQA上分别移除每个洞察，验证其贡献（图4d）。
- **鲁棒性分析**：改变训练集大小（50/75/100样本）（图4a-c）；改变总预算（500/850/2000）（图6）；改变温度（表2）；采用API价格作为预算度量（图7）。
- **可解释性案例**：呈现了AgentTTS与AgentHPO的完整搜索过程对比（图15）。
- **充分性评价**：实验覆盖多任务多场景，对比基线全面，消融和鲁棒性实验设计合理。但**缺乏误差棒**（仅单次运行），由于计算成本高未报告方差，这是公平性方面的不足。

## 6. 论文的主要结论与发现

1. **AgentTTS显著优于所有基线**：在搜索效率和最终测试集性能上均表现最佳，且收敛更快。
2. **三个洞察的有效性**：消融实验表明，去除任何一个洞察都会导致性能下降或搜索延迟。
3. **鲁棒性**：AgentTTS对训练集大小变化不敏感，而其他方法在训练集较小时性能下降明显。
4. **可解释性**：AgentTTS能生成明确的搜索指南（如“检索应使用大模型，问答应使用小模型”），便于理解决策过程。
5. **计算最优配置特征**：通常前序子任务（如检索）应分配更多资源（大模型，少量采样），后序子任务（如问答）应使用小模型较多采样，达到平衡。

## 7. 优点

- **方法创新**：首次将测试时扩展的专用经验洞察整合到LLM智能体搜索中，针对多阶段任务设计，而非直接套用通用超参优化。
- **实验全面**：覆盖4类6个数据集，对比传统和LLM两类基线，进行了充分的消融和鲁棒性分析。
- **低成本高效**：搜索时间远低于基线（如2Wiki上仅2.5小时 vs AgentHPO 8.3小时）。
- **可解释性强**：智能体生成的指南直观可理解，有助于信任和调试。
- **泛化性好**：在不同预算水平、成本度量（FLOPs/API价格）下均有效。

## 8. 不足与局限

- **静态任务假设**：仅适用于子任务数量和顺序固定的静态多阶段任务，不适用于动态运行时子任务可变的场景（如语音助手）。
- **潜在风险放大**：重复采样可能放大LLM的幻觉和对抗攻击风险（如越狱、后门注入），安全方面未提供防护。
- **未报告统计显著性**：由于计算成本高，实验仅单次运行，缺乏误差棒和置信区间。
- **搜索空间限制**：仅探索了模型大小和采样数两个维度，未考虑其他TTS策略（如树搜索、自修正）。
- **依赖LLM能力**：智能体使用GPT-o3-mini，其性能上限会影响搜索结果；也未测试其他LLM作为智能体。
- **数据集规模有限**：训练集仅50样本，虽验证了鲁棒性，但更大规模下的表现未知。

（完）
