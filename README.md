# 校园问答场景基础理论教学

本仓库面向校园场景下的问答系统教学，系统化讲解大模型应用开发的基础理论与工程实践。

课程围绕一个完整项目——**校园智能答疑助手**，从业务场景分析、Prompt 工程、检索增强（RAG）、Agent 系统构建到最终部署运维，帮助学习者掌握从"问题理解"到"系统落地"的全链路能力。

---

## 课程目录

### C1 构造问答系统

| 课时 | 标题 | 学习目标 |
|------|------|---------|
| 1.1 | 用大模型构建新人答疑机器人 | 调通大模型 API，理解多轮对话与 Token 计费 |
| 1.2 | 扩展答疑机器人的知识范围 | 用 RAG 让机器人读懂校园文档 |
| 1.3 | 优化提示词改善回答质量 | 系统提示词 + 思维链，提升回答稳定性 |
| 1.4 | 自动化评测答疑机器人的表现 | 搭建 RAGAS 评测流水线，量化回答质量 |
| 1.5 | 优化 RAG 应用提升问答准确度 | 句子窗口检索 + Reranker 两级优化 |

### C2 构建 Agent 系统

| 课时 | 标题 | 学习目标 |
|------|------|---------|
| 2.0 | 从回答问题到解决问题 | Agent 系统的核心思路与应用边界 |
| 2.1 | Agent 基础与工具调用 | Function Calling + ReAct + MCP 协议 |
| 2.2 | 让 Agent 学会规划与执行 | 反思机制 + 工作流 + 自主规划 |
| 2.3 | 用多 Agent 实现团队协作 | Boss/Worker 架构、多智能体分工 |
| 2.4 | 用 Memory 让 Agent 积累经验 | 短期/长期记忆 + 主动记忆管理 |
| 2.5 | 用 Skill 将能力固化为可复用流程 | 从 Prompt 到 Skill 的演进 |
| 2.6 | 用评测驱动 Agent 开发 | 确定性检查 + LLM-as-Judge + Rubric 评分 |
| 2.7 | Qwen Code 实践 | 掌握 Coding Agent 的日常工作方式 |

### C3 交付上线

| 课时 | 标题 | 学习目标 |
|------|------|---------|
| 3.1 | 用蒸馏让小模型掌握专业能力 | 准备蒸馏数据 → 微调训练 → 效果对比 |
| 3.2 | 部署模型 | 模型部署与推理服务 |
| 3.3 | 大模型应用生产实践 | 生产环境最佳实践 |
| 3.4 | 大模型应用安全合规 | 内容安全 + 合规审查 |

### C4 总结与展望

| 课时 | 标题 | 学习目标 |
|------|------|---------|
| 4.1 | 培养品味用 AI 为业务提效 | RIDE 方法论：选方向、定标准、验效果 |
| 4.2 | 总结与展望 | 演进逻辑回顾 + 核心方法论 |

---

## 共享模块

课程代码复用以下共享模块，Notebook 中直接 import 使用：

| 目录 | 用途 | 使用方式 |
|------|------|---------|
| `course_core/chatbot/` | 核心模块：LLM 调用、RAG、Agent、评测 | `from chatbot.llm import client, get_response` |
| `course_core/config/` | API Key 加载 | `from config.load_key import load_key; load_key()` |
| `course_core/docs/` | 测试文档 | RAG 实验用 |
| `course_core/knowledge_base/` | 知识库文件 | 向量检索数据源 |
| `course_core/ragas_prompt/` | RAGAS 评测提示词 | 评测流水线用 |
| `course_core/resources/` | 课程资源 | Notebook 引用 |
| `course_core/utils/` | 工具函数（安全模块等） | 按需导入 |

---

## 环境准备

> ⚠️ **重要提示：请使用 Python 3.10 运行本课程代码。**
>
> 本课程中的依赖包（如 LlamaIndex、LangChain 及相关扩展）已针对 Python 3.10 进行兼容性验证。使用其他 Python 版本可能会导致依赖冲突或运行时错误。

本课程假设你已初步了解 Python 与 Git。推荐通过以下命令创建 Python 3.10 虚拟环境：

```bash
# 请确认系统已安装 Python 3.10
python3.10 --version

# 创建虚拟环境（必须使用 Python 3.10）
python3.10 -m venv llm_learn
source llm_learn/bin/activate

# 安装依赖
pip install --upgrade pip
pip install -r requirements.txt
pip install ipykernel
python -m ipykernel install --user --name llm_learn --display-name "Python (llm_learn)"
```

> 注意：运行 Notebook 前请在右上角选择对应的 Python 内核 `Python (llm_learn)`。

---

## 许可

本仓库内容遵循 [Apache License 2.0](LICENSE) 开源协议。
