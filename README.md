# vite-plugin-version-log

一个用于在生产环境构建时注入版本信息的 Vite 插件。

## 功能特点

- 自动获取 Git 信息（分支、提交哈希、提交日期）
- 在生产环境构建时注入版本信息
- 通过 console.table 在控制台美观展示

## 安装
```bash
pnpm add -D vite-plugin-version-log
```

```typescript
// vite.config.ts
import { defineConfig } from 'vite'
import vitePluginVersionLog from 'vite-plugin-version-log'
export default defineConfig({
  plugins: [
    vitePluginVersionLog({
      enable: true,
      message: '当前版本信息'
    })
  ]
})
```

## 开发

## 配置选项

| 选项 | 类型 | 默认值 | 描述 |
|------|------|--------|------|
| enable | boolean | true | 是否启用插件 |
| message | string | '版本信息' | 版本信息的标题 |

## 输出示例

在浏览器控制台中，你将看到类似下面的信息表格：

```bash
┌────────────┬──────────────────────┐
│ (index) │ Values │
├────────────┼──────────────────────┤
│ message │ 当前版本信息 │
│ branch │ main │
│ commit │ a1b2c3d │
│ commitDate│ Wed Mar 13 2024 │
│ buildDate │ 2024/3/13 15:30:00 │
└────────────┴──────────────────────┘
```

## 开发
```bash
pnpm install
pnpm dev
```

## 构建
```bash
pnpm build
```

## 测试
```bash
pnpm test
```

## 注意事项

1. 该插件仅在生产环境构建时生效
2. 需要在 Git 仓库中使用才能获取完整的版本信息
3. 如果不在 Git 仓库中，相关信息将显示为 "unknown"

## License

MIT