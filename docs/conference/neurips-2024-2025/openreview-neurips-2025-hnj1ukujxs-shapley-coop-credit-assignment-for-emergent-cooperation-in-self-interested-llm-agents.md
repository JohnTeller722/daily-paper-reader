---
title: "Shapley-Coop: Credit Assignment for Emergent Cooperation in Self-Interested LLM Agents"
title_zh: Shapley-Coop：面向自利LLM智能体的涌现合作信用分配
authors: "Yun Hua, Haosheng Chen, Shiqin Wang, Wenhao Li, Xiangfeng Wang, Jun Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HnJ1UkuJXS"
tags: ["query:mas-routing"]
score: 6.0
evidence: 针对自利LLM智能体的合作工作流，实现动态智能体协调
tldr: 针对开放环境中自利LLM智能体缺乏协调指南、导致社会困境的问题，本文提出Shapley-Coop合作工作流。该方法通过Shapley值进行信用分配，激励智能体自发形成临时合作。实验表明，该方法在博弈论场景中有效促进了涌现合作，提升了集体收益，为多智能体系统中的动态协调路由提供了借鉴。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1372, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1346, \"height\": 970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 797, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1022, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 590, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hnj1ukujxs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 598, \"height\": 532, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 758, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 766, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1175, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1197, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1173, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1201, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1171, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1203, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1172, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1175, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1168, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 890, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1438, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 822, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 900, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1150, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 940, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 928, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hnj1ukujxs/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 912, \"height\": 257, \"label\": \"Table\"}]"
motivation: 在开放环境中，自利的LLM智能体缺乏协调指南，导致社会困境和低效集体结果。
method: 提出Shapley-Coop合作工作流，基于Shapley值进行信用分配，激励自利智能体临时合作。
result: 在博弈论场景中，该方法促进了自主合作，提升了集体收益。
conclusion: 信用分配机制能有效引导自利LLM智能体实现涌现合作，为多智能体协调路由提供新思路。
---

## Abstract
Large Language Models (LLMs) are increasingly deployed as autonomous agents in multi-agent systems, and promising coordination has been demonstrated in handling complex tasks under predefined roles and scripted workflows.
However, significant challenges remain in open-ended environments, where agents are inherently self-interested and explicit coordination guidelines are absent. 
In such scenarios, misaligned incentives frequently lead to social dilemmas and inefficient collective outcomes.
Inspired by how human societies tackle similar coordination challenges—through temporary collaborations like employment or subcontracting—a cooperative workflow \textbf{Shapley-Coop} is proposed. 
This workflow enables self-interested Large Language Model (LLM) agents to engage in emergent collaboration by using a fair credit allocation mechanism to ensure each agent’s contributions are appropriately recognized and rewarded.
Shapley-Coop introduces structured negotiation protocols and Shapley-inspired reasoning to estimate agents’ marginal contributions, thereby enabling effective task-time coordination and equitable post-task outcome redistribution. 
This results in effective coordination that fosters collaboration while preserving agent autonomy, through a rational pricing mechanism that encourages cooperative behavior.
Evaluated in two multi-agent games and a software engineering simulation, Shapley-Coop consistently enhances LLM agent collaboration and facilitates equitable outcome redistribution, accurately reflecting individual contributions during the task execution process.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：大型语言模型（LLM）被广泛部署为多智能体系统中的自主代理，在预设角色和脚本化工作流下展现出强大的协作能力。然而，在缺乏协调规则的开放环境中，代理天然倾向于利己行为，导致社会困境（如囚徒困境）和低效的集体结果。
- **核心问题**：如何实现自利LLM代理之间的自主协作？关键挑战在于**信用分配**——公平评估每个代理的贡献，并设计合理的定价机制来对齐其异质目标。这一问题的实际意义在于，随着LLM越来越多地参与复杂的人机协作，公平报酬和问责机制依赖于有效的定价机制。
- **灵感来源**：人类社会通过临时合作（如雇佣、分包）来解决类似协调问题，这为论文提供了启发。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：受经济学中的庇古税和科斯定理启发，提出Shapley-Coop合作工作流，将Shapley值（合作博弈论中用于公平分配收益的概念）嵌入到LLM代理的推理中，通过“任务时间定价”和“事后奖励再分配”实现自发合作。
- **关键技术细节**：
  - **结构化协商协议**：定义标准化消息格式（如`<s>I propose to {action}</s>`），让代理明确表达意图、提出/响应定价方案，实现透明沟通。
  - **短期Shapley思维链**：在任务执行期间，代理通过启发式推理（定性而非精确数值）评估其行为对他人产生的是正外部性还是负外部性，从而决定是否需要提出/接受补偿（定价）。具体步骤包括：
    1. 定性评估长期集体奖励；
    2. 评估自身行为的边际贡献符号（正/负面）；
    3. 基于外部性类型构建谈判策略（正外部性→要求补偿，负外部性→提供补偿）。
  - **长期Shapley思维链**：任务完成后，代理根据完整轨迹追溯性地近似计算Shapley值，以确保公平信用分配。步骤包括：
    1. 计算集体总回报；
    2. 估计自身边际贡献；
    3. 应用Shapley公式加权平均各联盟下的边际贡献；
    4. 基于Shapley值进行谈判，提出/接受/拒绝奖励再分配方案。
- **流通程**：两个思维链形成闭环：短期指导实时合作，长期确保事后公平，共同维持激励对齐。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **实验场景**：
  - **Escape Room（密室逃脱）**：一个简单的社会困境场景（2个代理，一人拉杆付出-1成本，另一人开门获得+10收益），检验自发合作和公平分配能力。
  - **Raid Battle（副本战斗）**：更复杂的多轮、多代理环境（4个英雄合作击败Boss），每个英雄有技能（嘲讽、火球、治疗），其中火球个人奖励最高，但团队需要嘲讽和治疗才能获胜，这模拟了社会困境。设置了三个难度等级（Boss HP分别为2000/2500/3000）。
  - **ChatDEV（虚拟软件开发）**：模拟真实软件公司，包含CEO、CTO、程序员等多角色，通过功能研讨会（设计、编码、测试、文档）完成具体开发任务。选用了两个任务：BMI Calculator（简单）和 ArtCanvas（较复杂）。
- **Benchmark**：使用加权挣值（Weighted Earned Value, WEV）作为公平分配的基准指标，该指标基于COCOMO II等标准，综合代码、决策、文档、修复等四类贡献。
- **对比方法**：
  - **LLM-only**：无协商，自私行动；
  - **LLM+NEG**：允许简单协商，但无Shapley推理；
  - **LLM+STS**：仅使用短期Shapley思维链；
  - **LLM+SC**：完整Shapley-Coop工作流。

## 4. 资源与算力

- 论文在附录中说明：所有模块在小型服务器（24核CPU、32GB DRAM）上运行，仅涉及API调用，**未使用GPU资源**。未提供具体训练时长或推理时间数据。

## 5. 实验数量与充分性

- **实验数量**：
  - Escape Room：提供了个体收益图（图3a）和协商轮次/差异图（图3b），每个条件重复次数未明确说明。
  - Raid Battle：三个难度等级各进行了实验，报告了贡献分数（图4）和奖励分配百分比（图5），以及多轮协商的收敛分析（附录表7）。每个等级可能有多轮独立运行。
  - ChatDEV：两个任务（BMI Calculator、ArtCanvas），报告了各角色的WEV、分配奖励和调整幅度（表3）。
  - 补充实验：与Banzhaf值对比（附录表9-11），验证Shapley值的优越性。
- **充分性评价**：实验设计较为充分，覆盖了从简单社会困境到复杂多步游戏再到真实模拟场景，对比了不同变体。但未报告多次运行的统计误差棒，个别结果仅有单次示例（如ChatDEV表格），可能影响统计可靠性。此外，未与基于强化学习的多智能体方法（如LIO、LOPT）进行直接比较（作者在附录E中解释了范式差异）。

## 6. 主要结论与发现

- Shapley-Coop能有效解决社会困境，实现自发合作：Escape Room中成功率从0%（LLM-only）提升至100%（LLM+SC），且个体收益接近最优（4.5）。
- 短期Shapley思维链实现了公平且高效的奖励分配：相比仅使用短期推理（LLM+STS），完整工作流（LLM+SC）显著减少了分配偏差，使奖励更接近理论期望。
- 在Raid Battle中，LLM+SC促进了角色平衡（如承担嘲讽/治疗责任），而LLM+NEG则偏向高个体奖励行为，导致团队效率低下。贡献得分平均提升56%-222%。
- 在ChatDEV中，基于WEV的奖励分配与人类预设分配差距很小（多数角色低于6%），验证了方法的实际适用性。

## 7. 优点

- **问题定位精准**：明确将多智能体协作困难归因于“信用分配”和“激励对齐”，并借鉴经济学理论提出基于定价的解决方案。
- **方法创新**：将Shapley值的公理化公平性与LLM的推理能力结合，设计出“短期定性推理+长期定量计算”的双阶段思维链，兼顾实时性和精确性。
- **实验覆盖全面**：从简单社会困境（Escape Room）到复杂多步博弈（Raid Battle）再到真实世界模拟（ChatDEV），场景多样，验证了方法的泛化能力。
- **模块化设计**：三个核心模块（协商协议、短期CoT、长期CoT）可独立替换或增强，具有良好扩展性。
- **与现有方法对比客观**：设置了多个消融变体（LLM-only、LLM+NEG、LLM+STS），清晰展示了每个组件的贡献。
- **理论分析扎实**：提供Shapley值的数学定义、与现实世界类比（雇佣合同），以及附录中与Banzhaf值等替代方法的比较，论证了选择Shapley值的合理性。

## 8. 不足与局限

- **实验统计性不足**：未提供多次运行的误差棒或置信区间，无法判断结果的稳定性。例如ChatDEV表格仅展示单次运行结果，可能存在偶然性。
- **与强化学习方法比较缺失**：尽管作者在附录E解释了范式差异（MARL需要大量训练而本文是零样本），但未在类似场景（如Escape Room）进行直接性能对比，读者难以评估相对优劣。
- **计算成本未量化**：虽然声称仅需API调用，但协商过程会产生大量token消耗（沟通开销），文中仅定性提及，未提供具体成本数据。
- **动态定价能力有限**：作者在结论中指出当前无法在协作过程中动态调整定价，这是一个明确局限性。未来需要开发自适应、实时的激励机制。
- **可扩展性**：Shapley值计算在代理数量较大时呈指数级增长，当前近似方法可能牺牲效率属性（文中已承认），但未讨论对10+代理规模的适用性。
- **应用场景限制**：实验环境均为游戏或软件工程，未涉及更开放的真实世界任务（如机器人协作、医疗决策），泛化性尚需验证。
- **可能的偏差风险**：LLM的固有偏差（如过度承诺、谈判策略差异）未被系统控制；假设代理诚实遵循Shapley推理，但可能被恶意操纵。

（完）
