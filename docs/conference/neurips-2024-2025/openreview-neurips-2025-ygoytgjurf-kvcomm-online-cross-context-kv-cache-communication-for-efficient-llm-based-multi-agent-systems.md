---
title: "KVCOMM: Online Cross-context KV-cache Communication for Efficient LLM-based Multi-agent Systems"
title_zh: KVCOMM：面向高效LLM多智能体系统的在线跨上下文KV缓存通信
authors: "Hancheng Ye, Zhengqi Gao, Mingyuan Ma, Qinsi Wang, Yuzhe Fu, Ming-Yu Chung, Yueqian Lin, Zhijian Liu, Jianyi Zhang, Danyang Zhuo, Yiran Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yGOytgjurF"
tags: ["query:mas-routing"]
score: 7.0
evidence: 优化多智能体系统中KV缓存通信以提升效率
tldr: 多智能体LLM系统因重复处理重叠上下文而效率低下。本文提出KVCOMM，实现跨上下文的KV缓存在线通信，避免重复计算。实验表明KVCOMM显著降低推理时间和计算成本，为多智能体系统的高效路由与通信提供关键技术支撑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1233, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1408, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1394, \"height\": 1805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1430, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 1803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 1799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 1820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1440, \"height\": 1825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1442, \"height\": 1820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1441, \"height\": 1823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1443, \"height\": 1830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1442, \"height\": 1827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ygoytgjurf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1416, \"height\": 945, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 952, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 721, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 659, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 122, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 802, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 803, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1258, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 804, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1050, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ygoytgjurf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1450, \"height\": 431, \"label\": \"Table\"}]"
motivation: 多智能体系统中上下文重叠导致大量重复计算，影响效率。
method: 提出KVCOMM，通过在线共享KV缓存，避免每个智能体重复处理相同前缀上下文。
result: 在多种多智能体任务中，KVCOMM大幅减少延迟和计算开销，且不损失性能。
conclusion: 高效的缓存通信机制是构建可扩展多智能体系统的关键。
---

## Abstract
Multi-agent large language model (LLM) systems are increasingly adopted for complex language processing tasks that require communication and coordination among agents. However, these systems often suffer substantial overhead from repeated reprocessing of overlapping contexts across agents. In typical pipelines, once an agent receives a message from its predecessor, the full context-including prior turns-must be reprocessed from scratch, leading to inefficient processing. While key-value (KV) caching is an effective solution for avoiding redundant computation in single-agent settings where prefixes remain unchanged, it cannot be directly reused in multi-agent scenarios due to diverging prefixes introduced by agent-specific context extensions. We identify that the core challenge lies in the offset variance of KV-caches across agents. To address this, we propose **KVCOMM**, a training-free framework that enables efficient prefilling in multi-agent inference by reusing KV-caches and aligning cache offsets of overlapping contexts under diverse prefix contexts. KVCOMM estimates and adjusts KV-caches for shared content by referencing a pool of cached examples—termed *anchors*—that store observed cache deviations under varying prefixes. The anchor pool is maintained and updated online, allowing dynamic adaptation to distinct user requests and context structures. KVCOMM achieves over 70% reuse rate across diverse multi- agent workloads, including retrieval-augmented generation, math reasoning, and collaborative coding tasks, all without quality degradation. Particularly, when each fully-connected agent receives 1K input tokens with 512 prefix tokens and 512 output tokens under a five-agent setting, KVCOMM achieves up to 7.8× speedup compared to the standard prefill pipeline, reducing TTFT from ∼430ms to ∼55ms. Code is available at https://github.com/FastMAS/KVCOMM.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多智能体大语言模型（LLM）系统中，每个智能体在接收到上游消息后，必须重新处理包含先前轮次在内的完整上下文，导致大量重复的预填充（prefill）计算，显著增加推理延迟和计算开销。
- **核心问题**：传统KV缓存（KV-cache）在单智能体场景中可有效避免前缀不变的冗余计算，但在多智能体场景中，由于每个智能体扩展了不同的前缀上下文，导致共享文本的KV缓存因前缀不同而产生偏移（offset variance），无法直接重用。
- **整体含义**：需要一种无需训练、能动态适应不同前缀上下文的KV缓存共享机制，以提升多智能体系统的推理效率，同时保持任务性能。

## 2. 方法论：核心思想、关键技术、算法流程

- **核心思想**：将KV缓存重用视为一个“近似平移”问题——对于共享文本，通过参考之前观察到的类似样本（称为“锚点”）来估计其在新前缀下的KV偏移，从而避免重新计算。
- **关键技术**：
  - **Anchor池（Anchor Pool）**：在线维护一组锚点样本，每个锚点存储其基座KV缓存、在不同智能体上下文中的KV偏移量（包括占位符偏移和前缀偏移）。
  - **锚点匹配（Anchor Matching）**：对新到来的占位符，根据嵌入相似度和序列长度兼容性，从锚点池中选出最匹配的锚点。
  - **偏移近似（Offset Approximation）**：通过软权重（基于ℓ2范数或余弦相似度）插值多个锚点的偏移，得到当前上下文的预测偏移，然后将其加回到基座KV缓存上。
  - **位置对齐（Positional Alignment）**：由于RoPE旋转位置编码，Key缓存必须先进行反旋转/再旋转对齐，才能比较和偏移。
  - **锚点更新**：当无法找到可重用锚点时，将当前样本作为新锚点加入池中，并定期剪枝低频锚点以节省内存。
- **算法流程**（文字描述）：
  1. 初始化：所有智能体预计算并存储提示模板中固定前缀的KV缓存。
  2. 请求到达：检查各占位符的基座KV缓存是否可用，若缺失则并行计算。
  3. 可重用性判断：若占位符满足锚点预测条件（长度覆盖且嵌入熵低于阈值），则执行重用；否则执行完整预填充，并将计算出的偏移存入锚点池。
  4. 偏移近似：取出匹配的锚点，利用嵌入距离计算权重，插值得到占位符和相邻前缀的KV偏移，并更新缓存。
  5. 解码：拼接更新后的KV缓存，直接进入自回归解码，跳过预填充。
  6. 锚点更新：生成的响应KV缓存若可重用则存入共享内存，否则作为新锚点加入池中。

## 3. 实验设计

- **数据集/场景**：
  - 检索增强生成（RAG）：MMLU
  - 数学推理：GSM8K、MATH500、AIME（附加实验）
  - 协作编程：HumanEval
- **基准（Benchmark）与对比方法**：
  - 原始无缓存重用（Original）
  - 选择性重计算方法 CacheBlend（固定重算 top-20% 令牌）
- **评估指标**：
  - 准确率（Accuracy）、Pass@1
  - 重用率（Reuse Rate）
  - 首令牌延迟（TTFT）及加速比

## 4. 资源与算力

- 文中明确提到：所有实验在**单个 NVIDIA H100 GPU** 上执行。
- 未提及训练时长（方法无需训练），也未给出完整实验总耗时或锚点维护的具体GPU开销。

## 5. 实验数量与充分性

- **主要实验组数**：覆盖3个数据集、2～5个智能体的多种配置，总计约24组主要结果（表1、表2、表3）；附加实验包括MATH500、AIME（表A.2），以及消融实验、超参数分析、鲁棒性测试等（表4～表6、表A.3～表A.5），共计约10余组额外实验。
- **充分性评价**：实验较为充分，覆盖了多种任务类型、不同智能体数量、不同上下文长度，并包含消融研究（位置对齐、锚点匹配标准、近似方法）和超参数敏感性分析。但缺少与更多最新基线（如KVLink、DroidSpeak）的对比，且仅在开源模型上验证（Llama-3.1-8B、Qwen-Coder-2.5-7B、Deepseek-Qwen-7B），未在更大模型或商业模型上测试，存在一定局限性。

## 6. 主要结论与发现

- KVCOMM可在无质量损失的情况下实现平均 **~6.7× 预填充加速**（三智能体、Llama-3.1-8B），最长设置下加速比可达7.82×。
- 重用率稳定在 **70%～87.6%**，显著高于基线方法。
- 在数学推理（GSM8K）和编程（HumanEval）任务上，KVCOMM的准确率/Pass@1与原始无重用流程接近（差距<2.5%），而CacheBlend在复杂任务上出现严重退化。
- 所有对齐步骤（位置旋转、占位符偏移、前缀偏移）均不可或缺；锚点匹配中嵌入距离与长度兼容性的结合至关重要。

## 7. 优点

- **无需训练**：不改变模型参数或增加训练成本，可直接作为插件框架使用。
- **自适应性强**：通过在线锚点池动态适应不同请求和上下文结构，不受固定策略限制。
- **理论支撑**：提供了形式化的命题证明（KV距离与偏移近似错误的上界），为方法有效性提供数学基础。
- **实用性强**：在多种多智能体任务上均获得显著加速，且代码已开源。

## 8. 不足与局限

- **实验覆盖范围有限**：仅在文本输入的多智能体系统上评估，未涉及图像、音频等多模态场景。
- **仅支持同构模型**：要求所有智能体使用同一模型架构（RoPE-based decoder），异构模型（不同注意力机制、不同权重）尚待探索。
- **解码阶段未加速**：方法仅加速预填充阶段，自回归解码延迟仍是瓶颈。
- **内存开销较大**：存储锚点偏移会占用额外显存，文中虽提出剪枝策略，但在长上下文、多锚点场景下可能成为负担（附录中报告了4K上下文时内存达95GB）。
- **锚点匹配与数据搬移开销**：长上下文锚点匹配中softmax延迟及KV缓存从CPU搬移到GPU的耗时（可达1.3秒），在极端场景下可能削弱加速收益。

（完）
