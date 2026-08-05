# 🔄 Agent 工作流设计 (Workflow)

## 1. 业务流程逻辑图
本项目采用 Dify 的 Workflow 编排模式，完整映射了真实的销售闭环机制。加入了并行节点与工具调用（Tool Calling），突破了单聊机器人的局限。

```mermaid
graph TD
    A[Start: 输入客户资料 & 会议纪要] --> B[LLM: 客户需求深度分析]
    B --> C{并行处理节点}
    C --> D[LLM: 生成针对性销售建议]
    C --> E[LLM: 撰写定制化跟进邮件]
    B --> F[Tool Calling: 提取关键字段]
    F --> G[HTTP Request: 同步至企业 CRM]
    D --> H[聚合输出节点]
    E --> H
    G --> H
    H --> I[End: 呈现最终销售工作台界面]
