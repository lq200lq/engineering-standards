# Engineering Standards 内容库

此仓库保存项目可继承的工程规则。`registry.yaml` 是 Resolver 的入口；它按 `engineering.yaml` 中的项目能力和技术栈选择 Markdown 规则。

## 规则覆盖

| 设计领域 | 规则位置 | 装配条件 |
| --- | --- | --- |
| Constitution 通用原则 | `constitution/` | 所有项目 |
| 技术与架构决策 | `decisions/` | 所有项目 |
| 项目结构检查 | `validators/project-structure.md` | 所有项目；README 检查为 recommended |
| Backend / Frontend / Database / Cache / MQ / AI / File Storage | `capabilities/` | 对应 `capabilities.*: true` |
| API 文档、成员角色与权限 | `capabilities/` | `capabilities.apiDocumentation: true` 或 `capabilities.authorization: true` |
| 离线部署 | `capabilities/offline-deployment.md` | `deployment.internetAccess: false` |
| Java 版本与 Lombok、Spring Boot Maven 多模块单体、Spring Cloud、Node.js | `stacks/` | Profile 声明对应后端语言或框架 |
| Vue、Next.js、Ant Design、Ant Design Pro、Ant Design Vue、Vben Admin、Tailwind CSS | `stacks/` | Profile 声明对应前端框架、UI 库、脚手架或 CSS 框架 |
| PostgreSQL、Flyway | `stacks/` | Profile 声明数据库类型或迁移工具 |

目前只有能够无歧义自动判定的 README 存在性检查接入 Validator。新增的 Migration、框架、UI 库和权限规则是推荐性文档，不伪装成机器已强制执行的检查。Profile 中的技术选择仅用于装配规则，不等同于依赖或运行环境自动检测。

所有新增规则都应能追溯到设计文档的明确决策，或由规范维护者通过独立评审补充。不要把仅供讨论的示例自动提升为 mandatory。
