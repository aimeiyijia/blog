---
title: Hexo常用命令
comments: false
date: 2023-03-25 14:33:24
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 写作相关命令

### 新建分页

```powershell
hexo new page 名称
```

### 新建文章

```powershell
hexo new 名称 或 hexo n 名称
```

### 新建草稿

```powershell
hexo new draft 名称 或 hexo n draft 名称
```

### 草稿生成文章

```powershell
hexo publish 名称 或 hexo p 名称
```

### 草稿生成分页

```powershell
hexo publish page 名称 或 hexo p page 名称
```

## 操作命令

### 清除已生成文件

```powershell
hexo clean
```

### 运行本地服务器（预览）

```powershell
hexo s
```

### 运行本地服务器（预览草稿）

```powershell
hexo s --drafts
```

### 生成静态文件

```powershell
hexo g
```

### 部署到服务器

```powershell
hexo d
```

### 生成并部署文件

```powershell
hexo g -d 或 hexo d -g
```
