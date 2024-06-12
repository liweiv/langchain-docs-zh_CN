# 构建聊天机器人

## 概述

我们将通过一个示例来讲解如何设计和实现一个由 LLM 驱动的聊天机器人。这个聊天机器人将能够进行对话并记住之前的互动。

请注意，我们构建的这个聊天机器人只会使用语言模型来进行对话。你可能还在寻找其他几个相关的概念：

[对话式 RAG](https://python.langchain.com/v0.2/docs/tutorials/qa_chat_history/)：在外部数据源上启用聊天机器人体验

[代理](https://python.langchain.com/v0.2/docs/tutorials/agents/)：构建一个可以执行操作的聊天机器人

本教程将涵盖基础知识，这些知识对于上述两个更高级的主题会有所帮助，但如果你愿意，也可以直接跳到那些部分。

## 概念

以下是我们将要使用的一些高级组件：

- [`聊天模型(Chat Models)`](https://python.langchain.com/v0.2/docs/concepts/#chat-models)：聊天机器人界面基于消息而不是原始文本，因此更适合使用聊天模型而不是文本 LLM。

- [`提示模板(Prompt Templates)`](https://python.langchain.com/v0.2/docs/concepts/#prompt-templates)：简化了组合默认消息、用户输入、聊天历史记录和（可选的）额外检索上下文的提示的过程。

- [`聊天历史(Chat History)`](https://python.langchain.com/v0.2/docs/concepts/#chat-history)：允许聊天机器人“记住”过去的互动，并在回答后续问题时考虑这些互动。

- 使用 LangSmith 进行调试和追踪：帮助你调试和追踪你的应用程序。

我们将介绍如何将上述组件结合起来，创建一个强大的对话式聊天机器人。

## 设置

### Jupyter Notebook

本指南（以及文档中的大多数其他指南）使用 Jupyter Notebook，并假设读者也是如此。Jupyter Notebook 非常适合学习如何使用 LLM 系统，因为很多时候事情可能会出错（意外输出、API 停止工作等），在交互式环境中进行学习是更好地理解它们的好方法。

这个和其他教程可能最方便在 Jupyter Notebook 中运行。有关如何安装的说明，请参见这里 。

### 安装

要安装 LangChain，请运行以下命令(二选一)：

- 通过 pip 安装

```bash
pip install langchain
```

- 通过 Conda 安装

```bash
conda install langchain -c conda-forge
```

有关更多详细信息，请参见我们的[安装指南](https://python.langchain.com/v0.2/docs/how_to/installation/)。

## LangSmith

你使用 LangChain 构建的许多应用程序将包含多个步骤，并多次调用 LLM。随着这些应用程序变得越来越复杂，能够检查链或代理内部发生的具体情况变得至关重要。使用 [LangSmith](https://smith.langchain.com/) 是实现这一目标的最佳方式。

在上面的链接注册后，请确保设置你的环境变量以开始记录追踪信息：

```bash
export LANGCHAIN_TRACING_V2="true"
export LANGCHAIN_API_KEY="..."
```
或者，如果在 Jupyter Notebook 中，你可以使用以下方式设置环境变量：
```bash
import getpass
import os

os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = getpass.getpass()
```
