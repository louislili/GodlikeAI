<img src="godlike.png" alt="Godlike AI" width="100%" />

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Apache_2.0%20%2B%20Additional_Terms-blue.svg" alt="License"></a>
  <a href="https://github.com/louislili/GodlikeAI/stargazers"><img src="https://img.shields.io/github/stars/louislili/GodlikeAI?style=social" alt="GitHub Stars"></a>
  <a href="https://github.com/louislili/GodlikeAI/network/members"><img src="https://img.shields.io/github/forks/louislili/GodlikeAI?style=social" alt="GitHub Forks"></a>
  <a href="https://github.com/louislili/GodlikeAI/issues"><img src="https://img.shields.io/github/issues/louislili/GodlikeAI" alt="GitHub Issues"></a>
  <a href="https://github.com/louislili/GodlikeAI/pulls"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome"></a>
</p>

# Godlike AI

让机器像神一样思考

## 愿景
- 以 Agent 为核心，将“让机器像神一样思考”的方法论落地到每一个项目。
- 输出的不只是工作流，更是具备先进性的神思 Agent：理解意图、多视角推理、工具调用、记忆管理、可评估与可复用。
- 以工程化与评测驱动沉淀模式库与能力栈，在真实场景中持续迭代。

## 方法论：神思 Agent
- 意图与角色：明确目标与角色切换，约束边界与输出风格。
- 多视角推理：拆分子任务、对立观点校验、计划—执行—反思闭环。
- 记忆与上下文：短期语境、长期语义记忆与任务记忆协同。
- 工具与检索：RAG、HTTP、数据库、插件与执行器组合，支持溯源。
- 策略调度：意图路由、阈值与重试、断点恢复与策略优先级。
- 评估与回溯：自动化评测、误判分析、数据闭环持续改进。
- 结构化输出：可解析的回复与引用，便于集成与治理。


## 核心定位
- 专注可落地的智能体工作流与工具，跨平台、跨领域（如工作流编排、聊天助理、自动化、DeFi Bot 等）。
- 每个工作流都直指目标问题，避免空泛描述，强调可复用与清晰命名。

## 命名与文件约定
- 工作流文件：`workflows/<平台或领域>/<名称>.workflow.json`
- 介绍文档：与工作流同名的 `*.md`，位于同一目录（例如：`workflows/assistant/multi-intent-routing-qa.md`）。
- 名称应一眼看出用途与场景，例如：`customer-support-multi-intent.workflow.json`、`defi-auto-rebalance.workflow.json`、`coze-content-curation.workflow.json`。
 - 智能体 Schema：`collections/agents.schema.json` 用于约定 Agent 的基本结构（角色、能力、工具与记忆），后续模板将以此为准。

## 目录结构
- `workflows/` — 工作流定义（平台或领域分目录存放）
- `collections/` — 集合（Schema）约定与说明（平台无关）
- `docs/` — 愿景与设计说明（简洁、直观）
- `metadata/` — 项目元数据与外部链接

## 快速上手
- 优先选择或实例化一个 Agent（后续将提供模板），并绑定所需工具与知识源。
- 在 `workflows/` 下找到合适工作流，阅读同名 `*.md` 了解目的、输入输出与注意事项。
- 若你的平台支持导入 JSON/YAML，直接使用 `*.workflow.json` 文件进行导入与配置。
- 按需修改意图、路由与数据源，保持命名规范与文档同步。

## 示例 Agent/工作流：多意图路由问答
- 简介：对用户问题进行多意图识别与路由，结合知识检索、HTTP 请求与插件能力，生成可溯源、可靠的回复。
- 文件：
  - 工作流定义：`workflows/fastgpt/多意图路由问答.workflow.json`
  - 介绍文档：`workflows/fastgpt/多意图路由问答.md`
- 输入/输出：输入 `user_question`（必填）与可选 `user_files`；输出结构化回复与可选引用（便于溯源）。
- 使用建议：导入后配置意图集合（如打招呼/使用问题/购买问题/其他）、知识源连接、外部请求端点与鉴权、回复模板；扩展行业意图时保持同名介绍与工作流同步。

## 交流与支持
- 问题与建议：在 GitHub `Issues` 提交（按模块清晰描述场景与期望）。
- 贡献与修复：直接发起 `Pull Request`，遵循同名工作流/文档约定与简洁提交信息。
- 商用与授权：请参考 `COMMERCIAL-USE.md`，或在 `Issues` 中进行沟通。

## 了解与联系
- 官网：[https://yigather.com/](https://yigather.com/)（了解公司与更多案例）
- 抖音：[抖音主页](https://www.douyin.com/user/MS4wLjABAAAARyKh_W-ahMmF08jLosvVbXFNfW57rklTDcFTyrgWfKr53T71f7JGLjNq5tQBGvw6?from_tab_name=main&vid=7395772480226463013)（关注短视频更新）

## 开源与贡献
- 许可：`Apache-2.0 + Additional Terms v1.0`，详情见 `LICENSE`。
- 贡献方式：在对应目录新增工作流与同名介绍文档，遵守命名规范，不包含敏感信息；提交 PR 或 Issue 说明场景与价值。

## 路线图
- 神思 Agent 模板库：角色/能力/工具/记忆的标准化定义与示例。
- 评测与对齐：自动化评测 Harness、多维指标与误判回溯。
- 记忆与上下文：长期记忆管理、检索路由与上下文压缩策略。
- 多智能体协作：任务分解、协同与竞争、仲裁与合并策略。
- 跨平台移植：结构化工作流模板，导入/导出与兼容层。
- 数据治理与安全：审计、脱敏、溯源引用与合规策略。

## 说明
- 仓库不包含敏感信息（密钥、账号）。如需本地环境变量，请使用 `.env`（已在 `.gitignore` 中忽略）。