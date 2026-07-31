# 图解 120 个大语言模型 (LLM) 核心概念

> 每张图片对应一个 LLM 核心概念的知识卡片，包含标题、定义、核心内容和页码。

> 图片格式：竖版构图（1024×1536），白色背景，靛蓝色/科技蓝强调色系统，简洁线性图标 + 圆角卡片风格。

---

## 1. LLM (Large Language Model)

![](./images/llm1.png)

**主要内容：** 指在海量文本数据上训练出的 AI 系统，能够理解并生成类似人类的语言，胜任对话、写作、推理等任务。LLM 通过对海量文本的学习，捕捉语言规律与世界知识，从而在遇到新问题时进行理解、推理并生成高质量的文本输出。

---

## 2. Transformer

![](./images/llm2.png)

**主要内容：** 一种专为处理序列数据设计的神经网络架构，依靠 Self-Attention（自注意力）机制捕捉输入元素之间的依赖关系，且不受它们在序列中距离远近的影响。Transformer 是当前 LLM 的核心架构，凭借并行计算与长程依赖建模能力，成为自然语言处理的基础。

---

## 3. GPT (Generative Pre-trained Transformer)

![](./images/llm3.png)

**主要内容：** 一种基于 Transformer 架构的自回归语言模型，通过预测序列中的下一个词来生成类似人类的文本，先在海量文本上预训练，再针对具体任务微调。GPT 是现代大语言模型（如 GPT-4、ChatGPT 等）的基础架构范式。

---

## 4. BERT (Bidirectional Encoder Representations from Transformers)

![](./images/llm4.png)

**主要内容：** 一种仅使用 Encoder 的 Transformer 语言模型，通过 Masked Language Modelling（掩码语言建模）在每一层同时利用左右两侧的上下文，学习深层语境表示。广泛应用于文本分类、情感分析、命名实体识别、问答等理解类任务。

---

## 5. LLaMA (Large Language Model Meta AI)

![](./images/llm5.png)

**主要内容：** Meta 推出的一系列开放权重（open-weight）基础语言模型家族，覆盖不同规模、兼顾效率与性能，方便研究者和开发者以更低的资源研究和部署先进语言模型。

---

## 6. LRM (Large Reasoning Model)

![](./images/llm6.png)

**主要内容：** 一种强化推理能力的大模型，在回答问题前会进行多步推理、自我反思与验证，擅长数学、编程、科学等需要深度思考的任务。代表模型包括 OpenAI o1、DeepSeek-R1 等。

---

## 7. Multimodal LLMs

![](./images/llm7.png)

**主要内容：** 能够跨越文本、图像、音频、视频等多种数据类型进行理解与生成的大语言模型，让人机交互超越纯文字层面。通过统一的表示空间与强大的推理能力，实现跨模态理解与生成。

---

## 8. Context Window

![](./images/llm8.png)

**主要内容：** LLM 在单次对话或单条 Prompt 中，能够处理和记住的最大 Token（词、字符或符号）数量。决定了模型在一次交互中能"看到"的信息量上限，超出该上限的内容将无法被模型直接处理或记忆。

---

## 9. Common Crawl

![](./images/llm9.png)

**主要内容：** 一家非营利组织，维护着一个开放的网页爬取数据仓库，涵盖公开互联网上数以十亿计的网页，体量高达数拍字节（PB 级），被广泛用于训练和评测大语言模型及其他机器学习系统。

---

## 10. Embeddings

![](./images/llm10.png)

**主要内容：** 将 Token、单词或句子映射为稠密向量（Dense Vector）的表示方式，能够在连续向量空间中捕捉其语义与相互关系。Embeddings 是语言模型的"基石"，将离散内容转化为几何空间中的点。

---

## 11. BPE (Byte-Pair Encoding)

![](./images/llm11.png)

**主要内容：** 一种分词（Tokenization）技术，通过不断合并出现频率最高的字符或词对，逐步构建出一套子词（Subword）词表。OpenAI 的 Tiktoken 库实现了高速 BPE 版本，已被 GPT、LLaMA、Claude 等众多模型采用。

---

## 12. Positional Encoding

![](./images/llm12.png)

**主要内容：** Transformer 中用来向模型注入 Token 顺序信息的技术，使模型在本身不具备循环结构的情况下，依然能够捕捉序列的顺序结构。常见方式包括正弦/余弦编码和可学习编码。

---

## 13. RoPE (Rotary Position Embeddings)

![](./images/llm13.png)

**主要内容：** 一种旋转位置编码方法，通过对 Query 和 Key 向量施加旋转操作来编码相对位置信息，使 Transformer 能够更好地捕捉 Token 之间的相对位置关系。广泛应用于 LLaMA 等现代 LLM。

---

## 14. Self-Attention (Scaled Dot-Product Attention)

![](./images/llm14.png)

**主要内容：** 让 LLM 对序列中所有 Token（包括自身）的信息进行加权聚合，为每个 Token 计算出新表示，从而捕捉上下文、依赖关系与相互联系的核心机制。是 Transformer 编码器与解码器的核心。

---

## 15. MHA (Multi-Head Attention)

![](./images/llm15.png)

**主要内容：** Transformer 中的一种机制，通过并行运行多个 Attention 计算（即多个"头"），让模型能够同时关注不同表示子空间的信息，再将各头输出拼接组合，捕获多样化的语义信息。

---

## 16. Causal Masking

![](./images/llm16.png)

**主要内容：** 在自回归生成中，通过掩码矩阵确保每个 Token 只能关注它自身及之前的 Token，防止"看到未来信息"。这是 GPT 等 Decoder-only 模型实现从左到右逐词生成的关键机制。

---

## 17. Flash Attention

![](./images/llm17.png)

**主要内容：** 一种高效的 Attention 计算算法，通过分块（Tiling）和 GPU 显存优化，大幅减少 Attention 计算的内存占用和 IO 开销，使长序列训练和推理更加高效。已在 PyTorch 中原生支持。

---

## 18. GQA (Group Query Attention)

![](./images/llm18.png)

**主要内容：** 一种介于 Multi-Head Attention 和 Multi-Query Attention 之间的注意力机制，将 Query Head 分组，每组共享一组 Key/Value 头，在保持模型质量的同时减少 KV Cache 开销。LLaMA 2/3 等模型采用。

---

## 19. MQA (Multi-Query Attention)

![](./images/llm19.png)

**主要内容：** Multi-Head Attention 的一种极端变体（如 Google PaLM），所有 Query Head 共享同一组 Key-Value 头，极大减少 KV Cache 内存占用，提升推理速度，但可能略微影响模型质量。

---

## 20. MLA (Multi-head Latent Attention)

![](./images/llm20.png)

**主要内容：** 一种改进的注意力机制（如 DeepSeek 采用），将 Key 和 Value 压缩到低维潜在空间（Latent Space），在保持表达能力的同时大幅减少 KV Cache 开销，是 LLM 高效推理的重要方向。

---

## 21. LLM Inference

![](./images/llm21.png)

**主要内容：** LLM 根据输入 Prompt 逐 Token 生成输出的过程。推理阶段模型以自回归方式工作，每生成一个 Token 都需要基于之前所有 Token 进行计算，是 LLM 应用的核心环节。

---

## 22. Autoregression (Next-Token Prediction)

![](./images/llm22.png)

**主要内容：** LLM 的核心生成方式：基于已生成的 Token 序列，逐步预测下一个最可能的 Token。每次预测的结果会追加到序列中，用于下一轮预测，直到生成结束标记。

---

## 23. MLM (Masked Language Modeling)

![](./images/llm23.png)

**主要内容：** 一种预训练任务：随机遮盖输入中的部分 Token，让模型基于双向上下文预测被遮盖的 Token。这是 BERT 等 Encoder 模型的核心训练方式，能够学习深层双向语义表示。

---

## 24. KV Caching (Key-Value Caching)

![](./images/llm24.png)

**主要内容：** LLM 推理优化技术：在自回归生成过程中，缓存已计算过的 Key 和 Value 矩阵，避免重复计算，从而大幅加速推理速度。是 Transformer 解码器高效推理的关键技术。

---

## 25. Softmax

![](./images/llm25.png)

**主要内容：** 将 Logits（原始分数）转换为概率分布的函数，在 LLM 中用于将最后一层的输出转化为每个 Token 的预测概率。所有输出值在 (0,1) 之间且和为 1，是分类和生成的基础组件。

---

## 26. Greedy Decoding

![](./images/llm26.png)

**主要内容：** 最简单的解码策略：每一步都选择概率最高的 Token 作为输出。速度快但容易陷入重复和缺乏多样性，适用于对确定性要求高的场景。

---

## 27. Beam Search

![](./images/llm27.png)

**主要内容：** 一种搜索解码策略：在每一步保留 K 个最优的候选序列（Beam），最终选择整体概率最高的序列。相比 Greedy Decoding 能探索更多可能性，常用于机器翻译等任务。

---

## 28. Top-K Sampling

![](./images/llm28.png)

**主要内容：** 一种随机采样策略：只从概率最高的 K 个 Token 中随机选择下一个 Token，在保持输出质量的同时增加多样性。K 值通常取 10~50。

---

## 29. Top-P Sampling (Nucleus Sampling)

![](./images/llm29.png)

**主要内容：** 一种动态采样策略：从累积概率达到 P 的最小 Token 集合中随机采样，P 通常设为 0.7~0.95。相比 Top-K 更灵活，能根据上下文动态调整候选集大小。

---

## 30. Temperature

![](./images/llm30.png)

**主要内容：** 控制 LLM 输出随机性的参数。Temperature 越低（如 0.2），输出越确定和保守；Temperature 越高（如 1.2），输出越多样和创造性。常与 Top-P、Top-K 配合使用。

---

## 31. Test-Time Scaling (Inference-Time Scaling)

![](./images/llm31.png)

**主要内容：** 在推理阶段通过增加计算资源（如更多推理步骤、更长思考链）来提升模型表现的技术。是 LRM 等推理模型实现深度思考的关键方法。

---

## 32. Perplexity

![](./images/llm32.png)

**主要内容：** 衡量语言模型性能的核心指标，反映模型对测试数据的"困惑程度"。Perplexity 越低，表示模型对文本的预测越准确，语言建模能力越强。

---

## 33. BLEU (Bilingual Evaluation Understudy)

![](./images/llm33.png)

**主要内容：** 机器翻译质量自动评估指标，通过比较机器译文与参考译文之间的 n-gram 重叠度来评分。分数范围 0-100，越高表示翻译质量越好。

---

## 34. Pass@K Accuracy

![](./images/llm34.png)

**主要内容：** 代码生成任务的评估指标：对每个问题生成 K 个候选答案，只要其中任意一个通过测试用例即视为正确。常用于 HumanEval 等代码基准测试。

---

## 35. Win Rate

![](./images/llm35.png)

**主要内容：** 模型对比评估指标：在两个模型的输出之间进行人工或自动评判，统计一个模型"胜出"的比例。常用于 Chatbot Arena 等竞技场式评估。

---

## 36. LLM Hallucination

![](./images/llm36.png)

**主要内容：** LLM 生成看似合理但与事实不符、无据可依或逻辑矛盾的内容的现象。是 LLM 应用面临的核心挑战之一，可通过 RAG、事实核查等方法缓解。

---

## 37. NIAH Testing (Needle-in-a-Haystack Testing)

![](./images/llm37.png)

**主要内容：** 一种评估 LLM 长上下文检索能力的测试：在超长文本（"干草堆"）中隐藏特定信息（"针"），测试模型能否准确找到并利用该信息。

---

## 38. Prompt Engineering

![](./images/llm38.png)

**主要内容：** 设计和优化 Prompt 以引导 LLM 产生期望输出的技术。包括指令设计、示例选择、格式规范等，是发挥 LLM 能力的关键技能。

---

## 39. Zero-Shot Prompting

![](./images/llm39.png)

**主要内容：** 不提供任何示例，仅通过指令直接让 LLM 完成任务。简单直接，适用于 LLM 已有较好理解的常见任务。

---

## 40. Few-Shot Prompting

![](./images/llm40.png)

**主要内容：** 在 Prompt 中提供少量示例（通常 2-5 个），让 LLM 通过上下文学习（In-Context Learning）理解任务模式并完成新输入。

---

## 41. CoT Prompting (Chain-of-Thought Prompting)

![](./images/llm41.png)

**主要内容：** 引导 LLM 在给出最终答案前，先展示逐步推理过程的 Prompting 技术。通过"让我们一步步思考"的方式，显著提升复杂推理任务的准确率。

---

## 42. Zero-Shot CoT (Zero-Shot Chain-of-Thought)

![](./images/llm42.png)

**主要内容：** 不提供推理示例，仅通过在 Prompt 中加入"Let's think step by step"等引导语，激发 LLM 的逐步推理能力。简单有效，适用于各类推理任务。

---

## 43. CoD Prompting (Chain-of-Draft Prompting)

![](./images/llm43.png)

**主要内容：** 一种精简的推理 Prompting 技术：LLM 以极简的"草稿"形式输出推理步骤，每个步骤仅用最少 Token 表达关键信息，在保持推理质量的同时大幅降低输出长度和延迟。

---

## 44. Tree of Thoughts

![](./images/llm44.png)

**主要内容：** 一种高级 Prompting 框架：LLM 同时探索多条推理路径（"思维树"），对每条路径进行评估和剪枝，最终选择最优路径。适用于需要规划和搜索的复杂问题。

---

## 45. ReAct (Reasoning and Acting)

![](./images/llm45.png)

**主要内容：** 将推理（Reasoning）与行动（Acting）交替进行的 Prompting 框架。LLM 在思考过程中可以调用外部工具获取信息，再基于新信息继续推理，形成"思考-行动-观察"循环。

---

## 46. Self-Consistency

![](./images/llm46.png)

**主要内容：** 一种提升推理准确率的技术：让 LLM 多次独立生成推理路径和答案，然后通过多数投票选择最一致的答案。用"采样多样性"换取"答案可靠性"。

---

## 47. Self-Verification

![](./images/llm47.png)

**主要内容：** 让 LLM 对自己的输出进行检查和验证的技术。模型先生成答案，再以"检查者"视角审视答案的正确性、完整性和逻辑一致性，发现并修正错误。

---

## 48. Vector Database

![](./images/llm48.png)

**主要内容：** 专门存储和检索高维向量数据的数据库系统。在 LLM 应用中用于存储 Embeddings，支持语义相似度搜索，是 RAG 系统的核心组件。

---

## 49. RAG (Retrieval-Augmented Generation)

![](./images/llm49.png)

**主要内容：** 一种技术：LLM 在生成回答前先检索相关的外部文档来增强自身上下文，从而提升回答的准确性与事实依据。将"检索"与"生成"结合，有效减少幻觉。

---

## 50. AI Agents

![](./images/llm50.png)

**主要内容：** 由语言模型驱动的自主系统，具备推理、规划、调用工具、与环境交互、访问记忆并通过反馈不断优化自身行为的能力，以完成用户设定的目标。

---

## 51. MCP (Model Context Protocol)

![](./images/llm51.png)

**主要内容：** 一种标准化的模型上下文协议，定义了 LLM 与外部工具、数据源之间的交互规范。使不同 LLM 应用能够以统一方式接入工具和资源。

---

## 52. Function Calling

![](./images/llm52.png)

**主要内容：** LLM 根据用户意图自动选择和调用预定义函数/API 的能力。模型输出结构化的函数调用参数，由外部系统执行后将结果返回模型继续处理。

---

## 53. Tool Use

![](./images/llm53.png)

**主要内容：** LLM 使用外部工具（搜索引擎、计算器、代码执行器等）来增强自身能力的技术。使 LLM 能够完成超出纯文本生成范畴的任务。

---

## 54. CLIP (Contrastive Language-Image Pretraining)

![](./images/llm54.png)

**主要内容：** OpenAI 提出的多模态模型，通过对比学习将图像和文本映射到同一向量空间，实现跨模态理解和检索。是 DALL-E、Stable Diffusion 等图像生成模型的基础。

---

## 55. Diffusion Models

![](./images/llm55.png)

**主要内容：** 一类生成模型，通过逐步向数据添加噪声再学习逆向去噪来生成新样本。在图像、视频、音频生成领域取得突破性成果，代表模型包括 Stable Diffusion、DALL-E 等。

---

## 56. DiT (Diffusion Transformer)

![](./images/llm56.png)

**主要内容：** 将 Transformer 架构应用于扩散模型的技术，用 Transformer 替代传统的 U-Net 作为去噪网络。Sora 等视频生成模型即基于此架构。

---

## 57. LoRA (Low-Rank Adaptation)

![](./images/llm57.png)

**主要内容：** 一种参数高效微调（PEFT）技术，通过在预训练模型的权重矩阵旁添加低秩分解矩阵来实现微调，大幅减少可训练参数量和显存占用。

---

## 58. Loss Function

![](./images/llm58.png)

**主要内容：** 衡量模型预测与真实值之间差异的函数，是模型训练的优化目标。在 LLM 中常用交叉熵损失（Cross-Entropy Loss）来衡量 Token 预测的准确性。

---

## 59. Cross-Entropy Loss

![](./images/llm59.png)

**主要内容：** LLM 训练中最常用的损失函数，衡量预测概率分布与真实分布之间的差异。最小化交叉熵等价于最大化正确 Token 的预测概率。

---

## 60. Gradient Descent

![](./images/llm60.png)

**主要内容：** 通过计算损失函数对模型参数的梯度，沿梯度反方向更新参数以最小化损失的优化算法。是深度学习训练的核心方法。

---

## 61. Backpropagation

![](./images/llm61.png)

**主要内容：** 反向传播算法：通过链式法则从输出层向输入层逐层计算梯度，是训练神经网络的基石。使深层网络的端到端训练成为可能。

---

## 62. Adam Optimizer

![](./images/llm62.png)

**主要内容：** 一种自适应学习率优化算法，结合了 Momentum 和 RMSProp 的优点。是 LLM 训练中最常用的优化器，收敛速度快且对超参数不敏感。

---

## 63. ReLU (Rectified Linear Unit)

![](./images/llm63.png)

**主要内容：** 最常用的激活函数之一：f(x) = max(0, x)。计算简单、缓解梯度消失，但存在"神经元死亡"问题（负半轴梯度为零）。

---

## 64. Sigmoid Function

![](./images/llm64.png)

**主要内容：** S 形激活函数：f(x) = 1/(1+e^(-x))，输出范围 (0,1)。常用于二分类输出层，但在深层网络中容易导致梯度消失。

---

## 65. Tanh Function

![](./images/llm65.png)

**主要内容：** 双曲正切激活函数：f(x) = (e^x - e^(-x))/(e^x + e^(-x))，输出范围 (-1,1)。相比 Sigmoid 以零为中心，但仍存在梯度消失问题。

---

## 66. SiLU (Sigmoid Linear Unit)

![](./images/llm66.png)

**主要内容：** 也称为 Swish 激活函数：f(x) = x · σ(x)。在 LLM 中广泛使用（如 LLaMA 系列），相比 ReLU 更平滑，性能更优。

---

## 67. GELU (Gaussian Error Linear Unit)

![](./images/llm67.png)

**主要内容：** 基于高斯分布的激活函数，是 BERT、GPT 等早期 Transformer 模型的标准激活函数。相比 ReLU 更平滑，引入随机正则化效果。

---

## 68. Layer Normalization

![](./images/llm68.png)

**主要内容：** 对每个样本的特征维度进行归一化的技术，是 Transformer 架构的标准组件。稳定训练过程，加速收敛，减少对初始化和学习率的敏感性。

---

## 69. RMSNorm (Root Mean Square Normalization)

![](./images/llm69.png)

**主要内容：** Layer Normalization 的简化变体，仅使用均方根进行归一化，去除了均值中心化步骤。计算更高效，被 LLaMA 等现代 LLM 广泛采用。

---

## 70. Model Activations

![](./images/llm70.png)

**主要内容：** 神经网络中各层神经元的输出值。在 LLM 推理中，激活值的存储和计算是显存占用的主要来源之一。

---

## 71. Residual Connections

![](./images/llm71.png)

**主要内容：** 残差连接（跳跃连接）：将层的输入直接加到输出上，使梯度能够直接流过深层网络。是训练深层 Transformer 的关键技术，有效缓解梯度消失。

---

## 72. Dropout

![](./images/llm72.png)

**主要内容：** 一种正则化技术：训练时随机"丢弃"一部分神经元（将其输出置零），防止过拟合。在推理时关闭，所有神经元都参与计算。

---

## 73. Regularization

![](./images/llm73.png)

**主要内容：** 防止模型过拟合的技术总称，包括 L1/L2 正则化、Dropout、Weight Decay、数据增强等。目的是提升模型在未见数据上的泛化能力。

---

## 74. L1 Regularization

![](./images/llm74.png)

**主要内容：** 在损失函数中添加参数绝对值之和作为惩罚项，倾向于产生稀疏解（部分参数为零）。可用于特征选择和模型压缩。

---

## 75. L2 Regularization

![](./images/llm75.png)

**主要内容：** 在损失函数中添加参数平方和作为惩罚项（也称为 Weight Decay），倾向于让参数值变小但非零。是最常用的正则化方法之一。

---

## 76. Weight Decay

![](./images/llm76.png)

**主要内容：** 等同于 L2 正则化，通过在每次参数更新时按比例缩小权重来防止过拟合。在现代优化器中通常与 Adam 等算法解耦使用（AdamW）。

---

## 77. Layer Normalization

![](./images/llm77.png)

**主要内容：** 对每个样本的特征维度进行归一化的技术，是 Transformer 架构的标准组件。稳定训练过程，加速收敛。

---

## 78. Batch Normalization

![](./images/llm78.png)

**主要内容：** 对每个特征在 batch 维度上进行归一化。在 CNN 中广泛使用，但在 Transformer 中通常被 Layer Normalization 替代。

---

## 79. Group Normalization

![](./images/llm79.png)

**主要内容：** 将通道分组后在每组内进行归一化，是 Batch Normalization 和 Layer Normalization 的折中方案。在 batch size 较小时表现更好。

---

## 80. Mixture of Experts (MoE)

![](./images/llm80.png)

**主要内容：** 一种模型架构：将模型分为多个"专家"子网络，每个输入只激活部分专家。在增加模型容量的同时控制计算成本，被 Mixtral、DeepSeek-V2 等模型采用。

---

## 81. Pretraining

![](./images/llm81.png)

**主要内容：** 在海量无标注文本上训练 LLM 学习通用语言知识和规律的过程。预训练后的模型具备基础的语言理解和生成能力，是后续微调的基础。

---

## 82. Fine-tuning

![](./images/llm82.png)

**主要内容：** 在预训练模型基础上，使用特定任务或领域的数据进行进一步训练，使模型适应该任务。包括全量微调和参数高效微调（PEFT）两种方式。

---

## 83. Instruction Tuning

![](./images/llm83.png)

**主要内容：** 使用（指令，回答）对来微调 LLM，使模型学会遵循人类指令。是让基础模型转变为有用助手的关键步骤，ChatGPT 等产品即基于此技术。

---

## 84. RLHF (Reinforcement Learning from Human Feedback)

![](./images/llm84.png)

**主要内容：** 使用人类偏好反馈来优化 LLM 的技术：先训练奖励模型来模拟人类偏好，再用强化学习（如 PPO）优化 LLM 以最大化奖励。是 ChatGPT 等对齐技术的核心。

---

## 85. DPO (Direct Preference Optimization)

![](./images/llm85.png)

**主要内容：** 一种替代 RLHF 的对齐技术：直接从人类偏好数据中优化模型，无需显式训练奖励模型和强化学习。更简单、更稳定，效果与 RLHF 相当。

---

## 86. PPO (Proximal Policy Optimization)

![](./images/llm86.png)

**主要内容：** 一种强化学习算法，通过限制策略更新幅度来保证训练稳定性。在 RLHF 中用于基于奖励模型优化 LLM 的输出质量。

---

## 87. GRPO (Group Relative Policy Optimization)

![](./images/llm87.png)

**主要内容：** 一种改进的策略优化方法，通过对一组输出的相对比较来优化模型，无需显式的价值函数。在 DeepSeek-R1 等推理模型训练中使用。

---

## 88. Reward Model

![](./images/llm88.png)

**主要内容：** RLHF 中的关键组件：一个训练来预测人类对模型输出偏好分数的模型。为强化学习阶段提供奖励信号，引导 LLM 向人类偏好方向优化。

---

## 89. Alignment

![](./images/llm89.png)

**主要内容：** 使 LLM 的行为、价值观和输出与人类意图和期望保持一致的技术总称。包括 RLHF、DPO、Constitutional AI 等方法，目标是让 AI 更有用、诚实、无害。

---

## 90. GRPO (Group Relative Policy Optimization)

![](./images/llm90.png)

**主要内容：** 一种改进的策略优化方法，通过对一组输出的相对比较来优化模型，无需显式的价值函数。在 DeepSeek-R1 等推理模型训练中使用。

---

## 91. Knowledge Distillation

![](./images/llm91.png)

**主要内容：** 将大型"教师模型"的知识迁移到小型"学生模型"的技术。学生模型学习模仿教师模型的输出分布，在保持较好性能的同时大幅减小模型规模。

---

## 92. Model Merging

![](./images/llm92.png)

**主要内容：** 将多个微调后的模型权重合并为一个模型的技术，无需额外训练。可以结合不同模型的优势，如合并不同领域专长的模型。

---

## 93. LLM Quantization

![](./images/llm93.png)

**主要内容：** 将模型参数从高精度（如 FP16/FP32）压缩到低精度（如 INT8/INT4）的技术，大幅减少模型大小和推理显存需求，使 LLM 能在消费级硬件上运行。

---

## 94. GGUF / GPTQ

![](./images/llm94.png)

**主要内容：** 两种主流的 LLM 量化格式。GGUF（GGML Universal Format）主要用于 llama.cpp 生态的 CPU 推理；GPTQ 针对 GPU 推理优化。两者都支持 INT4/INT8 等精度级别。

---

## 95. Speculative Decoding

![](./images/llm95.png)

**主要内容：** 一种加速 LLM 推理的技术：使用小型"草稿模型"快速生成候选 Token，再由大模型并行验证。在不损失质量的前提下，可将推理速度提升 2-3 倍。

---

## 96. Mamba

![](./images/llm96.png)

**主要内容：** 一种基于状态空间模型（SSM）的序列建模架构，作为 Transformer 的替代方案。具有线性时间复杂度，在处理超长序列时效率更高。

---

## 97. State Space Models (SSM)

![](./images/llm97.png)

**主要内容：** 一类序列建模架构，通过状态空间方程来描述序列的动态演化。Mamba 等模型基于此架构，在长序列处理上具有线性复杂度的优势。

---

## 98. Linear Attention

![](./images/llm98.png)

**主要内容：** 将标准 Attention 的 O(n²) 复杂度降低到 O(n) 的技术。通过核函数近似或状态空间方法，使长序列处理更加高效。

---

## 99. Prompt Injection / Jailbreak

![](./images/llm99.png)

**主要内容：** 通过精心构造的 Prompt 绕过 LLM 安全限制的攻击技术。Prompt Injection 直接注入恶意指令，Jailbreak 通过角色扮演等方式诱导模型突破限制。是 LLM 安全的重要挑战。

---

## 100. Red Teaming

![](./images/llm100.png)

**主要内容：** 通过模拟攻击者行为来测试和发现 LLM 安全漏洞的系统性方法。由专业团队尝试各种方式诱导模型产生有害输出，以改进安全防护。

---

## 101. Constitutional AI

![](./images/llm101.png)

**主要内容：** Anthropic 提出的 AI 对齐方法：让模型基于一套"宪法"原则（如无害、诚实、有益）来自我监督和改进，减少对人类反馈的依赖。

---

## 102. Safety Guardrails

![](./images/llm102.png)

**主要内容：** 部署在 LLM 周围的防护机制，包括输入过滤、输出审核、内容分类器等。用于防止模型产生有害、不当或违规内容。

---

## 103. Evaluation Benchmark

![](./images/llm103.png)

**主要内容：** 用于评估 LLM 能力的标准化测试集和指标体系。涵盖知识、推理、代码、数学、安全等多个维度，是衡量模型进步的重要工具。

---

## 104. MMLU (Massive Multitask Language Understanding)

![](./images/llm104.png)

**主要内容：** 涵盖 57 个学科的大规模多任务语言理解基准测试，是评估 LLM 知识和推理能力的核心指标之一。

---

## 105. HumanEval / MBPP

![](./images/llm105.png)

**主要内容：** 两个主流的代码生成能力评估基准。HumanEval 包含 164 个 Python 编程问题，MBPP 包含约 1000 个入门级编程任务，均使用 Pass@K 指标评估。

---

## 106. Chatbot Arena

![](./images/llm106.png)

**主要内容：** LMSYS 组织运营的众包 LLM 评估平台，用户对匿名模型对战进行投票，通过 Elo 评分排名。是目前最具影响力的 LLM 竞技场式评估。

---

## 107. Tokenization

![](./images/llm107.png)

**主要内容：** 将原始文本切分为 Token（最小语义单元）的过程。是 LLM 处理文本的第一步，分词质量直接影响模型的理解和生成能力。

---

## 108. SentencePiece / Tiktoken

![](./images/llm108.png)

**主要内容：** 两种主流的分词工具。SentencePiece 由 Google 开发，支持 BPE 和 Unigram 算法；Tiktoken 是 OpenAI 的高效 BPE 实现，用于 GPT 系列模型。

---

## 109. Structured Output

![](./images/llm109.png)

**主要内容：** 让 LLM 按照预定义的结构化格式（如 JSON、XML）输出内容的技术。通过约束解码或格式指令，确保输出可被程序解析和处理。

---

## 110. JSON Mode / Function Calling

![](./images/llm110.png)

**主要内容：** LLM 输出结构化 JSON 或调用函数的能力。JSON Mode 确保输出为合法 JSON；Function Calling 让模型选择并参数化函数调用。两者是 LLM 与外部系统集成的基础。

---

## 111. Streaming

![](./images/llm111.png)

**主要内容：** LLM 逐 Token 实时输出生成结果的技术。用户无需等待完整响应即可看到部分结果，显著改善交互体验和感知延迟。

---

## 112. Caching (Semantic Cache)

![](./images/llm112.png)

**主要内容：** 通过缓存相似请求的 LLM 响应来减少重复计算和 API 调用的技术。语义缓存不仅匹配完全相同的请求，还能识别语义相似的查询并复用结果。

---

## 113. Coding Agent

![](./images/llm113.png)

**主要内容：** 专门用于软件开发的 AI Agent，能够理解需求、编写代码、调试错误、运行测试，自主完成编程任务。代表产品包括 Devin、Cursor、GitHub Copilot 等。

---

## 114. SWE-bench

![](./images/llm114.png)

**主要内容：** 评估 AI 编码 Agent 解决真实 GitHub Issue 能力的基准测试。包含来自主流开源项目的实际 bug 修复任务，是衡量 Coding Agent 实用性的重要指标。

---

## 115. Workflow Orchestration

![](./images/llm115.png)

**主要内容：** 将多个 LLM 调用、工具使用和人工审核步骤编排为自动化工作流的技术。通过定义任务依赖和执行顺序，实现复杂的多步骤 AI 应用。

---

## 116. Multi-Agent Systems

![](./images/llm116.png)

**主要内容：** 由多个 AI Agent 协作完成任务的系统。各 Agent 可承担不同角色（如规划者、执行者、审核者），通过通信和协调解决单个 Agent 难以处理的复杂问题。

---

## 117. Agentic RAG

![](./images/llm117.png)

**主要内容：** 将 AI Agent 的自主决策能力与 RAG 的检索增强能力相结合的技术。Agent 可以自主决定何时检索、检索什么、如何利用检索结果，实现更智能的知识利用。

---

## 118. Computer Use

![](./images/llm118.png)

**主要内容：** AI Agent 直接操作计算机界面（鼠标、键盘、屏幕）的能力。通过视觉理解和动作执行，Agent 可以像人类一样使用各种软件和网页应用。

---

## 119. Code Interpreter

![](./images/llm119.png)

**主要内容：** LLM 在安全沙箱中编写和执行代码的能力。模型可以运行 Python 代码处理数据、生成图表、进行数学计算，并将结果整合到回复中。ChatGPT 的 Advanced Data Analysis 即基于此。

---

## 120. Native Multimodal Agents

![](./images/llm120.png)

**主要内容：** 原生支持多模态输入输出（文本、图像、音频、视频）的 AI Agent。能够理解和生成多种模态的内容，实现更自然、更全面的人机交互。

---
