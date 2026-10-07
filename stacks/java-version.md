# Java 版本选择

**等级：recommended**

适用于 Profile 声明 `stack.backend.language: java` 的项目。

- 新项目优先评估仍在维护期的长期支持版本（LTS）；只有产品、依赖或平台确有要求时才选非 LTS 版本。
- 选择前核对 Spring Boot、Spring Cloud、构建插件、关键依赖、运行容器和生产平台的兼容范围，采用所有必要组件共同支持的版本。
- 明确编译目标、开发 JDK、CI JDK 和生产运行 JRE/JDK 的关系；使用工具链或构建配置固定项目要求，不能只依赖开发者本机默认版本。
- 记录选择理由、支持期限、升级责任和升级窗口；当支持期、依赖兼容或安全维护变化时重新评估。
- 尽可能在 CI 中使用与生产相同的主要 Java 版本构建和测试；如需多版本兼容，应将支持矩阵作为明确验收范围。
- 不使用预览特性，除非项目已批准其生产风险并建立明确退出或升级计划。

具体 LTS 版本与各框架支持范围会变化，应以 [Java 官方发布信息](https://www.oracle.com/java/technologies/java-se-support-roadmap.html)、[Spring Boot 系统要求](https://docs.spring.io/spring-boot/system-requirements.html) 和所用 Spring Cloud 发布列车文档为准。
