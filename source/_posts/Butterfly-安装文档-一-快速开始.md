---
title: Butterfly 安装文档(一) 快速开始
date: 2023-03-24 13:36:42
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: Docs文档
keywords: "hexo,butterfly,主题,doc,教程,文档"
description: Butterfly安装文档-快速开始
cover: 
abbrlink: 21cfbf15
sticky: 100
comments: false
---

{% note green 'fas fa-rocket' %}

📚 文档目录

{% post_link Butterfly-安装文档-一-快速开始 ' 🚀 快速开始' %} - {% post_link Butterfly-安装文档-二-主题页面 ' 📑 主题页面' %} - {% post_link Butterfly-安装文档-三-主题配置-1 ' 🛠 主题配置-1' %} - {% post_link Butterfly-安装文档-四-主题配置-2 ' ⚔️ 主题配置-2' %} - {% post_link Butterfly-安装文档-五-进阶教程 ' ⚡️ 进阶教程' %}

{% endnote %}

---

## 安装

{% tabs butterfly-install %}

<!-- tab Git安装 (Github) @fab fa-github-square -->

**稳定版【建议】**

在你的 Hexo 根目录里

```powershell
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
```

**测试版**

> 测试版可能存在 bug，追求稳定的请安装稳定版

如果想要安装比较新的 dev 分支，可以

```powershell
git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
```

{% note info %}

升级方法：在主题目录下，运行 `git pull`

{% endnote %}

<!-- endtab -->

<!-- tab Git安装 (Gitee) @fab fa-git-square -->

**稳定版【建议】**

在你的 Hexo 根目录里

```powershell
git clone -b master https://gitee.com/immyw/hexo-theme-butterfly.git themes/butterfly
```

**测试版**

> 测试版可能存在 Bugs，追求稳定的请安装稳定版

如果想要安装比较新的 dev 分支，可以

```powershell
git clone -b dev https://gitee.com/immyw/hexo-theme-butterfly.git themes/butterfly
```

{% note info %}

升级方法：在主题目录下，执行`git pull`

{% endnote %}

<!-- endtab -->

<!-- tab npm安装@fab fa-npm -->

> 此方法只支持 Hexo 5.0.0 以上版本
>
> **_通过 npm 安装并不会在 themes 里生成主题文件夹，而是在 node_modules 里生成_**

在你的 Hexo 根目录里

```powershell
npm i hexo-theme-butterfly
```

{% note info %}

升级方法：在 Hexo 根目录下，执行 `npm update hexo-theme-butterfly`

{% endnote %}

<!-- endtab -->

{% endtabs %}

## 应用主题

修改 Hexo 根目录下的 `_config.yml`，把主题改为`butterfly`

```yaml
theme: butterfly
```

## 安装插件

如果你没有 pug 以及 stylus 的渲染器，请下载安装：

```powershell
npm install hexo-renderer-pug hexo-renderer-stylus --save
```

## 升级建议

{% note blue 'fas fa-train' %}

升级完成后，请到 Github 的 [Releases](https://github.com/jerryc127/hexo-theme-butterfly/releases) 界面 或者 [文档七](https://butterfly.js.org/posts/198a4240/) 查看新版的更新内容。

里面有标注 `_config` 文件的变更内容（如有），请根据实际情況更新你的配置内容。

{% endnote %}

为了减少升级主题后带来的不便，请使用以下方法（**建议，可以不做**）。

在 hexo 的根目录创建一个文件 `_config.butterfly.yml`，并把**主题**目录的 `_config.yml` **内容**复制到 `_config.butterfly.yml` 去。( **注意: 复制的是主题的 `_config.yml` ,而不是 hexo 的 `_config.yml`**)

> **注意：** 不要把主题目录的 `_config.yml` 刪掉

> **注意：** 以后只需要在 `_config.butterfly.yml`进行配置就行。
> 如果使用了 `_config.butterfly.yml`， 配置主题的 `_config.yml` 将不会有效果。

Hexo 会自动**合并**主题中的`_config.yml`和 `_config.butterfly.yml`里的配置，如果存在同名配置，会使用`_config.butterfly.yml`的配置，其优先级较高。

![image-20200805191531090](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-docs-install-suggestion-1.png)

{% btn '/posts/dc584b87/',📑 Butterfly 安装文档(二) 主题页面,far fa-hand-point-right,block right larger %}
