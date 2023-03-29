---
title: Git分支创建与提交规范
comments: false
abbrlink: ff6002ac
date: 2023-03-29 20:05:15
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 分支命名规范

- 需求：`feature_` 开头，接需求编号，例：`feature_2021-917`

- 设计：`design_` 开头，接设计编号，例：`design_2021-127`

- 同类需求：`feature_ `开头，接需求编号,编号之间用&连接，例：`feature_2021-917&2021-918`

- 同类设计：`design_` 开头，接设计编号,编号之间用&连接，例：`design_2021-917&2021-918`

- 测试：`test_` 开头，接编号，例：`test_sass`

- 版本：`release_ `开头，接版本编号，例：`release_2.3`

- 补丁：`_patch` 结尾，前接`release_版本编号`，例：`release_2.3_patch1/release_2.3-patch1`

## git 提交规范

#### git 提交类型

- `feat：`       - 需求类变更

- `des：`        - 设计类变更

- `fix：`           - 修复 bug

- `docs ：`      - 文档注释或修改了文档

- `style：`       - 代码格式(不影响代码运行的变动)，例如格式化、缺少分号等等

- `refactor：` - 重构(原有功能优化)

- `perf：`       - 性能优化

- `test：`- 增加测试

- `chore：` - 构建过程或辅助工具的变动

- `revert：` - 回退

- `build：`- 打包

#### git 提交格式
> 提交类型(需求或设计编号)：业务名称 + 具体操作描述

例如编号为2021-127的需求提交：`feat(2021-127)： 增加批量转账说明和查询添加下拉选项`
