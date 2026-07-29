# 首页品牌名称与 Logo 显示规范

> **分类**：设计规范 / 前端展示
> **标签**：防爆电机证书查询系统、首页、品牌名称、Logo展示、皖南电机、CCC、CNEX
> **适用范围**：`防爆电机证书快速查询系统`（YBX4 系列，GitHub Pages 部署）
> **负责人**：待补充（建议指定：前端维护人 / 品牌负责人）
> **更新时间**：2026-07-29
> **关联资料**：[index.html](../index.html)、[images/](../images/)

---

## 一、背景

系统原首页标题为「防爆电机证书快速查询模块」，未体现品牌归属。2026-07-29 产品方确认该查询系统归属于**皖南电机**品牌，要求：

1. 首页标题冠以「皖南电机」前缀；
2. 将 CCC 认证标识、国家防爆（CNEX）标识在首页 header 右侧**并排、实心展示**，强化「双证齐全」的专业感。

本次改动已上线（commit `52f2f75`，GitHub Pages 自动发布）。

## 二、当前规范（有效）

### 2.1 标题文案

| 位置 | 文案 | 代码位置 |
|------|------|----------|
| 页面 `<title>` | `皖南电机防爆电机证书快速查询 · YBX4系列` | `index.html` 第 9 行 |
| 首页 `<h1>` 主标题 | `🛡️ 皖南电机防爆电机证书<span class="tag">快速查询</span>模块` | `index.html` 第 235 行 |

> 其中「快速查询」通过 `<span class="tag">` 套用主题橙色（`--accent`），形成视觉重点。

### 2.2 Logo 展示规范

| 项目 | 规范值 |
|------|--------|
| 左侧 Logo | CCC 认证标识 → `images/ccc-logo.jpg` |
| 右侧 Logo | 国家防爆 CNEX 标识 → `images/cnex-logo.png` |
| 展示方式 | header 内右侧并排显示，不透明、不遮挡标题 |
| 容器 | `<div class="header-logos">` 内用 `<img>` 标签 |
| PC 端高度 | CCC `64px`；CNEX `58px` |
| PC 端间距 | 两个 logo 之间 `gap: 18px` |
| 布局 | `header` 使用 `display:flex; justify-content:space-between; align-items:center` |
| 手机端（≤600px） | logo 移至标题上方（`order:-1`），高度 CCC `40px`、CNEX `36px`，左对齐 |

### 2.3 资源文件

| 文件 | 说明 | 来源 |
|------|------|------|
| `images/ccc-logo.jpg` | CCC 认证标识（用户上传） | 微信图片 20260729164253 |
| `images/cnex-logo.png` | 国家防爆 CNEX 标识（用户上传） | 用户上传 |

## 三、修改指引（供后续改版参考）

若需调整品牌名称、Logo 或展示样式，按以下位置修改 `index.html`：

- **改标题文字**：搜索 `皖南电机防爆电机证书快速查询`，同步修改 `<title>` 与 `<h1>` 两处。
- **换/加 Logo**：将图片放入 `images/`，修改 `<div class="header-logos">` 内的 `<img src>`。
- **调 Logo 大小/间距**：改 `.header-logos img` 的 `height` 与 `.header-logos` 的 `gap`。
- **调位置**：改 `header` 的 `justify-content`（如改为 `flex-start` 左对齐）或调整 `.header-logos` 的 `margin-left`。

> 注意：GitHub Pages 从 `main` 分支根目录发布，`git push` 后一般 1–2 分钟生效；浏览器需强制刷新（`Ctrl+F5` / `Cmd+Shift+R`）以清缓存。

## 四、待补充 / 提醒

- [ ] **负责人**：本文档「负责人」字段待补充，建议指定前端维护人或品牌负责人。
- [ ] **Logo 版权**：CCC、CNEX 为认证机构标识，商用展示前请确认授权范围。
- [ ] **多系列扩展**：当前标题含「YBX4系列」，若后续接入 YBX3/YBX5 等其他系列，标题文案需同步评估是否保留系列后缀。

## 五、相关链接

- 线上地址：https://wxq5800676.github.io/cert-query/
- 代码仓库：https://github.com/wxq5800676/cert-query
- 应用版本：`v20250122.07`
- 相关提交：`52f2f75`
