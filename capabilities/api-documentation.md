# API 文档与 OpenAPI

**等级：recommended**

适用于 Profile 声明 `capabilities.apiDocumentation: true` 的项目。

- 对外或跨团队使用的 HTTP API 应维护准确的接口契约，描述路径、方法、认证、参数、响应、错误语义和兼容性要求。
- 可使用 OpenAPI 描述 REST API，并以 Swagger UI、Swagger Editor 等工具提供浏览或校验体验；Swagger 工具是 OpenAPI 工作流的一部分，不取代规范本身。
- 明确契约的来源与生成流程。若从代码生成，应在 CI 中检查生成结果和源代码一致；若契约优先，应验证实现符合已评审的契约。
- 示例和 Schema 不得包含真实凭证、个人信息或生产数据；错误响应应避免泄露堆栈、内部路径和实现细节。
- 对破坏性 API 变更采用版本化、弃用窗口或兼容策略，并在发布记录中说明影响面。
- 对认证要求、分页、幂等、限流和错误格式采用项目统一约定；至少验证关键接口的成功、校验失败、未认证和无权限响应。

参考：[OpenAPI 规范与 Swagger 文档](https://swagger.io/docs/specification/)。
