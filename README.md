# Engineering Standards 内容库

此仓库保存项目可继承的工程规则。`registry.yaml` 是 Resolver 的入口；它按 `engineering.yaml` 中的项目能力和技术栈选择 Markdown 规则。

## 规则覆盖

| 设计领域 | 规则位置 | 装配条件 |
| --- | --- | --- |
| Constitution 通用原则 | `constitution/` | 所有项目 |
| 技术与架构决策 | `decisions/` | 所有项目 |
| 项目结构检查 | `validators/project-structure.md` | 所有项目；README 检查为 recommended |
| Backend / Frontend / Database / Cache / MQ / AI / File Storage | `capabilities/` | 对应 `capabilities.*: true` |
| 离线部署 | `capabilities/offline-deployment.md` | `deployment.internetAccess: false` |
| Java / Vue / PostgreSQL | `stacks/` | Profile 明确选中对应技术栈 |

目前只有能够无歧义自动判定的 README 存在性检查接入 Validator。数据库 Migration 路径和各语言的依赖清单尚未在 Profile/Registry 中约定，因此相关规则作为 recommended / guideline 提供，不伪装成机器已强制执行的检查。

所有新增规则都应能追溯到设计文档的明确决策，或由规范维护者通过独立评审补充。不要把仅供讨论的示例自动提升为 mandatory。
