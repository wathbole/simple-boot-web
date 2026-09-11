# Simple Boot Web

Simple Boot 管理端（Vue3 + Element Plus），配合 `simple-boot` 后端使用。

## 环境要求

- Node.js > 16.18.0
- 强制使用 pnpm > 8.6.0

## 快速开始

```bash
pnpm i
pnpm dev
```

本地默认读取 `.env` / `.env.local`，应用标题为 **Simple Boot**。按环境使用：

| 命令 | 说明 |
|------|------|
| `pnpm dev` | 本地开发（`env.local`） |
| `pnpm build:local` | 本地构建 |
| `pnpm ts:check` | TypeScript 检查 |

## 保留范围

登录、布局、系统管理（`system/*`）、基础设施（`infra/*`）、个人中心、首页与错误页。业务模块（商城 / CRM / ERP 等）已移除。

## 技术栈

Vue 3、Vite、Element Plus、TypeScript、Pinia、Vue Router、UnoCSS。

## 开发工具

推荐 VS Code，配合 Vue - Official、UnoCSS、ESLint、Prettier、i18n Ally 等插件。
