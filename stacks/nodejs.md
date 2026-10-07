# Node.js

**等级：recommended**

适用于 Profile 声明 `stack.backend.language: nodejs` 的服务端项目。

- 生产环境使用仍处于 Active LTS 或 Maintenance LTS 支持期的 Node.js 版本，并在 `engines`、运行镜像和 CI 中保持一致；按官方发布计划及时升级。
- 提交所选包管理器的锁文件，CI 使用锁文件执行可复现安装；同一仓库避免混用多个包管理器或重复维护多份锁文件。
- 区分启动配置、业务逻辑与 I/O 边界；异步任务应处理拒绝、取消和资源释放，不让未处理错误静默丢失。
- 通过环境变量或受控配置注入运行参数。密钥不得进入仓库、镜像或客户端可访问的构建产物。
- 服务端入口应验证外部输入、限制请求体和资源消耗，并对日志中的个人数据、令牌和凭证进行脱敏。
- 使用项目实际采用的 TypeScript、JavaScript 模块和框架约定；不因 Node.js 运行时本身而强制迁移语言或引入框架。

参考：[Node.js 发布计划](https://nodejs.org/en/about/previous-releases)、[Node.js 安全说明](https://nodejs.org/en/about/eol)。
