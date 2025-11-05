# 集合（Collections）说明

为便于沉淀与扩展，项目提供基础集合的 Schema（平台无关）：

- `workflows.schema.json` — 工作流文件的结构约定。
- `agents.schema.json` — 多智能体的基础定义（角色、能力、模型等）。
- `intents.schema.json` — 多意图行业的意图定义与示例。

约定：
- 字段保持易扩展，允许 `additionalProperties`。
- 标识符统一使用字符串（如 `workflowId`、`agentId`、`intentId`）。