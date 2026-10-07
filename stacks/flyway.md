# Flyway 数据库版本管理

**等级：recommended**

适用于 Profile 声明 `stack.database.migrationTool: flyway` 的项目。

- 将迁移脚本纳入版本控制，并在所有环境中按同一迁移历史推进数据库；禁止通过线上手工改表绕开迁移。
- 对已应用到共享或下游环境的版本化迁移保持不可变；修正已发布变更时新增向前迁移，不重写历史来伪装回滚。
- 使用唯一、可排序的版本号和描述；团队应选定递增编号或时间戳等一种并发冲突策略，并在项目中保持一致。
- 在 CI 或部署流程中验证待执行迁移，明确数据库目标、执行身份、审批边界和失败处置；生产凭证应采用最小权限并由受控密钥系统提供。
- 对破坏性变更使用兼容性迁移步骤，例如先增量发布兼容结构、迁移数据、切换读写后再删除旧结构；评估锁表、执行时长和回滚限制。
- 应用迁移失败时先检查数据库实际状态和 Flyway 历史记录，再进行受审查的恢复；不得直接篡改历史表或重复执行有副作用的数据脚本。
- 对迁移命名、目录、占位符、基线和校验策略使用仓库统一约定，并定期在接近生产的数据量或副本上验证耗时与锁行为。

参考：[Flyway 迁移概念](https://documentation.red-gate.com/flyway/flyway-concepts/migrations)、[版本化迁移](https://documentation.red-gate.com/flyway/flyway-concepts/migrations/versioned-migrations)。
