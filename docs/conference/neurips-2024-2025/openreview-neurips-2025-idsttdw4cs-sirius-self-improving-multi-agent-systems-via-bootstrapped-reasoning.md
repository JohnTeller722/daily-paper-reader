---
title: "SiriuS: Self-improving Multi-agent Systems via Bootstrapped Reasoning"
title_zh: SiriuS：通过自举推理实现自改进多智能体系统
authors: "Wanjia Zhao, Mert Yuksekgonul, Shirley Wu, James Zou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IDSTtDw4Cs"
tags: ["query:mas-routing"]
score: 4.0
evidence: 自改进多智能体系统通过经验库引导推理
tldr: SiriuS提出自改进的多智能体优化框架，通过构建高质量推理轨迹经验库来训练智能体，虽然不直接研究路由，但通过优化智能体推理间接提升多智能体系统的路由效果。实验表明该方法在复杂任务上提升了系统表现。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 514, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 681, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 418, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-idsttdw4cs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 686, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1009, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-idsttdw4cs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 534, \"label\": \"Table\"}]"
motivation: 多智能体系统依赖脆弱的手动设计和启发式方法，优化困难。
method: 构建经验库，保留成功推理轨迹，用于多智能体系统的自优化。
result: 在多个复杂任务上提升了多智能体系统的协作效果。
conclusion: 通过经验库驱动的自改进，有效优化了多智能体系统的推理能力。
---

## Abstract
Multi-agent AI systems powered by large language models (LLMs) are increasingly applied to solve complex tasks. However, these systems often rely on fragile, manually designed prompts and heuristics, making optimization difficult. A key challenge in optimizing multi-agent systems is acquiring suitable training data for specialized agents. We introduce SiriuS, a self-improving, reasoning-driven optimization framework for multi-agent systems. Central to our approach is the construction of an experience library: a repository of high-quality reasoning trajectories. The library is built by retaining reasoning steps that lead to successful outcomes, providing a robust training set for optimizing multi-agent system. Additionally, we introduce a library augmentation procedure that refines unsuccessful trajectories, further enriching the library. SiriuS boosts performance by 2.86% to 21.88% on reasoning and biomedical QA and enhances agent negotiation in competitive settings. Our results show that SiriuS enhances multi-agent performance while generating reusable data for self-correction and self-play enhancement in the future.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：多智能体大语言模型（LLM）系统在复杂任务中表现出色，但严重依赖手工设计的提示和启发式规则，导致优化困难。核心挑战在于**难以获取针对每个智能体的高质量训练数据**（多智能体信用分配问题）以及对多个相互影响的组件的敏感性。
- **整体含义**：作者提出 **SiriuS 框架**，通过构建“经验库”来存储导致成功的推理轨迹，并利用这些轨迹进行监督微调，从而让多智能体系统能够**自我改进**，无需细粒度的中间监督。该方法旨在提供一种**可扩展的、自举的优化范式**。

## 2. 方法论
- **核心思想**：从成功协作的交互轨迹中学习有用的模式。将每次协作视为一个整体，筛选出最终结果正确的完整推理路径，将其加入经验库；对于失败的轨迹，则通过**轨迹增强**（利用额外智能体提供基于正确答案的反馈、重新生成答案并重述）来丰富经验库。
- **关键技术细节**：
  - 多智能体系统形式化定义为元组 ⟨S, A, T, R, N, G⟩，每个智能体使用策略 πᵢ。
  - **训练流程**（Algorithm 1）：迭代 T 轮。每轮中：
    1. **动作采样**：每个智能体根据自身策略和历史输出生成响应。
    2. **轨迹评估与增强**：根据奖励阈值 ε，将高奖励轨迹加入“好轨迹集” C；对低奖励轨迹执行增强（反馈 → 再生 → 重述 → 再次评估）。
    3. **监督微调**：在 C 上对每个智能体进行 SFT，更新策略参数。
  - **增强细节**（Appendix C, Algorithm 2）：对于错误回答，先由外部智能体基于正确答案生成反馈，再让原智能体根据反馈重新生成，最后将重生成的结果重述为直接的解题步骤，再参与后续协作并重新评估。

- **公式/算法文字说明**：无复杂数学公式；主要流程如上所述。

## 3. 实验设计
- **数据集与场景**：
  - **问题求解设置**：College Physics（MMLU+GPQA+TheoremQA 组合）、College Chemistry（类似组合）、PubMedQA（生物医学问答）。
  - **Actor-Critic 设置**：在 PubMedQA 上测试，包含演员、评判员、评论家三个角色。
  - **竞争设置**：三个博弈游戏——资源交换（Resource Exchange）、最后通牒（Ultimatum）、买卖谈判（Sell & Buy）。
- **基准方法**：Single-Agent、STaR、CoMM（Prompt Multi-Agent System）、TextGrad、DSPy (MIPROv2)。
- **骨干模型**：GPT-3.5-turbo、GPT-4o-mini、Llama-3.2-3B-instruct（部分实验）。
- **评估指标**：准确率（问题求解、Actor-Critic）、胜率/收益（竞争设置）。

## 4. 资源与算力
- **未明确说明**：论文在实验计算资源部分的回答为“No”，未提供 GPU 型号、数量、训练时长等具体信息。仅提及使用 OpenAI 的 Fine-tuning API 进行监督微调，模型推理采用 API 调用。因此无法得知算力消耗。

## 5. 实验数量与充分性
- **实验数量**：涵盖三大类设置，共约 6 个不同任务（物理、化学、PubMedQA、三个博弈游戏）。每个任务均有多组基线对比，以及消融实验（表 4、表 5 的 ablation）。
- **充分性与公平性**：
  - 提供了误差线（± 标准差），表明多次运行的结果。
  - 对比了多种主流方法（训练型 + 提示型 + 优化型），覆盖不同模型大小。
  - 消融实验验证了各组件（联合优化、角色专用、数据增强、额外迭代）的必要性。
  - 竞争设置中补充了泛化实验（不同初始化资源）。实验设计较为全面、客观。

## 6. 主要结论与发现
- SiriuS 在**所有任务上一致优于所有基线**，性能提升幅度为 **2.86% 至 21.88%**（绝对准确率）。
- 在 Actor-Critic 设置中，SiriuS 显著提高了**真实阳性准确率**（TP Accuracy），即正确判断回答是否需要修正，避免了过度修正导致正确回答被改错。
- 竞争设置中，SiriuS 优化后的智能体在资源交换、最后通牒、买卖谈判中均获得更高胜率或收益，且具备**泛化能力**（迁移到不同初始资源设置）。
- 消融研究表明：**联合优化多个智能体**比单独优化一个更好；**专用角色微调**比合并成一个模型更好；**数据增强模块**有效；**额外迭代**能带来微小但持续的提升。

## 7. 优点
- **自改进无需中间监督**：仅利用最终结果奖励（outcome reward），避开信用分配困难。
- **经验库 + 轨迹增强**：既保留成功案例，又通过反馈和重生成将失败案例转化为有用训练数据，显著增加数据利用率。
- **框架通用**：适用于问题求解、演员-评论家、竞争博弈等多种多智能体交互结构。
- **实验覆盖全面**：跨模型（GPT-3.5/4o-mini/Llama）、跨任务（推理/QA/谈判），且包含泛化测试。

## 8. 不足与局限
- **依赖基础模型能力**：SiriuS 的性能受限于底层 LLM 的推理和指令遵循能力，若基础模型弱，效果会打折扣。
- **信用分配仍存挑战**：虽然通过全局轨迹学习绕过直接分配，但根本上仍未解决语言系统中非结构化推理的精确归因问题。
- **交互协议设计复杂**：当前实验采用固定的角色结构和交互顺序，如何自动设计最优协议尚未解决。
- **计算资源未透明**：未提供训练算力需求，难以评估方法的实际计算成本。
- **偏差风险**：继承自基础模型的偏见可能被放大；竞争设置中可能被滥用于不公平谈判。

（完）
