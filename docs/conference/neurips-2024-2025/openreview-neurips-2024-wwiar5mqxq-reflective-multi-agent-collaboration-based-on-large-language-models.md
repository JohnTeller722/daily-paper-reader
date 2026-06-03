---
title: Reflective Multi-Agent Collaboration based on Large Language Models
title_zh: 基于大语言模型的反思式多智能体协作
authors: "Xiaohe Bo, Zeyu Zhang, Quanyu Dai, Xueyang Feng, Lei Wang, Rui Li, Xu Chen, Ji-Rong Wen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=wWiAR5mqXq"
tags: ["query:mas-routing"]
score: 5.0
evidence: 具有微调共享反射器的反思式多智能体协作框架，用于提示调优
tldr: COPPER提出了一种增强LLM多智能体协作的框架，通过自反思机制和微调共享反射器来优化智能体提示。使用反事实PPO算法训练反射器，智能体根据反事实奖励评估贡献，从而提高协作效率。实验表明，COPPER在多种多智能体任务中提升了性能，对多智能体协调路由有启发意义。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1338, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1340, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1341, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1340, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1340, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1340, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 424, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1429, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 514, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1339, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1343, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1341, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1474, \"height\": 833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1430, \"height\": 1425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wwiar5mqxq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1427, \"height\": 1644, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wwiar5mqxq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wwiar5mqxq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 210, \"label\": \"Table\"}]"
motivation: 现有LLM多智能体系统协作能力有限，需要更有效的反思和协调机制。
method: 提出COPPER框架，包含自反思和共享反射器，使用反事实PPO微调，自动调整智能体提示。
result: 在多种多智能体任务上，COPPER显著提升协作质量和任务完成率。
conclusion: 反思机制能有效增强LLM多智能体系统的协同工作能力。
---

## Abstract
Benefiting from the powerful language expression and planning capabilities of Large Language Models (LLMs), LLM-based autonomous agents have achieved promising performance in various downstream tasks. Recently, based on the development of single-agent systems, researchers propose to construct LLM-based multi-agent systems to tackle more complicated tasks. In this paper, we propose a novel framework, named COPPER, to enhance the collaborative capabilities of LLM-based agents with the self-reflection mechanism. To improve the quality of reflections, we propose to fine-tune a shared reflector, which automatically tunes the prompts of actor models using our counterfactual PPO mechanism. On the one hand, we propose counterfactual rewards to assess the contribution of a single agent’s reflection within the system, alleviating the credit assignment problem. On the other hand, we propose to train a shared reflector, which enables the reflector to generate personalized reflections according to agent roles, while reducing the computational resource requirements and improving training stability. We conduct experiments on three datasets to evaluate the performance of our model in multi-hop question answering, mathematics, and chess scenarios. Experimental results show that COPPER possesses stronger reflection capabilities and exhibits excellent generalization performance across different actor models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- 大型语言模型（LLM）驱动的自主智能体在各类下游任务中展现了强大能力，近年研究者开始构建多智能体系统以处理更复杂的任务。
- 现有方法通过手工设计智能体角色配置和协作机制来提升多智能体协作性能，但受限于 LLM 的上下文理解能力，难以充分释放协作潜力。
- 自然思路是收集大量协作数据进行微调，但这会损害模型的通用能力，与迈向通用人工智能（AGI）的愿景相悖。
- 本文提出利用**自反思机制**（self-reflection）优化协作过程：将环境的二元/标量奖励转化为语言反思，为后续尝试提供额外上下文。但直接从冻结的 LLM 中产生有用反思具有挑战性，且扩展到多智能体系统面临两大困难：
  - **信用分配问题**：环境回报只能反映所有智能体反思的整体贡献，无法评估单个智能体反思的贡献。
  - **资源消耗问题**：为每个智能体独立微调反射器会导致模型数量随智能体个数线性增长，不实用。
- 论文的研究动机：设计一个既能解决信用分配又能降低计算开销的反射式多智能体协作框架。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
提出 **COPPER** 框架（Counterfactual PPO Enhanced Shared Reflector），通过训练一个**共享反射器**（shared reflector）为所有智能体生成个性化反思；利用**反事实奖励**（counterfactual reward）评估每个智能体反思的独立贡献，解决信用分配问题。

### 2.2 关键技术细节
- **多智能体协作环境**：智能体按预定顺序轮流行动，通过共享消息池交流。引入上下文模型维护短期记忆，并加入长期记忆存储反思。
- **反思框架**：在每次尝试（trial）结束后，反射器根据智能体角色、所有智能体的轨迹和环境奖励生成文本反思，存入长期记忆，用于下一轮尝试的 prompt 优化。
- **反事实奖励构建**：
  1. 计算整体奖励：\( G_{i}^{k,\lambda} = r_{k,\lambda+1} - r_{k,\lambda} \)（先后两轮尝试的回报差）。
  2. 计算边际奖励：移除智能体 \( i \) 的反思（保持其他智能体反思不变），重新与环境交互得到新的奖励 \( \hat{r}_{k,\lambda+1} \)，则边际奖励 \( \hat{G}_{i}^{k,\lambda} = \hat{r}_{k,\lambda+1} - r_{k,\lambda} \)。
  3. 反事实奖励：\( \tilde{G}_{i}^{k,\lambda} = G_{i}^{k,\lambda} - \hat{G}_{i}^{k,\lambda} \)，反映该反思的独立贡献。
- **共享反射器训练**：采用 RLHF 三阶段：
  1. **监督微调（SFT）**：用反事实奖励为正的 (prompt, reflection) 对进行监督微调。
  2. **奖励模型训练**：训练回归模型 \( R_{\phi}^{\text{CF}} \) 预测反事实奖励，损失为 MSE。
  3. **PPO 优化**：基于奖励模型对 SFT 模型进行 PPO 微调，最大化期望奖励并加入 KL 散度惩罚项。
- 使用 LoRA 进行参数高效微调，基座反射器为 LongChat-7B-16k（也可替换为 Llama-3-8B-16k）。

## 3. 实验设计

### 3.1 数据集与场景
| 数据集 | 场景 | 任务描述 |
|--------|------|----------|
| HotPotQA | 多跳问答 | 需要多步检索推理 |
| GSM8K | 数学 | 小学数学应用题 |
| Checkmate in One Move | 国际象棋 | 在给定局面中找出一步杀 |

### 3.2 Benchmark 与对比方法
- **基线方法**：
  - CoT（思维链）
  - ReAct（推理+行动）
  - Reflexion（扩展至多智能体，使用 GPT-3.5 或 LongChat 作为反射器，不微调）
  - Retroformer（单智能体反射训练，在多智能体环境下为每个智能体独立训练）
- **评估指标**：准确率（exact match）

### 3.3 实验设置
- 冻结 actor 模型：GPT-3.5-turbo；反射器：LongChat-7B-16k；奖励模型：GPT-2。
- 每个数据集随机抽取 100 个样本作为测试集，最多进行 5 轮尝试（trial）。
- 训练数据：HotPotQA 和 Checkmate 各 2,000 个任务，GSM8K 为 3,000 个任务。

## 4. 资源与算力

- 文中明确提到：使用 **四个 NVIDIA A800-80G GPU** 进行所有实验。
- 训练细节：SFT 阶段通过网格搜索调优 epoch（1-4）、batch size（64/128/256）、learning rate（1e-4/5e-4）；PPO 阶段 learning rate 为 1e-5/5e-5；奖励模型学习率 5e-5，epoch 3，batch size 16。
- **未明确说明单次训练时长或总的训练时间**。

## 5. 实验数量与充分性

- **主要实验**：在三个数据集上对比 5 种方法，每个方法绘制 5 轮曲线。
- **消融实验**（共 5 组）：
  - 无反事实奖励 (w/o CF)
  - 无 PPO (w/o PPO)
  - 无共享反射器 (非共享)
  - 无智能体角色信息 (no-profile)
  - 不同基座模型（Llama-3 替换 LongChat）
- **泛化实验**：将在 GPT-3.5 上训练的反射器直接用于 GPT-4。
- **其他实验**：反事实奖励用于 SFT 的对比；部分信息设置下的实验（附录）。
- **案例研究**：每个数据集提供一个实例展示反思效果。
- **评价**：
  - 实验覆盖了主要场景、多个消融变量和跨模型泛化，设计较为全面。
  - 但由于计算资源限制，测试集仅 100 个样本，可能导致结果波动，统计显著性未提供（如误差棒）。不过作者指出这与先前工作惯例一致。
  - 对比基线包括经典方法和单智能体扩展，公平性较好。

## 6. 主要结论与发现

1. COPPER 在所有三个数据集上均优于所有基线，经过 5 轮反思后，相对于初始成功率：
   - HotPotQA 提升 **31.8%**
   - GSM8K 提升 **18.5%**
   - Checkmate in One Move 提升 **86.4%**
2. 与 Retroformer 相比，COPPER 在多智能体场景下提升更快，收益更大。
3. 反事实奖励和 PPO 训练均对性能有显著贡献（消融实验验证）。
4. 共享反射器在生成个性化反思的同时降低了计算资源需求，且训练更稳定。
5. 训练好的反射器能泛化到更强的 actor 模型（GPT-4），接近 GPT-4 自身反射的性能。
6. 反事实奖励作为数据筛选标准，甚至能提升普通 SFT 的效果。

## 7. 优点

- **创新性**：首次针对多智能体系统提出反事实奖励以解决信用分配问题，并设计共享反射器以降低训练成本，两者结合形成完整框架。
- **方法设计完备**：从环境交互、反思生成、奖励构造到微调流程，各环节均有清晰定义和实现。
- **实验分析深入**：不仅做了主实验，还进行了多组消融、泛化、不同基座、不同 fine-tuning 策略的对比，案例研究直观展示了反思质量。
- **实用性强**：使用 LoRA 微调开源模型（LongChat/Llama-3），训练后可直接替换冻结 LLM 的反射器，便于实际部署。

## 8. 不足与局限

- **反事实奖励的数据成本高**：需要为每个智能体依次去除反思并重新与环境交互，导致额外的数据收集开销（作者承认这一点，但通过共享反射器和 MSE 奖励模型缓解）。
- **测试集规模偏小**：每个数据集仅 100 个样本，可能不够稳定，缺少多次重复实验的统计误差分析。
- **长期记忆机制简单**：采用滑动窗口固定容量，未使用更先进的向量嵌入或结构记忆（作者指出这是未来方向）。
- **协作范式有限**：仅实验了教师-学生和辩论两种范式，未覆盖更复杂的通信拓扑或动态角色分配。
- **部分设置简化**：例如实验仅在 5 轮内考察，未验证更多轮次的收敛行为；论文强调资源限制，但未提供详细的训练耗时。

（完）
