# 依赖检查边界

**等级：recommended**

- 自动依赖检查只应判断 Registry 明确声明的包名是否存在或禁止，不推断包是否实际使用，也不比较未声明的版本阈值。
- 明确支持的包清单解析器之前，不应把其他生态的清单解析结果猜测为通过或失败。
- 依赖清单损坏、不可读或格式不受支持时，应报告无法确定，而不是通过检查。
- “依赖过重”“未来可能不用”等主观评价不能单独作为确定性失败条件。

当前 CLI 只解析 Node `package.json` 中的 `dependencies`、`devDependencies` 和 `optionalDependencies`。
