# 商业合同风控审查 - Agent 工作流

本项目在 Dify 平台上构建，采用线性可视化工作流编排：

```mermaid
flowchart LR
    Input(["👤 用户输入 (Start)"]) --> LLM["🧠 LLM 节点 (Gemini Vision)"]
    LLM --> Code["💻 代码执行 (Code)"]
    Code --> Output(["📄 标准化输出 (JSON)"])
