---
title: Butterfly 安装文档(三) 主题配置-1
date: 2022-03-24 14:48:42
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: Docs文档
keywords: "hexo,butterfly,主题,doc,教程,文档"
description: Butterfly安装文档-主题配置
cover: 
abbrlink: 4aa8abbe
comments: false
---

{% note green 'fas fa-rocket' %}
📚 文档目录

{% post_link Butterfly-安装文档-一-快速开始 ' 🚀 快速开始' %} - {% post_link Butterfly-安装文档-二-主题页面 ' 📑 主题页面' %} - {% post_link Butterfly-安装文档-三-主题配置-1 ' 🛠 主题配置-1' %} - {% post_link Butterfly-安装文档-四-主题配置-2 ' ⚔️ 主题配置-2' %} - {% post_link Butterfly-安装文档-五-进阶教程 ' ⚡️ 进阶教程' %}

{% endnote %}

---

## 语言

修改站点配置文件 `_config.yml`

默认语言是 en

主题支持三种语言

- default(en)
- zh-CN (简体中文)
- zh-TW (繁体中文)

## 网站资料

修改网站各种资料，例如标题、副标题和邮箱等个人资料，请修改博客根目录的`_config.yml`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/20191120000444.png)

## 导航菜单

修改 `主题配置文件`

```yaml
Home: / || fas fa-home
Archives: /archives/ || fas fa-archive
Tags: /tags/ || fas fa-tags
Categories: /categories/ || fas fa-folder-open
List||fas fa-list:
  Music: /music/ || fas fa-music
  Movie: /movies/ || fas fa-video
Link: /link/ || fas fa-link
About: /about/ || fas fa-heart
```

必须是 `/xxx/`，后面`||`分开，然后写图标名。

如果不希望显示图标，图标名可不写。

默认子目录是展开的，如果你想要隐藏，在子目录里添加 `hide` 。

```yaml
List||fas fa-list||hide:
  Music: /music/ || fas fa-music
  Movie: /movies/ || fas fa-video
```

**注意：** 导航的文字可自行更改

例如：

```markdown
menu:
首页: / || fas fa-home
时间轴: /archives/ || fas fa-archive
标签: /tags/ || fas fa-tags
分类: /categories/ || fas fa-folder-open
清单||fa fa-heartbeat:
音乐: /music/ || fas fa-music
照片: /Gallery/ || fas fa-images
电影: /movies/ || fas fa-video
友链: /link/ || fas fa-link
关于: /about/ || fas fa-heart
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-menu.png)

## 导航栏设置

主题配置文件中

```yaml
nav:
  logo: #image
  display_title: true
  fixed: false # fixed navigation bar
```

| 参数          | 解释                                    |
| ------------- | --------------------------------------- |
| logo          | 网站的 logo，支持图片，直接填入图片链接 |
| display_title | 是否显示网站标题，填写 true 或者 false  |
| fixed         | 是否固定状态栏，填写 true 或者 false    |

## 代码

{% note info %}

代码块中的所有功能只适用于 Hexo 自带的代码渲染

如果使用第三方的渲染器，不一定会有效

{% endnote %}

### 代码高亮主题

{% tabs highlight-theme %}

<!-- tab 默认主题 -->

`Butterfly` 支持 6 种代码高亮样式：

- darker
- pale night
- light
- ocean
- mac
- mac light

修改 `主题配置文件`

```yaml
highlight_theme: light
```

> darker

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-darker.png)

> pale night

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-pale-night.png)

> light

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-light.png)

> ocean

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-highlight-ocean.png)

> mac

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-highlight-mac.png)

> mac light

![image-20200731175026827](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-mac-light.png)

<!-- endtab -->

<!-- tab 自定义主题 -->

主题从 3.0 开始，支持使用自定义的代码颜色。

如何自定义主题，请查看下面这篇文章。

{% post_link Butterfly-自定义代码配色 ' Butterfly-自定义代码配色' %}

<!-- endtab -->

{% endtabs %}

### 代码复制

主题支持代码复制功能

修改 `主题配置文件`

```yaml
highlight_copy: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-copy.png)

### 代码框展开/关闭

在默认情況下，代码框自动展开，可设置是否所有代码框都关闭状态，点击`>`可展开代码

- true 全部代码框不展开，需点击`>`打开
- false 代码框展开，有`>`点击按钮
- none 不显示`>`按钮

修改 `主题配置文件`

```yaml
highlight_shrink: true #代码框不展开，需点击 '>' 打开
```

{% note info %}

你也可以在 post/page 页对应的 markdown 文件 front-matter 添加 highlight_shrink 来独立配置。

当**主题配置文件中**的 `highlight_shrink `设为 true 时，可在 front-matter 添加`highlight_shrink: false`来单独配置文章展开代码框。

当**主题配置文件中**的 `highlight_shrink `设为 false 时，可在 front-matter 添加`highlight_shrink: true`来单独配置文章收缩代码框。

{% endnote %}

`highlight_shrink: true`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-highlight-shrink-true.png)

`highlight_shrink: false`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-highlight-shrink-false.png)

`highlight_shrink: none`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-highlight-shirk-none.png)

### 代码换行

在默认情況下，Hexo 在编译的时候不会实现代码自动换行。如果你不希望在代码块的区域里有橫向滚动条的话，那么你可以考虑开启这个功能。

修改 `主题配置文件`

```yaml
code_word_wrap: true
```

如果你是使用 highlight 渲染，需要找到你站点的 Hexo 配置文件`_config.yml`，将`line_number`改成`false`:

```yaml
highlight:
  enable: true
  line_number: false # <- 改这里
  auto_detect: false
  tab_replace:
```

如果你是使用 prismjs 渲染，需要找到你站点的 Hexo 配置文件`_config.yml`，将`line_number`改成`false`:

```yaml
prismjs:
  enable: false
  preprocess: true
  line_number: false # <- 改这里
  tab_replace: ""
```

> 设置`code_word_wrap`之前:

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-word-wrap-before.png)

> 设置`code_word_wrap`之后:

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-code-word-wrap-after.png)

### 代码高度限制

> 3.7.0 及以上支持

可配置代码高度限制，超出的部分会隐藏，并显示展开按钮。

```yaml
highlight_height_limit: false # unit: px
```

注意：

1. 单位是 `px`，直接添加数字，如 200

2. 实际限制高度为 `highlight_height_limit + 30 px` ，多增加 30px 限制，目的是避免代码高度只超出 highlight_height_limit 一点时，出现展开按钮，展开没内容。

3. 不适用于隐藏后的代码块（ css 设置 display: none）

![hexo-theme-butterfly-docs-highlight-heigh-limit](https://file.crazywong.com/gh/jerryc127/CDN@m2/img/hexo-theme-butterfly-docs-highlight-heigh-limit.gif)

## 社交图标

Butterfly 支持 [font-awesome v6](https://fontawesome.com/icons?from=io)图标.

书写格式 `图标名：url || 描述性文字`

```yaml
social:
  fab fa-github: https://github.com/xxxxx || Github
  fas fa-envelope: mailto:xxxxxx@gmail.com || Email
```

图标名可在这寻找

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-fontawesome.png)

PC:

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-social-icon-pc.png)

Mobile:

![1560603353743](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-socila-icon-mobile.png)

## 主页文章筛选(自动筛选和文章页 description)

因为主题 UI 的关係，`主页文章筛选`只支持`自动筛选`和`文章页description`。

在`butterfly`里，有四种可供选择

1. **description：** 只显示 description
2. **both：** 优先选择 description，如果没有配置 description，则显示自动筛选的内容
3. **auto_excerpt：**只显示自动筛选
4. **false：** 不显示文章内容

修改 `主题配置文件`

```yaml
index_post_content:
  method: 3
  length: 500 # if you set method to 2 or 3, the length need to config
```

`description`在 front-matter 里添加

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-description.png)

## 顶部图

{% note info %}

如果不要显示顶部图，可直接配置 `disable_top_img: true`

{% endnote %}

{% note primary %}

顶部图的获取顺序，如果都没有配置，则不显示顶部图。

1. 页面顶部图的获取顺序：

   `各自配置的 top_img` > `配置文件的 default_top_img `

2. 文章页顶部图的获取顺序：

   `各自配置的 top_img` > `cover` > `配置文件的 default_top_img `

{% endnote %}

配置中的值：

| 配置             | 解释                                                                |
| ---------------- | ------------------------------------------------------------------- |
| index_img        | 主页的 top_img                                                      |
| default_top_img  | 默认的 top_img，当页面的 top_img 没有配置时，会显示 default_top_img |
| archive_img      | 归档页面的 top_img                                                  |
| tag_img          | tag 子页面 的 默认 top_img                                          |
| tag_per_img      | tag 子页面的 top_img，可配置每个 tag 的 top_img                     |
| category_img     | category 子页面 的 默认 top_img                                     |
| category_per_img | category 子页面的 top_img，可配置每个 category 的 top_img           |

其它页面 （tags/categories/自建页面）和 文章页 的 `top_img` ，请到对应的 md 页面设置`front-matter`中的`top_img`

以上所有的 top_img 可配置以下值

> **3.2.0 以下**版本的配置只支持
>
> - 留空，true 和 false - 显示默认的颜色
> - img 链接 - 显示所配置的图片

| 配置的值                                                                                                                                       | 效果                                                                                             |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| 留空                                                                                                                                           | 显示默认的 top_img（如有），否则显示默认的颜色<br>（文章页 top_img 留空的话，会显示 cover 的值） |
| img 链接                                                                                                                                       | 图片的链接，显示所配置的图片                                                                     |
| 颜色(<br>HEX 值 - \#0000FF<br>RGB 值 - rgb(0,0,255)<br>颜色单詞 - orange<br>渐变色 - linear-gradient( 135deg, #E2B0FF 10%, #9F44D3 100%)<br>） | 对应的颜色                                                                                       |
| transparent                                                                                                                                    | 透明                                                                                             |
| false                                                                                                                                          | 不显示 top_img                                                                                   |

`tag_per_img` 和 `category_per_img` 是 3.2.0 新增的内容，可对 tag 和 category 进行单独的配置

并不推荐为每个 tag 和每个 category 都配置不同的顶部图，因为配置太多会拖慢生成速度

```yaml
tag_per_img：
  aplayer: https://xxxxxx.png
  android: ddddddd.png

category_per_img：
  随想: hdhdh.png
  推荐: ddjdjdjd.png
```

> top_img: false

![image-20200924224536013](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-page-top-img-false.png)

![image-20201027210949089](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-post-top-img-false-new.png)

> top_img: orange

![image-20200924225024153](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-top-img-orange.png)

> top_img: 'linear-gradient(20deg, #0062be, #925696, #cc426e, #fb0347)'

![image-20200924225300934](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-top-img-color.png)

## 文章置顶

【推荐】[`hexo-generator-index`](https://github.com/hexojs/hexo-generator-index)从 2.0.0 开始，已经支持文章置顶功能。你可以直接在文章的`front-matter`区域里添加`sticky: 1`属性来把这篇文章置顶。数值越大，置顶的优先级越大。

## 文章封面

文章的 markdown 文档上,在 `Front-matter` 添加 `cover` ,并填上要显示的图片地址。

如果不配置 `cover`,可以设置显示默认的 cover。

如果不想在首页显示 cover, 可以设置为 `false`。

> 文章封面的获取顺序 `Front-matter 的 cover` > `配置文件的 default_cover` > `false`

修改 `主题配置文件`

```yaml
cover:
  # 是否显示文章封面
  index_enable: true
  aside_enable: true
  archives_enable: true
  # 封面显示的位置
  # 三个值可配置 left , right , both
  position: both
  # 当没有设置cover时，默认的封面显示
  default_cover:
```

| 参数            | 解释                                                                                                                        |
| --------------- | --------------------------------------------------------------------------------------------------------------------------- |
| index_enable    | 主页是否显示文章封面图                                                                                                      |
| aside_enable    | 侧栏是否显示文章封面图                                                                                                      |
| archives_enable | 归档页面是否显示文章封面图                                                                                                  |
| position        | 主页卡片文章封面的显示位置<br />- left：全部显示在左边<br />- right：全部显示在右边<br />- both：封面位置以左右左右轮流显示 |
| default_cover   | 默认的 cover, 可配置图片链接/颜色/渐变色等                                                                                  |

当配置多张图片时,会随机选择一张作为 cover.此时写法应为

```yaml
default_cover:
  - https://file.crazywong.com/gh/jerryc127/CDN@latest/cover/default_bg.png
  - https://file.crazywong.com/gh/jerryc127/CDN@latest/cover/default_bg2.png
  - https://file.crazywong.com/gh/jerryc127/CDN@latest/cover/default_bg3.png
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-cover.png)
![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-cover-show.png)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-cover-false.png)

> left

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-cover-left.png)

> right

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-cover-right.png)

> both

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-cover-both.png)

## 文章页相关配置

### 文章 meta 显示

这个选项是用来显示文章的相关信息的。

修改 `主题配置文件`

```yaml
post_meta:
  page:
    date_type: both # created or updated or both 主页文章日期是创建日或者更新日或都显示
    date_format: relative # date/relative 显示日期还是相对日期
    categories: true # true or false 主页是否显示分类
    tags: true # true or false 主页是否显示标签
    label: true # true or false 显示描述性文字
  post:
    date_type: both # created or updated or both 文章页日期是创建日或者更新日或都显示
    date_format: relative # date/relative 显示日期还是相对日期
    categories: true # true or false 文章页是否显示分类
    tags: true # true or false 文章页是否显示标签
    label: true # true or false 显示描述性文字
```

> 主页

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-page-meta.png)

> 文章页

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-info.png)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-tag.png)

`date_format` 是 3.2.0 新增的内容，配置时间显示明确时间还是相对时间

> 相对时间

![image-20200928201701560](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-relative-time.png)

> 明确时间

![image-20200928201911032](https://file.crazywong.com/gh/jerryc127/CDN/img/theme-butterfly-docs-full-date.png)

### 文章版权

为你的博客文章展示文章版权和许可协议。

修改 `主题配置文件`

```yaml
post_copyright:
  enable: true
  decode: false
  author_href:
  license: CC BY-NC-SA 4.0
  license_url: https://creativecommons.org/licenses/by-nc-sa/4.0/
```

由于`Hexo 4.1`开始，默认对网址进行解码，以至于如果是中文网址，会被解码，可设置`decode: true`来显示中文网址。

如果有文章（例如：转载文章）不需要显示版权，可以在文章 Front-matter 单独设置

```yaml
copyright: false
```

从`3.0.0`开始，支持对单独文章设置版权信息，可以在文章 Front-matter 单独设置

```markdown
copyright_author: xxxx
copyright_author_href: https://xxxxxx.com
copyright_url: https://xxxxxx.com
copyright_info: 此文章版权归 xxxxx 所有，如有转载，请注明来自原作者
```

**版权显示截图**

![image-20210130161913121](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-copyright.png)

### 文章打赏

在你每篇文章的结尾，可以添加打赏按钮。相关二维码可以自行配置。

对于没有提供二维码的，可配置一张软件的 icon 图片，然后在 link 上添加相应的打赏链接。用户点击图片就会跳转到链接去。

link 可以不写，会默认为图片的链接。

修改 `主题配置文件`

```yaml
reward:
  enable: true
  QR_code:
    - img: /img/wechat.jpg
      link:
      text: 微信
    - img: /img/alipay.jpg
      link:
      text: 支付宝
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-donate.png)

### TOC

在文章页，会有一个目录，用于显示 TOC。

修改 `主题配置文件`

```yaml
toc:
  post: true
  page: true
  number: true
  expand: false
  style_simple: false # for post
  scroll_percent: true
```

| 属性           | 解释                                              |
| -------------- | ------------------------------------------------- |
| post           | 文章页是否显示 TOC                                |
| page           | 普通页面是否显示 TOC                              |
| number         | 是否显示章筛数                                    |
| expand         | 是否展开 TOC                                      |
| style_simple   | 简洁模式（侧边栏**只**显示 TOC, 只对文章页有效 ） |
| scroll_percent | 是否显示滚动进度百分比                            |

> Toc PC

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-toc-pc-new.png)

> Toc Mobile

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-toc-mobile-new.png)

> style_simple: true

![image-20201209232104167](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-toc-style-simple.png)

#### 为特定的文章配置

在你的文章`md`文件的头部，加入`toc_number`和`toc`，并配置`true`或者`false`即可。

主题会优先判断文章 Markdown 的 Front-matter 是否有配置，如有，则以 Front-matter 的配置为准。否则，以**主题配置文件中**的配置为准

### 相关文章

{% note warning %}
当文章封面设置为 false 时，或者没有获取到封面配置，相关文章背景将会显示主题色。
{% endnote %}

相关文章推荐的原理是根据文章 tags 的比重来推荐

修改 `主题配置文件`

```yaml
related_post:
  enable: true
  limit: 6 # 显示推荐文章数目
  date_type: created # or created or updated 文章日期显示创建日或者更新日
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-releatedpost.png)

### 文章过期提醒

可设置是否显示文章过期提醒，以更新时间为基准。

```markdown
# Displays outdated notice for a post (文章过期提醒)

noticeOutdate:
enable: true
style: flat # style: simple/flat
limit_day: 365 # When will it be shown
position: top # position: top/bottom
message_prev: It has been
message_next: days since the last update, the content of the article may be outdated.
```

` limit_day`： 距离更新时间多少天才显示文章过期提醒

`message_prev` ： 天数之前的文字

`message_next`：天数之后的文字

> style: flat

![image-20200731175909296](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butteffly-docs-outdate-flat.png)

> style: simple

![image-20200731180037968](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-outdated-simple.png)

### 文章编辑按钮

在文章标题旁边显示一个编辑按钮，点击会跳转到对应的链接去。

```yaml
# Post edit
# Easily browse and edit blog source code online.
post_edit:
  enable: false
  # url: https://github.com/user-name/repo-name/edit/branch-name/subdirectory-name/
  # For example: https://github.com/jerryc127/butterfly.js.org/edit/main/source/
  url:
```

![image-20210130160108360](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-post-edit.png)

![image-20210130160208436](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-post-edit-2.png)

### 文章分页按钮

{% note warning %}
当文章封面设置为 false 时，或者没有获取到封面配置，分页背景将会显示主题色。
{% endnote %}

可设置分页的逻辑，也可以关闭分页显示

```yaml
# post_pagination (分页)
# value: 1 || 2 || false
# 1: The 'next post' will link to old post
# 2: The 'next post' will link to new post
# false: disable pagination
post_pagination: false
```

| 参数                   | 解释                 |
| ---------------------- | -------------------- |
| post_pagination: false | 关闭分页按钮         |
| post_pagination: 1     | 下一篇显示的是旧文章 |
| post_pagination: 2     | 下一篇显示的是新文章 |

![image-20210130161545100](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-post-pagination.png)

## 页面锚点

开启页面锚点后，当你在进行滚动时，页面链接会根据标题 ID 进行替换
(注意: 每替换一次，会留下一个历史记录。所以如果一篇文章有很多锚点的话，网页的历史记录会很多。)

修改 `主题配置文件`

```yaml
# anchor
# when you scroll in post , the url will update according to header id.
anchor:
  button:
    enable: false
    always_show: false
    icon: # the unicode value of Font Awesome icon, such as '\3423'
  auto_update: false # when you scroll in post, the URL will update according to header id.
```

## 头像

修改 `主题配置文件`

```yaml
avatar:
  img: /img/avatar.png
  effect: true # 头像会一直转圈
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-avatar.png)

## 图片描述

可开启图片 Figcaption 描述文字显示

优先显示图片的 title 属性，然后是 alt 属性

修改 `主题配置文件`

```yaml
photofigcaption: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-photo-figcaption.png)

## 复制相关配置

可配置网站是否可以复制、复制的内容是否添加版权信息

```markdown
# copy settings

# copyright: Add the copyright information after copied content (复制的内容后面加上版权信息)

copy:
enable: true
copyright:
enable: true
limit_count: 50
```

| 配置        | 解释                                                                   |
| ----------- | ---------------------------------------------------------------------- |
| enable      | 是否开启网站复制权限                                                   |
| copyright   | 复制的内容后面加上版权信息                                             |
| enable      | 是否开启复制版权信息添加                                               |
| limit_count | 字数限制，当复制文字大于这个字数限制时，将在复制的内容后面加上版权信息 |

> 添加版权信息后

```
Lorem ipsum dolor sit amet, test link consectetur adipiscing elit. Strong text pellentesque ligula commodo viverra vehicula. Italic text at ullamcorper enim. Morbi a euismod nibh. Underline text non elit nisl. Deleted text tristique, sem id condimentum tempus, metus lectus venenatis mauris, sit amet semper lorem felis a eros. Fusce egestas nibh at sagittis auctor. Sed ultricies ac arcu quis molestie. Donec dapibus nunc in nibh egestas, vitae volutpat sem iaculis. Curabitur sem tellus, elementum nec quam id, fermentum laoreet mi. Ut mollis ullamcorper turpis, vitae facilisis velit ultricies sit amet. Etiam laoreet dui odio, id tempus justo tincidunt id. Phasellus scelerisque nunc sed nunc ultricies accumsan.


作者: Jerry
链接: http://localhost:4000/posts/bd3c650b/#Paragraph
来源: Butterfly
著作权归作者所有。商业转载请联络作者获得授权，非商业转载请注明出处。
```

## Footer 设置

### 博客年份

`since`是一个来展示你站点起始时间的选项。它位于页面的最底部。

修改 `主题配置文件`

```yaml
footer:
  owner:
    enable: true
    since: 2018
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-since.png)

### 页脚自定义文本

`custom_text`是一个给你用来在页脚自定义文本的选项。通常你可以在这里写声明文本等。支持 HTML。

修改 `主题配置文件`

```yaml
custom_text: Hi, welcome to my <a href="https://butterfly.js.org/">blog</a>!
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-footer-text.png)

对于部分人需要写 ICP 的，也可以写在 `custom_text`里

```yaml
custom_text: <a href="icp链接"><img class="icp-icon" src="icp图片"><span>备案号：xxxxxx</span></a>
```

## 右下角按钮

### 简繁转换

简体繁体互换

右下角会有简繁转换按钮。

修改 `主题配置文件`

```yaml
translate:
  enable: true
  # 默认按钮显示文字(网站是简体，应设置为'default: 繁')
  default: 简
  #网站默认语言，1: 繁体中文, 2: 简体中文
  defaultEncoding: 1
  #延迟时间,若不在前, 要设定延迟翻译时间, 如100表示100ms,默认为0
  translateDelay: 0
  #当文字是简体时，按钮显示的文字
  msgToTraditionalChinese: "繁"
  #当文字是繁体时，按钮显示的文字
  msgToSimplifiedChinese: "简"
```

> 简体

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-simp.png)

> 繁体

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-tranditional.png)

### 夜间模式

右下角会有夜间模式按钮

修改 `主题配置文件`

```yaml
# dark mode
darkmode:
  enable: true
  # dark mode和 light mode切换按钮
  button: true
  autoChangeMode: false
```

![image-20201230201029381](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-dark-mode-1.png)

{% note info %}
V2.0.0 开始增加一个选项，可开启自动切换 light mode 和 dark mode

autoChangeMode: 1 跟随系统而变化，不支持的浏览器/系统将按照时间晚上 6 点到早上 6 点之间切换为 dark mode

autoChangeMode: 2 只按照时间 晚上 6 点到早上 6 点之间切换为 dark mode,其余时间为 light mode

autoChangeMode: false 取消自动切换
{% endnote %}

### 阅读模式

阅读模式下会去掉除文章外的内容，避免干扰阅读。

只会出现在文章页面，右下角会有阅读模式按钮。

修改 `主题配置文件`

```yaml
readmode: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-read-mode.png)

### 滚动状态百分比

主题配置文件中

```yaml
# show scroll percent in scroll-to-top button
rightside_scroll_percent: true
```

![](https://cdn.jsdelivr.net/gh/jerryc127/CDN@m2/img/hexo-butterfly-docs-scroll-percent-right-btn.gif)

### 按钮排序

```yaml
# Don't modify the following settings unless you know how they work (非必要请不要修改 )
# Choose: readmode,translate,darkmode,hideAside,toc,chat,comment
# Don't repeat 不要重复
rightside_item_order:
  enable: false
  hide: # readmode,translate,darkmode,hideAside
  show: # toc,chat,comment
```

注意： 不要重复

## 侧边栏设置

### 侧边排版

可自行決定哪个项目需要显示，可決定位置，也可以设置不显示侧边栏。

修改 `主题配置文件`

```yaml
aside:
  enable: true
  hide: false
  button: true
  mobile: true # display on mobile
  position: right # left or right
  display:
    archive: true
    tag: true
    category: true
  card_author:
    enable: true
    description:
    button:
      enable: true
      icon: fab fa-github
      text: Follow Me
      link: https://github.com/xxxxxx
  card_announcement:
    enable: true
    content: This is my Blog
  card_recent_post:
    enable: true
    limit: 5 # if set 0 will show all
    sort: date # date or updated
    sort_order: # Don't modify the setting unless you know how it works
  card_categories:
    enable: true
    limit: 8 # if set 0 will show all
    expand: none # none/true/false
    sort_order: # Don't modify the setting unless you know how it works
  card_tags:
    enable: true
    limit: 40 # if set 0 will show all
    color: false
    orderby: random # Order of tags, random/name/length
    order: 1 # Sort of order. 1, asc for ascending; -1, desc for descending
    sort_order: # Don't modify the setting unless you know how it works
  card_archives:
    enable: true
    type: monthly # yearly or monthly
    format: MMMM YYYY # eg: YYYY年MM月
    order: -1 # Sort of order. 1, asc for ascending; -1, desc for descending
    limit: 8 # if set 0 will show all
    sort_order: # Don't modify the setting unless you know how it works
  card_webinfo:
    enable: true
    post_count: true
    last_push_date: true
    sort_order: # Don't modify the setting unless you know how it works
```

> position: left

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-aside-left.png)

> position: right

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-aside-right.png)

> card_tags color: false

![](https://file.crazywong.com/gh/jerryc127/CDN/img/20200426182730.png)

> card_tags color: true

![](https://file.crazywong.com/gh/jerryc127/CDN/img/20200426183025.png)

> aside button

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-aside-button.gif)

### 访问人数 busuanzi (UV 和 PV)

访问 busuanzi 的[官方网站](http://busuanzi.ibruce.info/)查看更多的介绍。

修改 `主题配置文件`

```yaml
busuanzi:
  site_uv: true
  site_pv: true
  page_pv: true
```

> 如果需要修改 busuanzi 的 CDN 链接，可通过 `主题配置文件` 的 `CDN` 中的 `option` 进行修改

```yaml
CDN:
  option:
  	busuanzi: xxxxxxxxx
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-busuanzi-site-pv.png)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-pv.png)

### 运行时间

网页已运行时间

修改 `主题配置文件`

```yaml
runtimeshow:
  enable: true
  publish_date: 6/7/2018 00:00:00
  ##网页开通时间
  #格式: 月/日/年 时间
  #也可以写成 年/月/日 时间
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-runtime.png)

### 最新评论

> 3.1.0 起支持

{% note primary %}

最新评论只会在刷新时才会去读取，并不会实时变化

由于 API 有 访问次数限制，为了避免调用太多，主题默认存取期限为 10 分钟。也就是说，调用后资料会存在 _localStorage_ 里，10 分钟内刷新网站只会去 _localStorage_ 读取资料。 10 分钟期限一过，刷新页面时才会去调取 API 读取新的数据。（ 3.6.0 新增了 `storage` 配置，可自行配置缓存时间）

{% endnote %}

在侧边栏显示最新评论板块

修改 `主题配置文件`

```js
# Aside widget - Newest Comments
newest_comments:
  enable: true
  sort_order: # Don't modify the setting unless you know how it works
  limit: 6
  storage: 10 # unit: mins, save data to localStorage
  avatar: true
```

部分配置解释：

| 配置    | 解释                    |
| ------- | ----------------------- |
| limit   | 显示的数量              |
| storage | 设置缓存时间，单位 分钟 |
| avatar  | 是否显示头像            |

> Demo

![image-20200830223037320](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-newest-comments.png)

### 自定义添加栏目

{% btn '/posts/ea33ab97/','点击前往',fas fa-lightbulb,block green %}

## 标签插件（Tag Plugins）

{% note info %}

标签插件是 Hexo 独有的功能，并不是标准的 Markdown 格式。

以下的写法，只适用于 Butterfly 主题，用在其它主题上不会有效果，甚至可能会报错。使用前请留意

{% endnote %}

{% note warning %}

标签插件虽然能为主题带来一些额外的功能和 UI 方面的强化，但是，标签插件也有明显的限制，使用时请留意。

{% endnote %}

### Note (Bootstrap Callout)

{% tabs note %}

<!-- tab 通用设置 -->

移植于 next 主题，并进行修改。

修改 `主题配置文件`

```yaml
note:
  # Note tag style values:
  #  - simple    bs-callout old alert style. Default.
  #  - modern    bs-callout new (v2-v3) alert style.
  #  - flat      flat callout style with background, like on Mozilla or StackOverflow.
  #  - disabled  disable all CSS styles import of note tag.
  style: simple
  icons: false
  border_radius: 3
  # Offset lighter of background in % for modern and flat styles (modern: -12 | 12; flat: -18 | 6).
  # Offset also applied to label tag variables. This option can work with disabled note tag.
  light_bg_offset: 0
```

`icons`和`light_bg_offset`只对*方法一*生效

Note 标签插件有两种用法

<!-- endtab -->

<!-- tab 用法 1 -->

```markdown
{% note [class] [no-icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

| 名称    | 用法                                                                                                |
| ------- | --------------------------------------------------------------------------------------------------- |
| class   | 【可选】标识，不同的标识有不同的配色<br>（ default / primary / success / info / warning / danger ） |
| no-icon | 【可选】不显示 icon                                                                                 |
| style   | 【可选】可以覆盖配置中的 style <br>（simple/modern/flat/disabled）                                  |

> simple

```markdown
{% note simple %}
默认 提示块标签
{% endnote %}

{% note default simple %}
default 提示块标签
{% endnote %}

{% note primary simple %}
primary 提示块标签
{% endnote %}

{% note success simple %}
success 提示块标签
{% endnote %}

{% note info simple %}
info 提示块标签
{% endnote %}

{% note warning simple %}
warning 提示块标签
{% endnote %}

{% note danger simple %}
danger 提示块标签
{% endnote %}
```

{% note simple %}
默认 提示块标签
{% endnote %}

{% note default simple %}
default 提示块标签
{% endnote %}

{% note primary simple %}
primary 提示块标签
{% endnote %}

{% note success simple %}
success 提示块标签
{% endnote %}

{% note info simple %}
info 提示块标签
{% endnote %}

{% note warning simple %}
warning 提示块标签
{% endnote %}

{% note danger simple %}
danger 提示块标签
{% endnote %}

> modern

```markdown
{% note modern %}
默认 提示块标签
{% endnote %}

{% note default modern %}
default 提示块标签
{% endnote %}

{% note primary modern %}
primary 提示块标签
{% endnote %}

{% note success modern %}
success 提示块标签
{% endnote %}

{% note info modern %}
info 提示块标签
{% endnote %}

{% note warning modern %}
warning 提示块标签
{% endnote %}

{% note danger modern %}
danger 提示块标签
{% endnote %}
```

{% note modern %}
默认 提示块标签
{% endnote %}

{% note default modern %}
default 提示块标签
{% endnote %}

{% note primary modern %}
primary 提示块标签
{% endnote %}

{% note success modern %}
success 提示块标签
{% endnote %}

{% note info modern %}
info 提示块标签
{% endnote %}

{% note warning modern %}
warning 提示块标签
{% endnote %}

{% note danger modern %}
danger 提示块标签
{% endnote %}

> flat

```markdown
{% note flat %}
默认 提示块标签
{% endnote %}

{% note default flat %}
default 提示块标签
{% endnote %}

{% note primary flat %}
primary 提示块标签
{% endnote %}

{% note success flat %}
success 提示块标签
{% endnote %}

{% note info flat %}
info 提示块标签
{% endnote %}

{% note warning flat %}
warning 提示块标签
{% endnote %}

{% note danger flat %}
danger 提示块标签
{% endnote %}
```

{% note flat %}
默认 提示块标签
{% endnote %}

{% note default flat %}
default 提示块标签
{% endnote %}

{% note primary flat %}
primary 提示块标签
{% endnote %}

{% note success flat %}
success 提示块标签
{% endnote %}

{% note info flat %}
info 提示块标签
{% endnote %}

{% note warning flat %}
warning 提示块标签
{% endnote %}

{% note danger flat %}
danger 提示块标签
{% endnote %}

> disabled

```markdown
{% note disabled %}
默认 提示块标签
{% endnote %}

{% note default disabled %}
default 提示块标签
{% endnote %}

{% note primary disabled %}
primary 提示块标签
{% endnote %}

{% note success disabled %}
success 提示块标签
{% endnote %}

{% note info disabled %}
info 提示块标签
{% endnote %}

{% note warning disabled %}
warning 提示块标签
{% endnote %}

{% note danger disabled %}
danger 提示块标签
{% endnote %}
```

{% note disabled %}
默认 提示块标签
{% endnote %}

{% note default disabled %}
default 提示块标签
{% endnote %}

{% note primary disabled %}
primary 提示块标签
{% endnote %}

{% note success disabled %}
success 提示块标签
{% endnote %}

{% note info disabled %}
info 提示块标签
{% endnote %}

{% note warning disabled %}
warning 提示块标签
{% endnote %}

{% note danger disabled %}
danger 提示块标签
{% endnote %}

> no-icon

```markdown
{% note no-icon %}
默认 提示块标签
{% endnote %}

{% note default no-icon %}
default 提示块标签
{% endnote %}

{% note primary no-icon %}
primary 提示块标签
{% endnote %}

{% note success no-icon %}
success 提示块标签
{% endnote %}

{% note info no-icon %}
info 提示块标签
{% endnote %}

{% note warning no-icon %}
warning 提示块标签
{% endnote %}

{% note danger no-icon %}
danger 提示块标签
{% endnote %}
```

{% note no-icon %}
默认 提示块标签
{% endnote %}

{% note default no-icon %}
default 提示块标签
{% endnote %}

{% note primary no-icon %}
primary 提示块标签
{% endnote %}

{% note success no-icon %}
success 提示块标签
{% endnote %}

{% note info no-icon %}
info 提示块标签
{% endnote %}

{% note warning no-icon %}
warning 提示块标签
{% endnote %}

{% note danger no-icon %}
danger 提示块标签
{% endnote %}

<!-- endtab -->

<!-- tab 用法 2（自定义 icon）-->

> 3.2.0 以上版本支

```markdown
{% note [color] [icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

| 名称  | 用法                                                                     |
| ----- | ------------------------------------------------------------------------ |
| color | 【可选】颜色 <br>(default / blue / pink / red / purple / orange / green) |
| icon  | 【可选】可配置自定义 icon (只支持 fontawesome 图标, 也可以配置 no-icon ) |
| style | 【可选】可以覆盖配置中的 style<br/>（simple/modern/flat/disabled）       |

> simple

```markdown
{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' simple %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' simple %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' simple%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' simple %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' simple %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' simple %}
前端最讨厌的浏览器
{% endnote %}

> modern

```markdown
{% note 'fab fa-cc-visa' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' modern %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' modern %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' modern%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' modern %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' modern %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' modern %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' modern %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' modern%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' modern %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' modern %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' modern %}
前端最讨厌的浏览器
{% endnote %}

> flat

```markdown
{% note 'fab fa-cc-visa' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' flat %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' flat %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' flat%}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' flat %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' flat %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' flat%}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' flat%}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' flat%}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' flat %}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' flat %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' flat %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' flat %}
前端最讨厌的浏览器
{% endnote %}

> disabled

```markdown
{% note 'fab fa-cc-visa' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' disabled %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' disabled %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' disabled %}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' disabled %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' disabled %}
前端最讨厌的浏览器
{% endnote %}
```

{% note 'fab fa-cc-visa' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue 'fas fa-bullhorn' disabled %}
2021 年快到了....
{% endnote %}
{% note pink 'fas fa-car-crash' disabled %}
小心开车 安全至上
{% endnote %}
{% note red 'fas fa-fan' disabled %}
这是三片呢？还是四片？
{% endnote %}
{% note orange 'fas fa-battery-half' disabled %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple 'far fa-hand-scissors' disabled %}
剪刀石头布
{% endnote %}
{% note green 'fab fa-internet-explorer' disabled %}
前端最讨厌的浏览器
{% endnote %}

> no-icon

```markdown
{% note no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue no-icon %}
2021 年快到了....
{% endnote %}
{% note pink no-icon %}
小心开车 安全至上
{% endnote %}
{% note red no-icon %}
这是三片呢？还是四片？
{% endnote %}
{% note orange no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple no-icon %}
剪刀石头布
{% endnote %}
{% note green no-icon %}
前端最讨厌的浏览器
{% endnote %}
```

{% note no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note blue no-icon %}
2021 年快到了....
{% endnote %}
{% note pink no-icon %}
小心开车 安全至上
{% endnote %}
{% note red no-icon %}
这是三片呢？还是四片？
{% endnote %}
{% note orange no-icon %}
你是刷 Visa 还是 UnionPay
{% endnote %}
{% note purple no-icon %}
剪刀石头布
{% endnote %}
{% note green no-icon %}
前端最讨厌的浏览器
{% endnote %}

<!-- endtab -->

{% endtabs %}

### Gallery 相册图库

> 2.2.0 以上提供

一个图库集合。

写法

```
<div class="gallery-group-main">
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
{% galleryGroup name description link img-url %}
</div>
```

- name：图库名字
- description：图库描述
- link：連接到对应相册的地址
- img-url：图库封面的地址

例如：

```
<div class="gallery-group-main">
{% galleryGroup '壁纸' '收藏的一些壁纸' '/Gallery/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
{% galleryGroup '漫威' '关于漫威的图片' '/Gallery/marvel' https://i.loli.net/2019/12/25/8t97aVlp4hgyBGu.jpg %}
{% galleryGroup 'OH MY GIRL' '关于OH MY GIRL的图片' '/Gallery/ohmygirl' https://i.loli.net/2019/12/25/hOqbQ3BIwa6KWpo.jpg %}
</div>
```

<div class="gallery-group-main">
{% galleryGroup '壁纸' '收藏的一些壁纸' '/Gallery/wallpaper' https://i.loli.net/2019/11/10/T7Mu8Aod3egmC4Q.png %}
{% galleryGroup '漫威' '关于漫威的图片' '/Gallery/marvel' https://i.loli.net/2019/12/25/8t97aVlp4hgyBGu.jpg %}
{% galleryGroup 'OH MY GIRL' '关于OH MY GIRL的图片' '/Gallery/ohmygirl' https://i.loli.net/2019/12/25/hOqbQ3BIwa6KWpo.jpg %}
</div>

### Gallery 相册

> 2.0.0 以上提供

区别于旧版的 Gallery 相册,新的 Gallery 相册会自动根据图片长度进行排版，书写也更加方便，与 markdown 格式一样。可根据需要插入到相应的 md。

{% tabs %}

<!-- tab 本地 -->

写法:

```markdown
{% gallery [lazyload],[rowHeight],[limit] %}
markdown 图片格式
{% endgallery %}
```

| 参数      | 解释                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

> 示例

```markdown
{% gallery %}
markdown 图片格式
{% endgallery %}

{% gallery true,220,10 %}
markdown 图片格式
{% endgallery %}

{% gallery true,,10 %}
markdown 图片格式
{% endgallery %}
```

例如

```markdown
{% gallery %}
![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
{% endgallery %}
```

{% gallery %}
![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
{% endgallery %}

<!-- endtab -->

<!-- tab 远程拉取 -->

写法：

```markdown
{% gallery url,[link],[lazyload],[rowHeight],[limit] %}
{% endgallery %}
```

| 参数      | 解释                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| url       | 【必须】 识别詞                                                                      |
| link      | 【必须】远程的 json 链接                                                             |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

> 远程链接 Json 的例子

有三个参数，`url`是必须**存在**的，`alt` 和 `title` 可有，也可没有。

```json
[
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0556.jpg",
    "alt": "IMG_0556.jpg",
    "title": "这是title"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0472.jpg",
    "alt": "IMG_0472.jpg"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0453.jpg",
    "alt": ""
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0931.jpg",
    "alt": ""
  }
]
```

> 示例

```markdown
{% gallery url,https://xxxx.com/sss.json %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,220,10 %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,,10 %}
{% endgallery %}
```

<!-- endtab -->

{% endtabs %}

### tag-hide

{% note warning %}

2.2.0 以上提供

请注意，tag-hide 内的标签插件 content 内都不建议有 h1 - h6 等标题。因为 Toc 会把隐藏内容标题也显示出来，而且当滚动屏幕时，如果隐藏内容没有显示出来，会导致 Toc 的滚动出现异常。

{% endnote %}

如果你想把一些文字、内容隐藏起来，并提供按钮让用户点击显示。可以使用这个标签插件。

{% tabs tag-hide %}

<!-- tab Inline -->

`inline` 在文本里面添加按钮隐藏内容，只限文字

( content 不能包含英文逗号，可用`&sbquo;`)

```markdown
{% hideInline content,display,bg,color %}
```

- content: 文本内容

- display: 按钮显示的文字(可选)

- bg: 按钮的背景颜色(可选)

- color: 按钮文字的颜色(可选)

> Demo

```markdown
哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}

门里站着一个人? {% hideInline 闪 %}
```

哪个英文字母最酷？ {% hideInline 因为西装裤(C装酷),查看答案,#FF7242,#fff %}

门里站着一个人? {% hideInline 闪 %}

<!-- endtab -->

<!-- tab Block -->

`block`独立的 block 隐藏内容，可以隐藏很多内容，包括图片，代码块等等

( display 不能包含英文逗号，可用`&sbquo;`)

```markdown
{% hideBlock display,bg,color %}
content
{% endhideBlock %}
```

- content: 文本内容
- display: 按钮显示的文字(可选)
- bg: 按钮的背景颜色(可选)
- color: 按钮文字的颜色(可选)

> Demo

```mark
查看答案
{% hideBlock 查看答案 %}
傻子，怎么可能有答案
{% endhideBlock %}
```

查看答案
{% hideBlock 查看答案 %}
傻子，怎么可能有答案
{% endhideBlock %}

<!-- endtab -->

<!-- tab Toggle -->

> 2.3.0 以上支持

如果你需要展示的内容太多，可以把它隐藏在收缩框里，需要时再把它展开。

( display 不能包含英文逗号，可用`&sbquo;`)

```markdown
{% hideToggle display,bg,color %}
content
{% endhideToggle %}
```

> Demo

```markdown
{% hideToggle Butterfly安装方法 %}
在你的博客根目录里

git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

如果想要安装比较新的 dev 分支，可以

git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

{% endhideToggle %}
```

{% hideToggle Butterfly安装方法 %}
在你的博客根目录里

git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

如果想要安装比较新的 dev 分支，可以

git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/Butterfly

{% endhideToggle %}

<!-- endtab -->

{% endtabs %}

### mermaid

使用 mermaid 标签可以绘制 Flowchart（流程图）、Sequence diagram（时序图 ）、Class Diagram（类别图）、State Diagram（状态图）、Gantt（甘特图）和 Pie Chart（圆形图），具体可以查看[mermaid 文档](https://mermaid-js.github.io/mermaid/#/)

修改 `主题配置文件`

```yaml
# mermaid
# see https://github.com/mermaid-js/mermaid
mermaid:
  enable: true
  # built-in themes: default/forest/dark/neutral
  theme:
    light: default
    dark: dark
```

写法：

```markdown
{% mermaid %}
内容
{% endmermaid %}
```

例如：

```markdown
{% mermaid %}
pie
title Key elements in Product X
"Calcium" : 42.96
"Potassium" : 50.05
"Magnesium" : 10.01
"Iron" : 5
{% endmermaid %}
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-mermaid.png)

### Tabs

移植于 next 主题

使用方法

```markdown
{% tabs Unique name, [index] %}

<!-- tab [Tab caption] [@icon] -->

Any content (support inline tags too).

<!-- endtab -->

{% endtabs %}

Unique name : Unique name of tabs block tag without comma.
Will be used in #id's as prefix for each tab with their index numbers.
If there are whitespaces in name, for generate #id all whitespaces will replaced by dashes.
Only for current url of post/page must be unique!
[index] : Index number of active tab.
If not specified, first tab (1) will be selected.
If index is -1, no tab will be selected. It's will be something like spoiler.
Optional parameter.
[Tab caption] : Caption of current tab.
If not caption specified, unique name with tab index suffix will be used as caption of tab.
If not caption specified, but specified icon, caption will empty.
Optional parameter.
[@icon] : FontAwesome icon name (full-name, look like 'fas fa-font')
Can be specified with or without space; e.g. 'Tab caption @icon' similar to 'Tab caption@icon'.
Optional parameter.
```

> Demo 1 - 预设选择第一个【默认】

```markdown
{% tabs test1 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}
```

{% tabs test1 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

> Demo 2 - 预设选择 tabs

```markdown
{% tabs test2, 3 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}
```

{% tabs test2, 3 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

> Demo 3 - 没有预设值

```markdown
{% tabs test3, -1 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}
```

{% tabs test3, -1 %}

<!-- tab -->

**This is Tab 1.**

<!-- endtab -->

<!-- tab -->

**This is Tab 2.**

<!-- endtab -->

<!-- tab -->

**This is Tab 3.**

<!-- endtab -->

{% endtabs %}

> Demo 4 - 自定义 Tab 名 + 只有 icon + icon 和 Tab 名

```markdown
{% tabs test4 %}

<!-- tab 第一个Tab -->

**tab 名字为第一个 Tab**

<!-- endtab -->

<!-- tab @fab fa-apple-pay -->

**只有图标 没有 Tab 名字**

<!-- endtab -->

<!-- tab 炸弹@fas fa-bomb -->

**名字+icon**

<!-- endtab -->

{% endtabs %}
```

{% tabs test4 %}

<!-- tab 第一个Tab -->

**tab 名字为第一个 Tab**

<!-- endtab -->

<!-- tab @fab fa-apple-pay -->

**只有图标 没有 Tab 名字**

<!-- endtab -->

<!-- tab 炸弹@fas fa-bomb -->

**名字+icon**

<!-- endtab -->

{% endtabs %}

### Button

> 3.0 以上适用

使用方法：

```markdown
{% btn [url],[text],[icon],[color] [style] [layout] [position] [size] %}

[url] : 链接
[text] : 按钮文字
[icon] : [可选] 图标
[color] : [可选] 按钮背景颜色(默认 style 时）
按钮字体和边框颜色(outline 时)
default/blue/pink/red/purple/orange/green
[style] : [可选] 按钮样式 默认实心
outline/留空
[layout] : [可选] 按钮布局 默认为 line
block/留空
[position] : [可选] 按钮位置 前提是设置了 layout 为 block 默认为左边
center/right/留空
[size] : [可选] 按钮大小
larger/留空
```

> Demo

```markdown
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
```

This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline %}
This is my website, click the button {% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}

```markdown
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block center larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block right outline larger %}
```

{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block center larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,block right outline larger %}

**more than one button in center**

```markdown
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,green larger %}
```

{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,green larger %}

```markdown
<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline green larger %}
</div>
```

<div class="btn-center">
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline blue larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline pink larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline red larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline purple larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline orange larger %}
{% btn 'https://butterfly.js.org/',Butterfly,far fa-hand-point-right,outline green larger %}
</div>

### inlineImg

主题中的图片都是默认以`块级元素`显示，如果你想以`内联元素`显示，可以使用这个标签插件。

```markdown
{% inlineImg [src] [height] %}

[src] : 图片链接
[height] ： 图片高度限制【可选】
```

> Demo

```markdown
你看我长得漂亮不

![](https://i.loli.net/2021/03/19/2P6ivUGsdaEXSFI.png)

我觉得很漂亮 {% inlineImg https://i.loli.net/2021/03/19/5M4jUB3ynq7ePgw.png 150px %}
```

![image-20210319001204045](https://file.crazywong.com/gh/jerryc127/CDN@m2/img/hexo-theme-butterfly-docs-inlineimg.png)

### label

> 3.7.5 及以上版本适用

高亮所需的文字

```markdown
{% label text color %}
```

| 参数  | 解释                                                                              |
| ----- | --------------------------------------------------------------------------------- |
| text  | 文字                                                                              |
| color | 【可选】背景颜色，默认为 `default`<br />default/blue/pink/red/purple/orange/green |

> Demo

```markdown
臣亮言：{% label 先帝 %}创业未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此诚{% label 危急存亡之秋 red %}也！然侍卫之臣，不懈于内；{% label 忠志之士 purple %}，忘身于外者，盖追先帝之殊遇，欲报之于陛下也。诚宜开张圣听，以光先帝遗德，恢弘志士之气；不宜妄自菲薄，引喻失义，以塞忠谏之路也。
宫中、府中，俱为一体；陟罚臧否，不宜异同。若有{% label 作奸 orange %}、{% label 犯科 green %}，及为忠善者，宜付有司，论其刑赏，以昭陛下平明之治；不宜偏私，使内外异法也。
```

臣亮言：{% label 先帝 %}创业未半，而{% label 中道崩殂 blue %}。今天下三分，{% label 益州疲敝 pink %}，此诚{% label 危急存亡之秋 red %}也！然侍卫之臣，不懈于内；{% label 忠志之士 purple %}，忘身于外者，盖追先帝之殊遇，欲报之于陛下也。诚宜开张圣听，以光先帝遗德，恢弘志士之气；不宜妄自菲薄，引喻失义，以塞忠谏之路也。
宫中、府中，俱为一体；陟罚臧否，不宜异同。若有{% label 作奸 orange %}、{% label 犯科 green %}，及为忠善者，宜付有司，论其刑赏，以昭陛下平明之治；不宜偏私，使内外异法也。

### timeline

> 4.0.0 以上支持

```markdown
{% timeline title,color %}

<!-- timeline title -->

xxxxx

<!-- endtimeline -->
<!-- timeline title -->

xxxxx

<!-- endtimeline -->

{% endtimeline %}
```

| 参数  | 解释                                                                           |
| ----- | ------------------------------------------------------------------------------ |
| title | 标题/时间線                                                                    |
| color | timeline 颜色<br />default(留空) / blue / pink / red / purple / orange / green |

> Demo

```markdown
{% timeline 2022 %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022 %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,blue %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,blue %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,pink %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,pink %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,red %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,red %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,purple %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,purple %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,orange %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,orange %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

```markdown
{% timeline 2022,green %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}
```

{% timeline 2022,green %}

<!-- timeline 01-02 -->

这是测试页面

<!-- endtimeline -->

{% endtimeline %}

### flink

> 4.1.0 支持

可在任何界面插入类似友情链接列表效果

内容格式与友情链接界面一样，支持 yml 格式

```markdown
{% flink %}
xxxxxx
{% endflink %}
```

> Demo

```markdown
{% flink %}

- class_name: 友情链接
  class_desc: 那些人，那些事
  link_list:

  - name: JerryC
    link: https://jerryc.me/
    avatar: https://jerryc.me/img/avatar.png
    descr: 今日事,今日毕
  - name: Hexo
    link: https://hexo.io/zh-tw/
    avatar: https://d33wubrfki0l68.cloudfront.net/6657ba50e702d84afb32fe846bed54fba1a77add/827ae/logo.svg
    descr: 快速、简单且强大的博客框架

- class_name: 网站
  class_desc: 值得推荐的网站
  link_list: - name: Youtube
  link: https://www.youtube.com/
  avatar: https://i.loli.net/2020/05/14/9ZkGg8v3azHJfM1.png
  descr: 视频网站 - name: Weibo
  link: https://www.weibo.com/
  avatar: https://i.loli.net/2020/05/14/TLJBum386vcnI1P.png
  descr: 中国最大社交分享平台 - name: Twitter
  link: https://twitter.com/
  avatar: https://i.loli.net/2020/05/14/5VyHPQqR6LWF39a.png
  descr: 社交分享平台
  {% endflink %}
```

![](https://file.crazywong.com/gh/jerryc127/CDN@m2/img/hexo-theme-butterfly-docs-flink-demo.png)

{% btn '/posts/ceeb73f/',⚔️ Butterfly-安装文档-四-主题配置-2,far fa-hand-point-right,block red right larger %}
