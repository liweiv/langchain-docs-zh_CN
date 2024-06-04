
![](https://cdn.liweiv.com/imgs/2024-06-04-langchain.svg)

# 介绍

LangChain 是一个用于开发由大型语言模型（LLMs）驱动的应用程序的框架。

LangChain 简化了 LLM 应用程序生命周期的每个阶段：

- 开发：使用 LangChain 的开源构建块和组件构建您的应用程序。通过第三方集成和模板快速启动。
- 生产化：使用 LangSmith 检查、监控和评估您的链，以便您能够持续优化和自信地部署。
- 部署：使用 LangServe 将任何链转换为 API。

![](https://cdn.liweiv.com/imgs/2024-06-04-133938.png)

具体来说，该框架由以下开源库组成：

- ```langchain-core```：基础抽象和 LangChain 表达语言。

- ```langchain-community```：第三方集成。
  
   - 合作伙伴包（例如 langchain-openai、langchain-anthropic 等）：一些集成进一步分拆为仅依赖于 langchain-core 的轻量级包。
   
- ```langchain```：构成应用程序认知架构的链、代理和检索策略。

- **[langgraph](https://langchain-ai.github.io/langgraph)**: 图中的边和节点，使用 LLM 构建稳健和有状态的多角色应用程序。

- langserve：将 LangChain 链部署为 REST API。

- langSmith：一个开发者平台，让您调试、测试、评估和监控 LLM 应用程序。

>注意
这些文档重点介绍 Python LangChain 库。[点击这里](https://js.langchain.com/)查看 JavaScript LangChain 库的文档。

## 教程
如果您希望构建特定的内容或更喜欢动手学习，请查看我们的教程。这是开始的最佳地方。

这些是最好的入门教程：

构建一个简单的 LLM 应用程序
构建一个聊天机器人
构建一个代理
在这里探索完整的教程列表。

## 操作指南
在这里您会找到关于“如何……”类型问题的简短答案。这些操作指南不会深入涵盖主题——您会在教程和 API 参考中找到这些内容。然而，这些指南将帮助您快速完成常见任务。

## 概念指南
介绍您需要了解的所有关键 LangChain 部分！在这里，您会找到所有 LangChain 概念的高层次解释。

## API 参考
前往参考部分以获取 LangChain Python 包中所有类和方法的完整文档。

## 生态系统

### 🦜🛠️ LangSmith 
追踪并评估您的语言模型应用程序和智能代理，帮助您从原型转向生产环境。

### 🦜🕸️ LangGraph 
使用 LLM 构建有状态的多角色应用程序，建立在 LangChain 原语之上（并旨在与其一起使用）。

### 🦜🏓 LangServe 

将 LangChain 可运行对象和链部署为 REST API。

## 其他资源

### 安全性
阅读我们的安全最佳实践，确保您在使用 LangChain 开发时保持安全。

### 集成 
LangChain 是一个丰富的工具生态系统的一部分，这些工具与我们的框架集成并在其基础上构建。查看我们不断增长的集成列表。

### 贡献 
查看开发者指南，了解贡献的指导方针并帮助您设置开发环境。

<div id="giscus-container"></div>

