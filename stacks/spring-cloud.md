# Spring Cloud 微服务

**等级：recommended**

适用于 Profile 声明 `stack.backend.framework: spring-cloud` 的微服务项目。

- 只有在独立部署、扩缩容、故障隔离或团队自治存在明确需求时才拆分服务；服务围绕业务能力划分，并由单一团队负责其代码和运行。
- 每个服务维护自己的数据所有权，通过契约化接口或消息协作；避免共享业务数据库表、跨服务事务和以同步调用串联长链路。
- 使用 Spring Cloud 时只引入满足已识别需求的组件。服务发现、配置中心、网关、熔断和消息等基础设施应有清晰的运维责任、故障策略和观测指标。
- Spring Boot 与 Spring Cloud 版本必须遵循官方发布列车兼容矩阵，并使用对应 BOM 统一管理依赖；禁止通过覆盖兼容检查来掩盖不兼容组合。
- 为远程调用设置超时、重试边界、幂等策略和错误传播规则；重试不得放大非幂等写操作或形成级联故障。
- 接口契约应可版本化并对兼容性变更进行验证；日志、指标和追踪应能关联跨服务请求，同时避免记录凭证或敏感数据。

参考：[Spring Cloud 项目与发布列车](https://spring.io/projects/spring-cloud)、[Spring Cloud 文档](https://docs.spring.io/spring-cloud/reference/)。
