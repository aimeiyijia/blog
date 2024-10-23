---
title: UI规范-web
comments: false
abbrlink: 162285a8
date: 2023-04-19 20:05:31
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 尺寸规范

#### 字号

#### 行高

## 文字规范

#### 字号

| 层级                                           | 字体大小                                 |
| ---------------------------------------------- | ---------------------------------------- |
| <span style="font-size: 12px">辅助文字<span>   | <span style="font-size: 12px">12px<span> |
| <span style="font-size: 13px">正文（小）<span> | <span style="font-size: 13px">13px<span> |
| <span style="font-size: 14px">正文<span>       | <span style="font-size: 14px">14px<span> |
| <span style="font-size: 16px">小标题<span>     | <span style="font-size: 16px">16px<span> |
| <span style="font-size: 18px">标题<span>       | <span style="font-size: 18px">18px<span> |
| <span style="font-size: 20px">主标题<span>     | <span style="font-size: 20px">20px<span> |



#### 行高

| 层级   | 描述             |
| ------ | ---------------- |
| 无行高 | line-height: 1   |
| 紧凑   | line-height: 1.3 |
| 常规   | line-height: 1.5 |
| 宽松   | line-height: 1.7 |



## 色彩规范

#### 主要颜色

| 名称                                           | 值                                           | 说明                                                 |
| ---------------------------------------------- | -------------------------------------------- | ---------------------------------------------------- |
| <span style="color: #409EFF">主色<span>        | <span style="color: #409EFF">#409EFF<span>   | 产品主色调                                           |
| <span style="color: #67C23A">成功色<span>      | <span style="color: #67C23A">#67C23A<span>   | 操作成功、接口请求成功等提示色                       |
| <span style="color: #E6A23C">警告色<span>      | <span style="color: #E6A23C">#E6A23C<span>   | 操作未成功、接口未请求成功等提示色，一般伴随提示信息 |
| <span style="color: #F56C6C">危险色<span>      | <span style="color: #F56C6C">#F56C6C<span>   | 危险操作之前的警告色                                 |
| <span style="color: #909399F">一般提示色<span> | <span style="color: #909399F">#909399F<span> |                                                      |

#### 中性色

文本、背景、边框颜色

<div style="background-color: #303133;color: white;font-size: 14px;width: 70px;text-align: center"> 主要文字 #303133 </div>

<div style="background-color: #606266;color: white;font-size: 14px;width: 70px;text-align: center"> 常规文字 #606266 </div>

<div style="background-color: #909399;color: white;font-size: 14px;width: 70px;text-align: center"> 次要文字 #909399 </div>

<div style="background-color: #C0C4CC;color: white;font-size: 14px;width: 70px;text-align: center"> 占位文字 #C0C4CC </div>

<div style="background-color: #303133;color: white;font-size: 14px;width: 70px;text-align: center"> 主要文字 #303133 </div>

<div style="background-color: #303133;color: white;font-size: 14px;width: 70px;text-align: center"> 主要文字 #303133 </div>

## 阴影规范

## 圆角规范

## 布局规范

## 图标规范

## 交互提示规范

1. 可点击元素，鼠标移上去应显示为手型的样式（cursor:pointer;）
2. 数据加载、操作过程中需展示 loading 提示
3. 敏感性操作需进行二次操作，如删除、资金转账等

## 组件规范

#### 按钮

#### 列表

1. 针对“身份证号码”、“手机号码”、“地址”等用户敏感信息都应该中间用\*号隐去，如：XX\*\*\*XX
2. 表格需有边框、单元格居中
3. 除默认配置外，表格分页指示器须有 **共 0 页 / 0 条数据**

#### 表单

好的，以下是一份简单的前端 UI 规范文档：

# 前端 UI 规范文档

## 设计原则和指南

1. 保持简洁：界面应该简单明了，不要使用过多的装饰和复杂的图形。
2. 一致性：保持界面元素的一致性，包括颜色、字体、按钮样式等。
3. 可用性：界面应该易于使用，用户可以快速找到他们需要的功能。
4. 可访问性：界面应该易于访问，包括键盘导航和适当的文本标签。
5. 响应式设计：界面应该适应不同的设备和屏幕尺寸。
6. 可维护性：界面应该易于维护和修改，包括清晰的代码结构和注释。

## 样式指南

1. 命名规则：使用有意义的类名和 ID，不要使用无意义的缩写或单词。
2. 注释：在 CSS 中添加注释，解释代码的作用和意图。
3. 代码结构：使用缩进和空格来组织 CSS 代码，使其易于阅读和修改。
4. 媒体查询：使用媒体查询来实现响应式设计，而不是使用 JavaScript。
5. 浏览器兼容性：使用 CSS 前缀来保证在不同的浏览器上都能正常运行。

## HTML 标记指南

1. 语义化：使用语义化的 HTML 标记来描述页面的结构和内容。
2. 结构化：使用合适的标记来组织页面的结构，例如使用标题标记来表示标题。
3. 可访问性：使用适当的文本标签和属性来增加页面的可访问性。
4. 无障碍性：使用无障碍性标准来确保页面可以被屏幕阅读器等辅助技术使用。

## 图片和图标指南

1. 格式：使用合适的图像格式，例如 JPEG、PNG 或 SVG。
2. 大小：优化图像大小，以减少页面加载时间。
3. 分辨率：使用合适的分辨率，以确保图像在不同的设备上都能正常显示。
4. 图标：使用矢量图标，以便在不同的尺寸和分辨率下都能正常显示。

## 响应式设计指南

1. 布局：使用流式布局，以适应不同的屏幕尺寸。
2. 图像：使用响应式图像，以适应不同的屏幕分辨率。
3. 字体：使用相对单位（例如 em 或 rem）来设置字体大小，以适应不同的屏幕尺寸。
4. 媒体查询：使用媒体查询来确定不同屏幕尺寸的样式。

## 浏览器兼容性指南

1. 浏览器前缀：使用浏览器前缀来确保在不同的浏览器上都能正常运行。
2. 测试：在不同的浏览器和设备上测试页面，以确保它们在各种情况下都能正常运行。
3. 特性检测：使用 JavaScript 特性检测来检测浏览器是否支持某些功能。

## 性能优化指南

1. 压缩代码：使用压缩工具来减少代码大小。
2. 缓存：使用浏览器缓存来减少页面加载时间。
3. 减少 HTTP 请求：减少页面中的 HTTP 请求，以加快页面加载速度。
4. 图像优化：优化图像大小和分辨率，以减少页面加载时间。

以上是一份简单的前端 UI 规范文档，可以根据具体项目的需要进行修改和补充。

## 交互规范

数据加载过程中需提示加载状态
较长时间的渲染、操作需增加提示