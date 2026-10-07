# Next.js

**等级：recommended**

适用于 Profile 声明 `stack.frontend.framework: nextjs` 的项目。

- 新功能优先采用项目已选定的 Next.js 路由模型，并遵循其对应版本的文件约定；不要在同一应用中无明确迁移计划地混用 Pages Router 与 App Router 模式。
- 明确 Server 与 Client Component 的边界。仅在需要浏览器 API、交互状态或客户端事件时使用 Client Component，并尽量缩小客户端代码范围。
- 在服务端边界验证身份、权限和输入；隐藏按钮或客户端路由判断不构成授权。返回客户端的数据应按字段白名单最小化。
- 明确缓存、动态渲染和数据更新策略；涉及用户隔离的数据不能误用共享缓存。重要行为以当前 Next.js 版本官方文档为准。
- 通过服务端数据访问层封装数据库和内部 API 调用，避免在组件中散布数据访问或把服务端密钥暴露给客户端代码。
- 对路由、加载、错误和空数据状态提供可理解的用户反馈，并验证关键页面的无障碍与生产构建行为。

参考：[Next.js App Router 文档](https://nextjs.org/docs/app)、[数据安全指南](https://nextjs.org/docs/app/guides/data-security)、[生产检查清单](https://nextjs.org/docs/app/guides/production-checklist)。
