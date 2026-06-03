---
title: "Chain of Agents: Large Language Models Collaborating on Long-Context Tasks"
title_zh: 智能体链：大型语言模型协作处理长上下文任务
authors: "Yusen Zhang, Ruoxi Sun, Yanfei Chen, Tomas Pfister, Rui Zhang, Sercan O Arik"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=LuCLf4BJsr"
tags: ["query:mas-routing"]
score: 8.0
evidence: 多智能体协作框架，类似于子任务路由
tldr: 针对长上下文任务，现有方法信息覆盖不全或窗口扩展困难。本文提出Chain-of-Agents（CoA）框架，通过自然语言驱动多智能体协作，将长上下文拆解为子任务并路由给不同智能体，实现信息聚合与推理。实验证明该方法优于RAG和长窗口基线，为多智能体路由提供新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 714, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 719, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 983, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 725, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-luclf4bjsr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 447, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 811, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1466, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1227, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1531, \"height\": 873, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1534, \"height\": 743, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1556, \"height\": 950, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1553, \"height\": 1184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1556, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1445, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 774, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1381, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-luclf4bjsr/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1446, \"height\": 461, \"label\": \"Table\"}]"
motivation: 现有长上下文处理方法存在信息丢失或焦点分散问题，需要更有效的智能体协作机制。
method: 提出Chain-of-Agents框架，利用多智能体通过自然语言协作，将请求路由至不同智能体分别处理子任务。
result: 实验表明CoA在长上下文任务上显著优于RAG和长窗口LLM，验证了多智能体路由的有效性。
conclusion: 多智能体协同路由能有效解决长上下文难题，为LLM系统任务分配提供思路。
---

## Abstract
Addressing the challenge of effectively processing long contexts has become a critical issue for Large Language Models (LLMs). Two common strategies have emerged: 1) reducing the input length, such as retrieving relevant chunks by Retrieval-Augmented Generation (RAG), and 2) expanding the context window limit of LLMs. However, both strategies have drawbacks: input reduction has no guarantee of covering the part with needed information, while window extension struggles with focusing on the pertinent information for solving the task. To mitigate these limitations, we propose Chain-of-Agents (CoA), a novel framework that harnesses multi-agent collaboration through natural language to enable information aggregation and context reasoning across various LLMs over long-context tasks. CoA consists of multiple worker agents who sequentially communicate to handle different segmented portions of the text, followed by a manager agent who synthesizes these contributions into a coherent final output. CoA processes the entire input by interleaving reading and reasoning, and it mitigates long context focus issues by assigning each agent a short context. We perform a comprehensive evaluation of CoA on a wide range of long-context tasks in question answering, summarization, and code completion, demonstrating significant improvements by up to 10% over strong baselines of RAG, Full-Context, and multi-agent LLMs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

大规模语言模型（LLMs）在处理长上下文任务时面临重大挑战。现有的两种主流策略各有缺陷：
- **输入缩减**：如检索增强生成（RAG），通过检索相关片段减少输入长度，但检索精度不足时可能丢失关键信息。
- **窗口扩展**：通过微调扩大上下文窗口（如Claude-3支持200k tokens），但模型在长窗口中难以聚焦于任务所需信息，出现“中间丢失”（lost-in-the-middle）问题。

论文提出一种无需训练、任务无关、高度可解释的多智能体协作框架——**Chain-of-Agents (CoA)**，旨在通过智能体间的自然语言通信，集成信息聚合与上下文推理能力，从而有效处理长上下文任务。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

**核心思想**：模拟人类在有限工作记忆下边读边处理长文本的方式，将长文本分段分配给多个工作智能体（Worker Agents），它们按顺序通信并传递证据，最后管理器（Manager Agent）整合信息生成最终输出。

**关键技术细节**：
- **分块策略**：将长输入 \(x\) 分割成 \(l\) 个块 \(\{c_1, c_2, \dots, c_l\}\)，每块长度小于智能体窗口限制 \(k\)。
- **第一阶段（工作智能体链式通信）**：
  - 工作智能体 \(W_i\) 接收当前块 \(c_i\)、查询 \(q\)、指令 \(I_W\) 以及前一个智能体传递的通信单元 \(CU_{i-1}\)，生成新的通信单元 \(CU_i\)。
  - 公式：\(CU_i = LLM_{W_i}(I_W, CU_{i-1}, c_i, q)\)。
  - 通信单元内容随任务变化：问答任务中包含证据；摘要任务中包含前文摘要；代码补全中包含函数名和解释。
- **第二阶段（管理器信息整合与回答生成）**：
  - 管理器 \(M\) 接收最后一个工作智能体输出的 \(CU_l\)，结合指令 \(I_M\) 和查询 \(q\) 生成最终回答。
  - 公式：\(\text{Response} = LLM_M(I_M, CU_l, q)\)。
- **时间复杂度**：CoA 编码阶段为 \(O(nk)\)（\(n\) 为输入长度，\(k\) 为窗口限制），解码阶段为 \(O(nr)\)，优于 Full-Context 的 \(O(n^2)\) 编码复杂度，与 RAG 相当。

## 3. 实验设计：使用了哪些数据集 / 场景、benchmark、对比方法

### 数据集（共9个）
- **问答（QA）**：HotpotQA、MuSiQue、NarrativeQA、Qasper、QuALITY（均来自 LongBench/SCROLLS）。
- **摘要**：QMSum（查询式摘要）、GovReport（通用摘要）、BookSum（长文本摘要）。
- **代码补全**：RepoBench-P（仓库级代码补全）。

### Benchmark 指标
- 摘要任务：ROUGE 几何平均。
- 代码补全：代码相似度分数。
- QuALITY：精确匹配。
- 其他问答任务：F1 分数。

### 对比方法
- **Vanilla**：直接输入文本至上下文窗口上限（truncation）。
- **RAG**：使用最新检索器（[79]）分块检索，取 top-n 块输入 LLM。
- **其他多智能体基线**：
  - **Merge**：各工作智能体独立生成答案，多数投票决定最终输出。
  - **Hierarchical**：工作智能体分别判断是否有用信息并生成通信单元，汇总至管理器。
- **长上下文 LLM**：Claude-3（Haiku、Sonnet、Opus）支持 200k tokens 的 Vanilla 基线。

### 使用的 LLM 骨干模型
- PaLM 2（text-bison@001, text-unicorn@001，窗口 8k）
- Gemini 1.0（gemini-ultra，窗口 32k）
- Claude 3（Haiku、Sonnet、Opus，窗口 200k）

## 4. 资源与算力

论文未明确说明训练所用的 GPU 型号、数量或训练时长。因为 CoA 是**训练-免费（training-free）**框架，仅涉及 LLM 的推理调用。实验通过 Vertex Model Garden API 调用上述六种 LLM，无需额外 GPU 资源用于训练。RAG 的检索器使用 Huggingface 模型在 A100 GPU 上运行，但未给出具体卡时。

## 5. 实验数量与充分性

论文进行了大量实验，涵盖：
- **9个数据集**上的主实验（Table 4, Table 5）。
- **3种 LLM 家族、共6个模型**（PaLM 2, Gemini, Claude 3）。
- **对比两种主流基线**（Vanilla, RAG）及两种多智能体基线（Merge, Hierarchical）。
- **消融实验**：
  - 管理器的有效性（w/o Manager）。
  - 不同阅读顺序（左向右、右向左、随机顺序）。
  - 多路径增强（双向、自洽、随机排列，分别采用投票或 LLM 作为裁判）。
- **分析实验**：
  - RAG 检索失败时 CoA 的提升（Figure 3）。
  - 输入长度与性能关系（Figure 2）。
  - “中间丢失”问题缓解（Figure 4）。
  - 实际时间消耗（Table 9）。
  - 信息损失度量（Table 10）。
  - 窗口大小鲁棒性（Figure 6）。
  - NIAH PLUS 测试（Figure 7）。

实验设计全面、客观，控制变量（温度 0，种子固定），结果可重复。消融和对比充分证明了各组件贡献。

## 6. 论文的主要结论与发现

1. **CoA 显著优于所有基线**：在9个数据集上，CoA 相比于 Vanilla 和 RAG 提升高达10%，尤其在使用短窗口模型（8k）时甚至优于长窗口模型（200k）的 Vanilla。
2. **CoA 受益于更强的模型**：当使用 Claude-3 Opus 时，提升幅度更大。
3. **CoA 缓解“中间丢失”问题**：相比于 Full-Context，CoA 的输出性能波动更小（4.89 vs 6.13）。
4. **CoA 在长输入上提升更明显**：输入长度超过400k时，提升接近100%。
5. **链式通信优于并行结构**：CoA（顺序链）远优于 Merge 和 Hierarchical（并行无通信）的多智能体方法。
6. **多路径集成可进一步提升性能**：5 路径随机排列 + 投票或裁判方法可达更高性能，但简单投票在自洽场景中更好。

## 7. 优点：方法或实验设计上的亮点

- **无需训练**：可直接应用于现有 LLM，无需微调，成本低。
- **任务无关**：在 QA、摘要、代码补全三类任务上均有效。
- **高度可解释**：每个工作智能体的通信单元可被检查，便于分析推理过程。
- **应对极端长上下文**：通过增加智能体数量可处理任意长度输入，不受窗口限制。
- **缓解长上下文焦点问题**：每个智能体只处理短块，避免“中间丢失”。
- **实验设计严谨**：覆盖多模型、多任务、多基线，并进行了充分的消融、对抗分析、鲁棒性测试。

## 8. 不足与局限

1. **通信有效性可提升**：当前 LLM 的对齐方式并非最优于智能体间通信，未来可通过微调或上下文学习改进。
2. **通信形式单一**：仅采用顺序单向通信，未探索辩论、复杂讨论等更丰富的交互模式。
3. **成本与延迟**：CoA 需要多次 LLM 调用，比 Vanilla 慢（但可通过并行编码降低），实际应用中需权衡。
4. **信息损失**：链式传播中约有1%-4%的信息损失（Table 10），可能影响最终精度。
5. **依赖人工提示设计**：对不同的 LLM 可能需要精心设计提示语才能达到最优效果。
6. **实验覆盖局限**：未测试超长文档（如百万级 tokens）的极端场景；部分数据集（如 Qasper）的性能未超越领域微调模型。

（完）
