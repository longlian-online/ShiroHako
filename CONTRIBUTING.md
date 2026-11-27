# 贡献指南

感谢你对 **白箱 ShiroHako** 的关注与支持！欢迎通过提交 Issue、完善文档或贡献代码来一起改进项目。

## 仓库分工

本仓库（`ShiroHako`）是项目的总览与聚合仓库，前后端代码分别维护在各自独立的子仓库中：

| 内容 | 推荐提交位置 |
| --- | --- |
| 产品建议、跨端 Bug、使用咨询、总览文档与部署说明 | 本仓库 [`longlian-online/ShiroHako`](https://github.com/longlian-online/ShiroHako) |
| 前端界面、交互、使用手册与客户端代码 PR | [`longlian-online/longlian-oa-frontend`](https://github.com/longlian-online/longlian-oa-frontend) |
| 后端接口、工作流引擎、数据库迁移、MCP 与服务端代码 PR | [`longlian-online/longlian-oa-backend`](https://github.com/longlian-online/longlian-oa-backend) |

如果不确定问题属于前端还是后端，直接在本仓库提交 Issue 即可，维护者会协助分流。

## 提交 Issue

- **反馈 Bug**：请尽量附带复现步骤、期望结果、实际表现、截图或报错日志，以及你使用的版本/环境信息。
- **功能建议**：请说明使用场景（例如团队流程协作中的具体环节）和想要解决的问题，而不仅仅是最终方案。
- 提交前可以先搜索已有 Issue，避免重复反馈。

## 提交 Pull Request

1. Fork 目标仓库并从 `main` 拉出新分支（例如 `feat/xxx`、`fix/xxx`、`docs/xxx`）。
2. 保持改动聚焦，一个 PR 尽量只解决一个明确的问题。
3. 提交前请运行对应仓库的检查与测试：
   - **前端**（`shirohako-frontend`）：使用 `vp check` 完成格式、lint 和类型检查。
   - **后端**（`shirohako-backend`）：参考 [后端开发说明](https://github.com/longlian-online/longlian-oa-backend/blob/main/docs/dev.md) 与 `task test-docker` 运行单元测试和 API 测试。
4. 发起 PR 时说明改动动机、核心变更以及验证方式；若涉及界面调整，建议附上前后截图。

### Commit 规范

项目采用 [Conventional Commits](https://www.conventionalcommits.org/) 风格：

```text
<type>(<scope>): <subject>
```

常用 `type`：`feat`、`fix`、`docs`、`style`、`refactor`、`perf`、`test`、`build`、`ci`、`chore`、`revert`。更多细节可参考后端仓库的 [CONTRIBUTING.md](https://github.com/longlian-online/longlian-oa-backend/blob/main/docs/CONTRIBUTING.md)。

## 同步 Submodule 指针

本仓库通过 Git submodule 关联前后端的 `main` 分支。日常功能开发请在对应子仓库完成；当需要更新总仓库记录的子模块版本时，可运行：

```bash
git submodule update --remote
```

确认变更后在本仓库提交更新。
