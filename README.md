# vite-plugin-version-log

一个用于在生产环境构建时注入版本信息的 Vite 插件。

## 功能特点

- 自动获取 Git 信息（分支、提交哈希、提交日期）
- 在生产环境构建时注入版本信息
- 在控制台优雅展示版本信息

## 安装
```bash
pnpm add -D vite-plugin-version-log
```

## 使用方法
```typescript
// vite.config.ts
import { defineConfig } from 'vite'
import { vitePluginVersionLog } from 'vite-plugin-version-log'

export default defineConfig({
  plugins: [
    vitePluginVersionLog({
      message: '当前版本信息',
      emoji: '🚀'
    })
  ]
})
```

## 配置选项

| 选项 | 类型 | 默认值 | 描述 |
|------|------|--------|------|
| message | string | '版本信息' | 版本信息的标题 |
| emoji | string | '📦' | 显示的表情图标 |

## 输出示例

在浏览器控制台中，你将看到类似下面的信息：

```
🚀 当前版本信息
构建分支: main
提交HASH: a1b2c3d
提交时间: Wed Mar 13 2024
构建时间: 2024/3/13 15:30:00
```

## 开发
```bash
# 安装依赖
pnpm install

# 开发模式
pnpm dev:example

# 构建
pnpm build

# 测试
pnpm test
```

## 注意事项

1. 该插件仅在生产环境构建时生效
2. 需要在 Git 仓库中使用才能获取完整的版本信息
3. 如果不在 Git 仓库中，相关信息将显示为 "unknown"

## License

MIT