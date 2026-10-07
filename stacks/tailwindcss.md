# Tailwind CSS

**等级：recommended**

适用于 Profile 声明 `stack.frontend.cssFramework: tailwindcss` 的前端项目。

- 优先使用 Tailwind 提供的实用类表达局部布局和样式；重复出现且有稳定语义的界面模式再抽取组件或样式抽象。
- 将颜色、间距、字号等设计决策集中在项目主题配置或 CSS 变量中，避免在页面中散布互相矛盾的任意值。
- 遵循当前版本的类名扫描和构建配置；动态拼接的类名必须确保构建工具能发现，或通过受控的映射显式声明。
- 对响应式、状态和暗色模式采用一致的断点与变体约定；不要将大量条件逻辑堆入难以阅读的 class 字符串。
- 与组件库并用时明确样式所有权、优先级和主题来源；使用前验证样式重置与组件默认样式不会相互破坏。
- 保持语义化 HTML、焦点状态和对比度；工具类不替代无障碍检查。

参考：[Tailwind CSS 核心概念](https://tailwindcss.com/docs/styling-with-utility-classes)。
