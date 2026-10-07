# PostgreSQL 技术栈

**等级：recommended**

适用于 Profile 声明 `stack.database.type: postgresql` 的项目。

- Schema 变更通过项目采用的 Migration 管理；SQL 和回滚限制应可审查。
- 索引基于查询条件和实际计划评估，不为每个字段机械添加索引。
- 关注事务范围、锁等待和批量查询行为；优化应由查询计划、数据规模或测量结果支持。
- 使用参数化查询和数据库访问层已有能力处理输入，避免拼接不可信 SQL。

本规则不假定具体 PostgreSQL 版本、ORM 或 Migration 工具。
