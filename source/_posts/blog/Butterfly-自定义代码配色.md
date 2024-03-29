---
title: Butterfly 自定义代码配色
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: 进阶教程
keywords: 'hexo,butterfly,主题,doc,教程,文档'
description: blog/Butterfly-自定义代码配色
cover: 
abbrlink: b37b5fe3
date: 2022-03-24 16:20:42
comments: false
---

在[Butterfly-安装文档-三-主题配置](http://butterfly.js.org/posts/4aa8abbe/#代码高亮主题)中已经介绍了如何使用blog/Butterfly-自定义代码配色。

这篇文章是使用blog/Butterfly-自定义代码配色的实例教程。

## Highlight

以使用`Kimbie dark`主题配色为例子

### 配置`hljs`为`true`

修改Hexo根目录下的`_config.yml`

```yaml
highlight:
 enable: true
 line_number: true
 auto_detect: false
 tab_replace:
 hljs: true
```

###  配置`highlight_theme`为`false`

修改`主题配置文件`

```yaml
highlight_theme: false
```

### 下载和修改CSS文件

在[Github](https://github.com/highlightjs/highlight.js/blob/master/src/styles/kimbie.dark.css)上找到这个CSS

在Hexo的根目录`source`文件夹下创立一个`self`文件夹，在`self`文件夹创建一个`Kimbiedark.css`文件

把Github上`Kimbie dark`的CSS代码复制到`Kimbiedark.css`去。（你也可以直接从Github上下载这个CSS）

**Kimbiedark.css**代码如下

```css
/*
    Name:     Kimbie (dark)
    Author:   Jan T. Sott
    License:  Creative Commons Attribution-ShareAlike 4.0 Unported License
    URL:      https://github.com/idleberg/Kimbie-highlight.js
*/

/* Kimbie Comment */
.hljs-comment,
.hljs-quote {
  color: #d6baad;
}

/* Kimbie Red */
.hljs-variable,
.hljs-template-variable,
.hljs-tag,
.hljs-name,
.hljs-selector-id,
.hljs-selector-class,
.hljs-regexp,
.hljs-meta {
  color: #dc3958;
}

/* Kimbie Orange */
.hljs-number,
.hljs-built_in,
.hljs-builtin-name,
.hljs-literal,
.hljs-type,
.hljs-params,
.hljs-deletion,
.hljs-link {
  color: #f79a32;
}

/* Kimbie Yellow */
.hljs-title,
.hljs-section,
.hljs-attribute {
  color: #f06431;
}

/* Kimbie Green */
.hljs-string,
.hljs-symbol,
.hljs-bullet,
.hljs-addition {
  color: #889b4a;
}

/* Kimbie Purple */
.hljs-keyword,
.hljs-selector-tag,
.hljs-function {
  color: #98676a;
}

.hljs {
  display: block;
  overflow-x: auto;
  background: #221a0f;
  color: #d3af86;
  padding: 0.5em;
}

.hljs-emphasis {
  font-style: italic;
}

.hljs-strong {
  font-weight: bold;
}
```

修改这个CSS文件为

```css
/*
    Name:     Kimbie (dark)
    Author:   Jan T. Sott
    License:  Creative Commons Attribution-ShareAlike 4.0 Unported License
    URL:      https://github.com/idleberg/Kimbie-highlight.js
*/

/* 新添加的内容
  ------------------------------------- 
  --hl-color                  代码框字体颜色 【必须】 (把下面.hljs的 color复制到这里来)
  --hl-bg                     代码框背景色 【必须】 (把下面.hljs的 background复制到这里来)
  --hltools-bg: #321a0f       代码框顶部工具栏背景色 【可选】(如果你关掉了 copy、lang 和 shrink,可不用配置这个）
  --hltools-color: #fff       代码框顶部工具栏字体颜色 【可选】(如果你关掉了 copy、lang 和 shrink,可不用配置这个）
  --hlnumber-bg: #221a0f      代码框行数背景色 【可选】(如果已经关掉 line_number,可以不用配置这个)
  --hlnumber-color: #fff      代码框行数字体颜色 【可选】 (如果已经关掉 line_number,可以不用配置这个)
  --hlscrollbar-bg: #d3af86   代码框滚动条颜色 【可选】（默认为主题主颜色）
  --hlexpand-bg: #d3af86      代码框底部展开背景色 【可选】(如果已经关掉 highlight_height_limit,可以不用配置这个)
*/

:root {
  --hl-color: #d3af86;
  --hl-bg: #221a0f;
  --hltools-bg: #321a0f;
  --hltools-color: #fff;
  --hlnumber-bg: #221a0f;
  --hlnumber-color: #fff;
  --hlscrollbar-bg: #d3af86;
  --hlexpand-bg: #d3af86;
}

/* Kimbie Comment */
.hljs-comment,
.hljs-quote {
  color: #d6baad;
}

/* Kimbie Red */
.hljs-variable,
.hljs-template-variable,
.hljs-tag,
.hljs-name,
.hljs-selector-id,
.hljs-selector-class,
.hljs-regexp,
.hljs-meta {
  color: #dc3958;
}

/* Kimbie Orange */
.hljs-number,
.hljs-built_in,
.hljs-builtin-name,
.hljs-literal,
.hljs-type,
.hljs-params,
.hljs-deletion,
.hljs-link {
  color: #f79a32;
}

/* Kimbie Yellow */
.hljs-title,
.hljs-section,
.hljs-attribute {
  color: #f06431;
}

/* Kimbie Green */
.hljs-string,
.hljs-symbol,
.hljs-bullet,
.hljs-addition {
  color: #889b4a;
}

/* Kimbie Purple */
.hljs-keyword,
.hljs-selector-tag,
.hljs-function {
  color: #98676a;
}

/* 更改的内容 把.hljs改为 #article-container figure.highlight .hljs *、
/* ------------------------------------- */
#article-container figure.highlight .hljs {
  display: block;
  overflow-x: auto;
  background: #221a0f;
  color: #d3af86;
  padding: 0.5em;
}

.hljs-emphasis {
  font-style: italic;
}

.hljs-strong {
  font-weight: bold;
}
```

### 引入文件

修改`主题配置文件`

```yaml
inject:
  head:
    - <link rel="stylesheet" href="/self/Kimbiedark.css">
```

### 运行Hexo

运行Hexo后，应该可以看到修改的效果

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-highlight-self-css.png)

## Prismjs

以使用`prism-duotone-light`主题配色为例子

###  配置`highlight_theme`为`false`

修改`主题配置文件`

```yaml
highlight_theme: false
```

### 下载和修改CSS文件

在[Github](https://github.com/PrismJS/prism-themes/blob/master/themes/prism-duotone-light.css)上找到这个CSS

在 Hexo 的根目录`source`文件夹下创立一个`self`文件夹，在`self`文件夹创建一个`duotone.css`文件

把Github上`prism-duotone-light`的 CSS 代码复制到``duotone.css`去。（你也可以直接从Github上下载这个CSS）

**prism-duotone-light**代码如下

```css
/*
Name:   Duotone Light
Author: Simurai, adapted from DuoTone themes for Atom (http://simurai.com/projects/2016/01/01/duotone-themes)

Conversion: Bram de Haan (http://atelierbram.github.io/Base2Tone-prism/output/prism/prism-base2tone-morning-light.css)
Generated with Base16 Builder (https://github.com/base16-builder/base16-builder)
*/

code[class*="language-"],
pre[class*="language-"] {
	font-family: Consolas, Menlo, Monaco, "Andale Mono WT", "Andale Mono", "Lucida Console", "Lucida Sans Typewriter", "DejaVu Sans Mono", "Bitstream Vera Sans Mono", "Liberation Mono", "Nimbus Mono L", "Courier New", Courier, monospace;
	font-size: 14px;
	line-height: 1.375;
	direction: ltr;
	text-align: left;
	white-space: pre;
	word-spacing: normal;
	word-break: normal;

	-moz-tab-size: 4;
	-o-tab-size: 4;
	tab-size: 4;

	-webkit-hyphens: none;
	-moz-hyphens: none;
	-ms-hyphens: none;
	hyphens: none;
	background: #faf8f5;
	color: #728fcb;
}

pre > code[class*="language-"] {
	font-size: 1em;
}

pre[class*="language-"]::-moz-selection, pre[class*="language-"] ::-moz-selection,
code[class*="language-"]::-moz-selection, code[class*="language-"] ::-moz-selection {
	text-shadow: none;
	background: #faf8f5;
}

pre[class*="language-"]::selection, pre[class*="language-"] ::selection,
code[class*="language-"]::selection, code[class*="language-"] ::selection {
	text-shadow: none;
	background: #faf8f5;
}

/* Code blocks */
pre[class*="language-"] {
	padding: 1em;
	margin: .5em 0;
	overflow: auto;
}

/* Inline code */
:not(pre) > code[class*="language-"] {
	padding: .1em;
	border-radius: .3em;
}

.token.comment,
.token.prolog,
.token.doctype,
.token.cdata {
	color: #b6ad9a;
}

.token.punctuation {
	color: #b6ad9a;
}

.token.namespace {
	opacity: .7;
}

.token.tag,
.token.operator,
.token.number {
	color: #063289;
}

.token.property,
.token.function {
	color: #b29762;
}

.token.tag-id,
.token.selector,
.token.atrule-id {
	color: #2d2006;
}

code.language-javascript,
.token.attr-name {
	color: #896724;
}

code.language-css,
code.language-scss,
.token.boolean,
.token.string,
.token.entity,
.token.url,
.language-css .token.string,
.language-scss .token.string,
.style .token.string,
.token.attr-value,
.token.keyword,
.token.control,
.token.directive,
.token.unit,
.token.statement,
.token.regex,
.token.atrule {
	color: #728fcb;
}

.token.placeholder,
.token.variable {
	color: #93abdc;
}

.token.deleted {
	text-decoration: line-through;
}

.token.inserted {
	border-bottom: 1px dotted #2d2006;
	text-decoration: none;
}

.token.italic {
	font-style: italic;
}

.token.important,
.token.bold {
	font-weight: bold;
}

.token.important {
	color: #896724;
}

.token.entity {
	cursor: help;
}

pre > code.highlight {
	outline: .4em solid #896724;
	outline-offset: .4em;
}

/* overrides color-values for the Line Numbers plugin
 * http://prismjs.com/plugins/line-numbers/
 */
.line-numbers .line-numbers-rows {
	border-right-color: #ece8de;
}

.line-numbers-rows > span:before {
	color: #cdc4b1;
}

/* overrides color-values for the Line Highlight plugin
 * http://prismjs.com/plugins/line-highlight/
 */
.line-highlight {
	background: rgba(45, 32, 6, 0.2);
	background: -webkit-linear-gradient(left, rgba(45, 32, 6, 0.2) 70%, rgba(45, 32, 6, 0));
	background: linear-gradient(to right, rgba(45, 32, 6, 0.2) 70%, rgba(45, 32, 6, 0));
}
```

修改这个CSS文件为

```css
/* 新添加的内容
  ------------------------------------- 
  --hl-color                  代码框字体颜色 【必须】 (把下面 pre[class*="language-"]的 color 复制到这里来)
  --hl-bg                     代码框背景色 【必须】 (把下面 pre[class*="language-"]的 background复制到这里来)
  --hltools-bg: #321a0f       代码框顶部工具栏背景色 【可选】(如果你关掉了 copy、lang 和 shrink,可不用配置这个）
  --hltools-color: #fff       代码框顶部工具栏字体颜色 【可选】(如果你关掉了 copy、lang 和 shrink,可不用配置这个）
  --hlnumber-bg: #221a0f      代码框行数背景色 【可选】(如果已经关掉 line_number,可以不用配置这个)
  --hlnumber-color: #fff      代码框行数字体颜色 【可选】 (如果已经关掉 line_number,可以不用配置这个)
  --hlscrollbar-bg: #d3af86   代码框滚动条颜色 【可选】（默认为主题主颜色）
  --hlexpand-bg: #d3af86      代码框底部展开背景色 【可选】(如果已经关掉 highlight_height_limit,可以不用配置这个)
*/

:root {
  --hl-color: #728fcb;
  --hl-bg: #faf8f5;
  --hltools-bg: xxxxxxx;
  --hltools-color: xxxxxxx;
  --hlnumber-bg: xxxxxxx;
  --hlnumber-color: xxxxxxxx;
  --hlscrollbar-bg: xxxxx;
  --hlexpand-bg: xxxxxxx
}


/* ------------------------------------- */

/* 这些可以刪除（可留着，如果有衝突，请刪除） */
/* ------------------------------------- */
code[class*="language-"],
pre[class*="language-"] {
	font-family: Consolas, Menlo, Monaco, "Andale Mono WT", "Andale Mono", "Lucida Console", "Lucida Sans Typewriter", "DejaVu Sans Mono", "Bitstream Vera Sans Mono", "Liberation Mono", "Nimbus Mono L", "Courier New", Courier, monospace;
	font-size: 14px;
	line-height: 1.375;
	direction: ltr;
	text-align: left;
	white-space: pre;
	word-spacing: normal;
	word-break: normal;

	-moz-tab-size: 4;
	-o-tab-size: 4;
	tab-size: 4;

	-webkit-hyphens: none;
	-moz-hyphens: none;
	-ms-hyphens: none;
	hyphens: none;
	background: #faf8f5;
	color: #728fcb;
}

pre > code[class*="language-"] {
	font-size: 1em;
}

pre[class*="language-"]::-moz-selection, pre[class*="language-"] ::-moz-selection,
code[class*="language-"]::-moz-selection, code[class*="language-"] ::-moz-selection {
	text-shadow: none;
	background: #faf8f5;
}

pre[class*="language-"]::selection, pre[class*="language-"] ::selection,
code[class*="language-"]::selection, code[class*="language-"] ::selection {
	text-shadow: none;
	background: #faf8f5;
}

/* Code blocks */
pre[class*="language-"] {
	padding: 1em;
	margin: .5em 0;
	overflow: auto;
}

/* Inline code */
:not(pre) > code[class*="language-"] {
	padding: .1em;
	border-radius: .3em;
}
/* ------------------------------------- */
/* 到这里为止，可以刪除 */

.token.comment,
.token.prolog,
.token.doctype,
.token.cdata {
	color: #b6ad9a;
}

.token.punctuation {
	color: #b6ad9a;
}

.token.namespace {
	opacity: .7;
}

.token.tag,
.token.operator,
.token.number {
	color: #063289;
}

.token.property,
.token.function {
	color: #b29762;
}

.token.tag-id,
.token.selector,
.token.atrule-id {
	color: #2d2006;
}

code.language-javascript,
.token.attr-name {
	color: #896724;
}

code.language-css,
code.language-scss,
.token.boolean,
.token.string,
.token.entity,
.token.url,
.language-css .token.string,
.language-scss .token.string,
.style .token.string,
.token.attr-value,
.token.keyword,
.token.control,
.token.directive,
.token.unit,
.token.statement,
.token.regex,
.token.atrule {
	color: #728fcb;
}

.token.placeholder,
.token.variable {
	color: #93abdc;
}

.token.deleted {
	text-decoration: line-through;
}

.token.inserted {
	border-bottom: 1px dotted #2d2006;
	text-decoration: none;
}

.token.italic {
	font-style: italic;
}

.token.important,
.token.bold {
	font-weight: bold;
}

.token.important {
	color: #896724;
}

.token.entity {
	cursor: help;
}

pre > code.highlight {
	outline: .4em solid #896724;
	outline-offset: .4em;
}

/* overrides color-values for the Line Numbers plugin
 * http://prismjs.com/plugins/line-numbers/
 */
.line-numbers .line-numbers-rows {
	border-right-color: #ece8de;
}

.line-numbers-rows > span:before {
	color: #cdc4b1;
}

/* overrides color-values for the Line Highlight plugin
 * http://prismjs.com/plugins/line-highlight/
 */
.line-highlight {
	background: rgba(45, 32, 6, 0.2);
	background: -webkit-linear-gradient(left, rgba(45, 32, 6, 0.2) 70%, rgba(45, 32, 6, 0));
	background: linear-gradient(to right, rgba(45, 32, 6, 0.2) 70%, rgba(45, 32, 6, 0));
}
```

### 引入文件

修改`主题配置文件`

```yaml
inject:
  head:
    - <link rel="stylesheet" href="/self/duotone.css">
```

### 运行Hexo

运行Hexo后，应该可以看到修改的效果

![image-20200831000324474](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-custom-code-color-prismjs.png)