# Vben Admin

**等级：recommended**

适用于 Profile 声明 `stack.frontend.adminScaffold: vben-admin` 的管理后台项目。

- 初始化后先确认使用的 Vben Admin 版本、应用模板和组件库变体，并以当前版本文档为准；不要将其他版本的目录结构、命令或配置直接套用。
- 尊重脚手架的 Monorepo、workspace、应用和内部包边界。业务代码应位于项目约定的应用或包中，不随意修改生成器、内部工具和共享配置来实现单个页面需求。
- 路由、菜单、布局、权限指令和访问控制应使用脚手架提供的正式扩展点，并明确后端授权检查仍是最终权限边界。
- 新建管理页面优先复用已有表格、表单、请求、国际化和权限模式；添加依赖前确认仓库已有能力及其维护状态。
- 保持 lockfile、Node.js、包管理器与 workspace 配置一致；新增应用、内部包或共享配置后运行仓库级校验和受影响应用构建。
- 移除示例页面或 mock 行为时检查路由、菜单、权限、国际化和演示数据引用，避免保留死入口或误将 mock 服务发布到生产。

参考：[Vben Admin 项目文档](https://doc.vben.pro/guide/introduction/vben.html)、[目录说明](https://doc.vben.pro/guide/project/dir.html)。
