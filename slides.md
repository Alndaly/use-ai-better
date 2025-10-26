---
# try also 'default' to start simple
# theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: 如何用好AI？
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 60min
---

# 如何用好AI？

Rag / Context Engineering

---

# 近年来的AI交互的历史发展

- **单纯的LLM** - 只有一个对话聊天框，没有任何其他的功能
- **多模态** - AI开始支持多种类型的输入源和输出，可以浏览图片、视频等内容
- **微调** - 由于大模型训练的数据类型纷杂，在垂直领域的能力较弱，因此需要通过微调来提升特定领域的性能
- **RAG** - 通过RAG的方式，将部分知识提前作为prompt的一部分，让大模型能够更准确的回答问题
- **Tool Call** - 由于模型本身不具备联网、存储等能力，因此各AI提供商纷纷推出自己的工具调用机制，让模型能够调用外部工具来增强自身的功能
- **Workflow** - 通过定制的workflow，让大模型在固定的流程中，配合其他的脚本执行和调用，实现更复杂的功能
- **GraphRAG（RAG的演变）** - 先将知识点进行知识图谱的绘制，在提问的时候通过一些图算法快速索引到问题相关内容，并将其作为prompt的一部分，大大提高了模型回答问题的准确度
- **MCP** - 通用模型上下文协议，支持所有大模型去调用外部工具
- **Agent** - 通过不断循环的方式，让大模型能够自主的调用工具，并自主的进行决策

---
layout: center
---

# 方式一：提示词优化

Prompt Engineering

---
layout: center
---

# 提问时要明确具体

- 模糊提问

```
附近有什么好吃的？
```

- 具体提问
```
你能推荐一家在西湖附近的中餐厅、拥有室外座位且距离苏堤步行10分钟的餐厅吗？我想找环境优美、评价高的餐厅。
```

---
layout: center
---

# 提供必要的背景和上下文

- 无背景

```
什么时候去新疆最合适？
```

- 人物、背景限定

```
我想去新疆旅游，且想拍星空，而你是一名经验十足的旅游者，请根据你的经验和我聊聊一下最适合去新疆旅游的时间，结合天气、地点等等因素。
```

---
layout: center
---

# 任务分解

- 无任务分解

```
帮我写一份会议报告。
```

- 分解提问
  
```
请帮我写一份会议报告大纲，需要包括会议主题、会议时间、会议人员、会议总结、具体内容等信息，完成后继续细化各项内容。
```

---
layout: center
---

# 少样本学习

- 无样本：

```
请帮我分析这句话的情绪：“今天天气真好，心情也挺好。”
```

- 少样本示例： 

```
请根据下面的示例判断句子的情感（正面或负面），按照“输入句子 → 情感标签”的格式回答。

示例：
- 这部电影真是太棒了！ → 正面
- 我对这次购物体验非常失望。 → 负面

请判断下面这句话的情感：
- 服务员的态度非常好，我们度过了愉快的一晚。
```

---
layout: center
---

# 链式思维提示

- 无链式思维

```
请帮我写一篇关于人工智能的论文。
```

- 链式思维

```
请逐步思考并帮我写一篇关于人工智能的论文。
首先，请列出人工智能的定义和主要应用领域。
然后，探讨人工智能的发展历程和未来趋势。
最后，分析人工智能可能带来的挑战和机遇。
```

---
layout: center
---

# 方式二：微调

Fine-tuning

---
layout: iframe

# 网页来源
url: https://llamafactory.readthedocs.io/zh-cn/latest/
---

---
layout: center
---

# 方式三：RAG

Retrieval-Augmented Generation

---
layout: center
---

# RAG是什么？

- **RAG**：Retrieval-Augmented Generation
- **检索**：从知识库中检索相关的信息
- **生成**：将检索到的信息作为prompt的一部分，让大模型生成回答

---
layout: center
---

# RAG的优势

- **简单**：只需要将知识库中的信息作为prompt的一部分，让大模型生成回答
- **高效**：通过检索的方式，可以快速找到相关的信息，提高回答的准确度
- **灵活**：可以针对不同的领域和问题，定制不同的知识库，实现更准确的回答

---

![](https://www.microsoft.com/en-us/research/wp-content/uploads/2024/02/GraphRag-Figure3.jpg)


---
layout: center
---

# 方式四：MCP

Model Context Protocol

![mcp-simple-diagram](https://mintcdn.com/mcp/bEUxYpZqie0DsluH/images/mcp-simple-diagram.png?fit=max&auto=format&n=bEUxYpZqie0DsluH&q=85&s=35268aa0ad50b8c385913810e7604550)

---
layout: center
---

# MCP是什么？

- **MCP**：Model Context Protocol
- **协议**：一种让大模型能够调用外部工具的协议
- **工具**：可以是任何可以联网的工具，比如搜索引擎、数据库、API等等

---
layout: center
---

# MCP的优势

- **互通**：所有的平台都遵循相同的协议，可以实现工具的互通
- **灵活**：可以调用任何的工具，实现更复杂的功能


---
layout: center
---

# 方式五：Agent

Agent

![](https://www.falkordb.com/wp-content/uploads/2024/11/AI-Agents-Architecture-by-falkordb.webp)

---
layout: center
---

# Agent是什么？

- **Agent**：一个能够自主决策和执行任务的助手
- **决策**：根据当前的任务和状态，选择合适的工具和策略
- **执行**：调用工具和策略，实现任务的目标

---
layout: center
---

# Agent的优势

- **自主**：不需要任何人工干预，可以完全自主的完成任务
- **灵活**：可以调用任何的工具和策略，实现极其复杂的功能