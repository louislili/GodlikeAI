# Agent Kimi 工作流（Dify，介绍）

- 同名工作流文件：`Agent Kimi.yml`
- 目的：构建一个类似 Manus 的多循环意图智能体，形成“规划—执行—反思”的闭环，按步骤推进任务并产出可复核结果。

## 适用场景
- 研究与检索：围绕用户意图拆解任务，自动搜索信息并汇总。
- 任务分解执行：将复杂需求拆为多步 todo，逐步完成并记录结果。
- 连续改进：在每次迭代后进行反思，总结完成度与下一步行动。

## 架构要点
- 意图理解与规划：结合 `sys.query` 与会话变量，生成/读取 `conversation.todo`（任务拆解）。
- 循环执行（current_index）：按 `conversation.current_index` 仅执行当前步骤，避免跨步跳跃。
- 工具与检索：内置 Serper 搜索工具（Google/网页片段检索），支持关键词自动生成与溯源。
- 反思与推进：分类/总结当前步骤的完成度，决定“继续下一步”或“跳出流程”。
- 状态与断点恢复：对话变量 `results`、`todo_current`、`index` 记录过程与结果，便于断点续跑。
- 模型与策略：Kimi-K2（LLM）结合 FunctionCalling，支持稳定的工具调用与结构化输出。

## 输入与输出
- 输入：`sys.query`（必填，用户原始意图/问题）；可选加载既有 `conversation.todo`。
- 输出：结构化 JSON（示例字段）：`plan[]/todo[]`、`current_step_output`、`references[]`、`next_action`、`done_flag`、`results`（汇总）。

## 使用建议
- 迭代上限：根据场景调整 `maximum_iterations`（默认 15），防止长循环。
- 工具配置：为 Serper 搜索配置密钥与配额；按需增加数据库/RAG 工具。
- 步骤一致性：严格按 `current_index` 只执行当前步骤，避免跨步或跳过。
- 结构化输出：保持 JSON 可解析，便于存储与后续分析/渲染。

## 脱敏说明
- 工作流与文档不包含密钥、账号或具体公司/个人信息；外部端点与鉴权请使用环境变量与平台安全配置。