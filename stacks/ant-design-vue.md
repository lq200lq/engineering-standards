# Ant Design Vue

**等级：recommended**

适用于 Profile 声明 `stack.frontend.uiLibrary: ant-design-vue` 的 Vue 项目。

- 使用组件库提供的语义化组件和设计令牌；应用级主题通过集中配置维护，避免页面样式穿透或全局覆盖造成不可预测的影响。
- 统一组件版本、图标、国际化和日期处理方式；按当前 Ant Design Vue 版本文档使用组件 API，不复制其他 Vue UI 库的用法。
- 表单需处理校验和提交状态；数据表格需明确分页、筛选、排序及空状态的数据来源和服务端契约。
- 仅导入实际使用的组件和图标，检查构建体积；避免为单一页面引入重复的组件库或反馈机制。
- 升级时检查 Vue 兼容性、组件 API、样式变量及主题行为，并覆盖关键交互回归。
- 为组件提供可访问名称、键盘操作和清晰的校验错误提示；不能只依赖颜色或图标表达状态。

参考：[Ant Design Vue 组件文档](https://antdv.com/components/overview)。
