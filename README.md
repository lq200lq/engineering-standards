# Engineering Standards

Engineering Standards 是一组可按项目能力和技术栈组合的工程规则。规则以 Markdown 编写，`registry.yaml` 声明规则身份、适用条件、顺序和可由 CLI 执行的检查。

本仓库由 [Engineering Harness](https://github.com/lq200lq/engineering) 消费。npm CLI 包内置发布时固定 revision 的规范快照；使用者无需单独克隆本仓库。开发 CLI 或共同维护规则时，父仓库通过 `standards/` Git 子模块引用本仓库的一个已提交 revision。

## 规则目录

```text
standards/
├── registry.yaml
├── constitution/   # 所有项目共用的工程原则
├── decisions/      # 架构、依赖与边界决策
├── capabilities/   # 按能力启用的规则
├── validators/     # 项目结构与依赖检查说明
└── stacks/         # 具体语言、框架、数据库和工具规则
```

Registry 目前把 Constitution、决策和项目结构规则用于所有项目。其他规则按 Profile 中的字段选择：

| Profile 条件 | 载入规则 |
| --- | --- |
| `capabilities.backend`、`frontend`、`database`、`cache`、`mq`、`ai`、`fileStorage`、`apiDocumentation`、`authorization` 为 `true` | `capabilities/` 中对应领域的规则 |
| `deployment.internetAccess: false` | 离线部署规则 |
| `stack.backend.language: java` | Java、Java 版本、Lombok 规则 |
| `stack.backend.language: nodejs` | Node.js 规则 |
| `stack.backend.framework: spring-boot-monolith` 或 `spring-cloud` | 对应 Spring 规则 |
| `stack.frontend.framework: vue` 或 `nextjs` | 对应前端框架规则 |
| `stack.frontend.uiLibrary: ant-design` 或 `ant-design-vue` | 对应 UI 库规则 |
| `stack.frontend.adminScaffold: ant-design-pro` 或 `vben-admin` | 对应后台脚手架规则 |
| `stack.frontend.cssFramework: tailwindcss` | Tailwind CSS 规则 |
| `stack.database.type: postgresql` 或 `stack.database.migrationTool: flyway` | 对应数据库或迁移工具规则 |

Profile 字段由使用方的 `engineering.yaml` 提供。技术栈声明只决定装配哪些规则，不代表 CLI 会自动检测项目实际安装或运行的技术。

## 文档规则与自动检查

Markdown 规则用于描述约束、建议及适用背景。只有 Registry 中显式声明并受 Validator 支持的检查才会被机器执行。当前注册的自动检查是 README 文件存在性，级别为 `recommended`，不会阻断 `eng validate`。

CLI 支持的检查类型包括项目相对路径的 `file_exists`、`migration_exists`，以及 Node.js `package.json` 中的 `dependency_present` 和 `dependency_absent`。其中依赖检查只读取 `dependencies`、`devDependencies`、`optionalDependencies`，不比较版本。新增检查前要确认它能从受支持的输入中确定性判定，并同步更新 CLI、测试和使用说明。

不要把自然语言建议写成已经自动强制执行的检查；也不要仅因示例中出现某项做法，就将它设为 `mandatory`。为规则新增检查时，应说明等级和边界，并确保 `registry.yaml` 的检查声明与 Markdown 规则一致。

## 添加或修改规则

1. 明确规则适用场景，并判断它属于所有项目的原则、能力规则、决策规则还是技术栈规则。
2. 在对应目录新增或修改 Markdown 文件，写清适用范围、要求和例外。
3. 在 `registry.yaml` 中添加稳定的规则 ID、优先级、匹配条件和文件路径；只有支持的确定性检查才添加 `checks`。
4. 检查路径都指向本仓库内已有文件，并审阅 Registry 选择结果是否会让规则意外适用于其他项目。
5. 在本仓库运行 `git diff --check`，提交规范变更；如从父仓库开发，再运行父仓库规定的测试和包快照检查。

`registry.yaml` 中的 `standards.version` 标记规范内容版本；消费者的 Manifest 还会锁定完整 Git commit SHA，保证每次解析指向不可变的规范内容。父仓库的 `standards/` 子模块引用也必须更新到已提交的 revision。

## 双仓库维护

`standards/` 是独立 Git 仓库。修改规范时，先在本仓库提交；再回到 [Engineering Harness](https://github.com/lq200lq/engineering)，审阅并提交新的子模块引用。不要把未提交的子模块工作树状态当作可发布的规范快照。

完整的双仓库开发、验证和 Pull Request 流程见父仓库的[贡献指南](https://github.com/lq200lq/engineering/blob/main/CONTRIBUTING.md)。规范文件依据 Apache-2.0 许可证发布，详情见 [LICENSE](LICENSE)。
