# Spring Boot Maven 多模块单体

**等级：recommended**

适用于 Profile 声明 `stack.backend.framework: spring-boot-monolith` 的 Java 后端。

- 以一个可独立部署的 Spring Boot 应用承载业务，在确有代码所有权或变化边界时用 Maven 多模块组织代码；模块划分应表达业务能力或稳定技术边界，而不是按 Controller、Service、DAO 等技术层机械拆分。
- 根 POM 统一管理 Java 编译目标、Spring Boot parent 或 BOM、插件和依赖版本；子模块只声明自身依赖，避免重复版本与跨模块循环依赖。
- 明确可执行应用模块及启动入口。公共模块不应依赖 Web 启动流程；持久化、接口适配和业务模块之间的依赖方向应可理解并可检查。
- 模块内保持事务和业务规则边界清晰。跨模块调用优先使用公开接口，不直接访问其他模块内部实现或数据库表作为集成契约。
- 用 Maven Reactor 执行聚合构建与测试；CI 应能从根 POM 完整构建，并验证需要共同发布或部署的模块。
- 只有在业务边界稳定、独立部署有明确收益时，才将模块拆为独立服务；多模块本身不是微服务的理由。

参考：[Maven 多模块项目指南](https://maven.apache.org/guides/mini/guide-multiple-modules.html)、[Spring Boot 构建系统](https://docs.spring.io/spring-boot/reference/using/build-systems.html)。
