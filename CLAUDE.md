# CLAUDE.md

此文件为 Claude Code (claude.ai/code) 在此仓库中工作时提供指导。

## 项目概述

这是一个基于 Hugo 的个人博客网站，使用 Anatole 主题。网站部署在 `wenzisay.com`，包含中文博客文章，并按分类、标签和系列进行组织。

## 开发命令

### Hugo 命令
- `hugo server` - 启动开发服务器，支持热重载
- `hugo build` - 构建静态网站到 `public/` 目录
- `hugo new content/posts/new-post.md` - 创建新博客文章
- `hugo new content/about/new-page.md` - 创建新页面

### 内容创建
- 文章创建在 `content/posts/` 目录中
- 使用原型模板保持一致的 frontmatter 格式：`content/posts/my-first-post.md:1`
- 关于页面位于 `content/about.md`

## 架构与结构

### 关键文件和目录
- `hugo.toml` - 主要配置文件，包含主题、语言和 Google Analytics 设置
- `content/` - 所有 Markdown 内容文件
  - `posts/` - 使用 TOML frontmatter 的博客文章
  - `about.md` - 使用 YAML frontmatter 的关于页面
- `static/` - 静态资源（图片等）
- `public/` - 生成的静态网站（构建输出）
- `themes/` - 主题文件（Anatole 和 no-style-please 主题）

### 主题配置
- 当前使用 Anatole 主题 (`hugo.toml:5`)
- 可用替代主题：no-style-please
- 主题功能：暗色模式、多语言支持、分析、评论

### 内容组织
- **文章**：位于 `content/posts/`，使用 TOML frontmatter 格式
- **分类**：使用 `categories` 分类法（如 "呓语"）
- **标签**：使用 `tags` 分类法进行内容标记
- **导航**：在 `config/_default/menus.toml` 中配置

### Frontmatter 格式
网站使用混合 frontmatter 格式：
- 文章：TOML 格式（`+++` 分隔符）
- 页面：YAML 格式（`---` 分隔符）

### 主要功能
- Google Analytics 集成 (G-4MQXG1J2GX)
- 使用 Pygments 的语法高亮
- KaTeX 数学支持
- 多语言设置（中文为主）
- SEO 优化，支持 Open Graph 和 Twitter Cards

## 内容指南

### 文章 Frontmatter (TOML 格式)
```toml
+++
date = '2025-08-06T21:00:11+08:00'
draft = false
title = '文章标题'
categories = ['分类名称']
+++
```

### 页面 Frontmatter (YAML 格式)
```yaml
---
title: "页面标题"
date: 2024-01-01
draft: false
---
```

### 静态资源
- 头像图片在 `static/images/` 中
- 在模板中引用为 `/images/profile.jpg`
- 通过主题包含 FontAwesome 图标

## 构建与部署

网站构建到 `public/` 目录，似乎通过静态主机托管部署。当前 git 状态显示 `public/` 目录中有很多修改过的文件，表明最近的构建或更新。

## 注意事项

- Hugo 版本应支持本地化日期（0.87.0+）
- 主题支持亮色和暗色模式
- 中文是主要内容语言
- 内容混合使用不同的 frontmatter 格式 - 创建新内容时保持一致性