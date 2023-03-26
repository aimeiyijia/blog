---
title: Butterfly 安装文档(五) 进阶教程
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: Docs文档
keywords: 'hexo,butterfly,主题,doc,教程,文档'
description: Butterfly安装文档-进阶教程
cover: 
abbrlink: 4073eda
date: 2022-03-24 15:50:42
comments: false
---

{% note green 'fas fa-rocket' %}

 📚  文档目录

{% post_link Butterfly-安装文档-一-快速开始 ' 🚀 快速开始' %} - {% post_link Butterfly-安装文档-二-主题页面 ' 📑 主题页面' %} - {% post_link Butterfly-安装文档-三-主题配置-1 ' 🛠 主题配置-1' %} - {% post_link Butterfly-安装文档-四-主题配置-2 ' ⚔️ 主题配置-2' %} - {% post_link Butterfly-安装文档-五-进阶教程 ' ⚡️ 进阶教程' %} 

{% endnote %}



***

## 建议

1. 不要把个人需要的文件/图片放在主题`source`文件夹里，因为在升级主题的过程中，可能会把文件覆盖刪除了。
在Hexo根目录的`source`文件夹里，创建一个文件夹来放置个人文件/图片。
引用文件直接为`/文件夹名称/文件名`

## 音乐

音乐界面使用了插件 `hexo-tag-aplayer`
使用方法请参考插件[文档](https://github.com/MoePlayer/hexo-tag-aplayer/blob/master/docs/README-zh_cn.md)

音乐页面只是普通的page页，按普通页面操作生成就行。

> 以下内容可供**选择**配置
>
> 注意： 仍需要安装插件[hexo-tag-aplayer](https://github.com/MoePlayer/hexo-tag-aplayer)

插件会在每一个文件都插入 js 和 css，为了避免这一情況，3.0 版本内置了 aplayer 需要的 css 和 js。

首先在Hexo根目录`_config`里配置`asset_inject`为`false`

```yaml
aplayer:
  asset_inject: false
```

然后在你需要使用aplayer的页面Front-matter添加

```markdown
aplayer: true
```

这样只会在需要aplayer的页面插入js和css。

如何添加全局 Aplayer 播放，请参考 [这篇文章](/posts/507c070f/)

## 电影

电影界面使用了插件 `hexo-butterfly-douban`
使用方法请参考插件的[文档](https://github.com/jerryc127/butterfly-plugins/tree/main/hexo-butterfly-douban)。

**注意：** 
1. hexo-butterfly-douban 会主动生成页面，所以不需要自己创建。
2. 如遇到无法抓取问题，显示 `INFO  0 movies have been loaded in xxx ms, because you are offline or your network is bad`
   请过段时间再试试，这我也无能为力。

## 说说

### Artitalk

安装插件 [hexo-butterfly-artitalk](https://www.npmjs.com/package/hexo-butterfly-artitalk)

具体配置查看[插件文档](https://github.com/jerryc127/butterfly-plugins/tree/main/hexo-butterfly-artitalk)

### HexoPlusPlus Talk

安装插件 [hexo-butterfly-hpptalk](https://www.npmjs.com/package/hexo-butterfly-hpptalk)

具体配置查看[插件文档](https://github.com/jerryc127/butterfly-plugins/tree/main/hexo-butterfly-hpptalk)

## Butterfly-自定义代码配色

{% btn '/posts/b37b5fe3/','点击前往',fas fa-code,block blue %}


## 自定义侧边栏

{% btn '/posts/ea33ab97/','点击前往',fas fa-lightbulb,block green %}



## 添加全局吸底Aplayer教程

{% btn '/posts/507c070f/','点击前往',fas fa-music,block pink %}
## Icon

Butterfly主题内置了[Font Awesome V5 ](https://fontawesome.com/)图标，目前已更新到 5.13.0，总共有1,588个免费图标。由于是国外的图标网站，对于国内的一些网站Icon并不支持。如有需要，你可以引入其它的图标服务商。

### iconfont

国内最出名的莫过于[iconfont](https://www.iconfont.cn/),功能很强大且图标内容很丰富的矢量图标库。很多`Font Awesome`不支持的图标都可以在这里找到。同时，[iconfont](https://www.iconfont.cn/)支持选择需要的图标生成css链接，减少不必要的CSS加载。

#### 注册账号

打开[iconfont](https://www.iconfont.cn/)的网站，点击导航栏的`人像`图标，会跳出注册界面，按要求注册账号。

![Snipaste_2020-05-28_21-12-01](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont.png)

#### 添加图标入库

选择自己需要的图标，把鼠标移到图标上，会显示三个按钮（依次是添加入库、收藏和下载），而我们需要的是把图标添加入库

![image-20200528205401440](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-add.png)

添加入库后，你可以看到网站右上角`购物车`图标显示了`1`字，代表图标已经添加入库，点击`购物车`图标，会弹出侧边栏显示详情。

![image-20200528205925258](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-check.png)

![image-20200528210120442](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-detail.png)



已选择的图标会显示在上面，你可以重复上面的操作，把需要的图标添加入库，然后点击`添加到项目`。

接下来会要求选择项目名称，没有的自己创建一个。

![image-20200528211624459](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-create.png)

#### 生成CSS链接

在添加到项目之后，会跳到项目的详情界面。点击`Font class`，然后再点击`暫无代码，点击生成`文字。网站会自动生成CSS链接，我们只需要复制链接就行。

![image-20200528212301786](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-link.png)

#### 添加链接进主题配置文件

打开`主题配置文件`，找到`inject`配置，按要求把链接填入

![image-20200528212440743](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-setting.png)

在我们需要使用的地方填入icon，例如`Menu`，图片使用格式为`iconfont icon名字`

![image-20200528213151304](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-setting-menu.png)

运行Butterfly之后，你就可以看到menu的图标生效了

![image-20200528213346338](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-iconfont-show.png)

#### 其他添加方法

除了通过引入CSS链接使用图标，iconfont也支持通过其它方法使用图标，具体可查看[iconfont官方使用文档](https://www.iconfont.cn/help/detail?helptype=code)

### 其它图标提供商

除了[iconfont](https://www.iconfont.cn/)，还有[RemixIcon](https://github.com/Remix-Design/RemixIcon)、[Flaticon](https://www.flaticon.com/categories/seo-and-web)等等提供商，很多图标可以选择，具体使用方法请参考各自的文档。

## 图片压缩

Butterfly主题需要使用到很多图片。如果图片太大，会严重拖慢网站的加载速度。

图片压缩能夠有效的缓解这个问题。

除了通过`gulp-imagemin`来压缩图片，还可以通过在线压缩网站和软件来进行压缩。以下两款是我自己正在使用的工具。网上有很多这样的工具，挑选一款适合自己的就行。

- [tinypng](https://tinypng.com/)

  一个在线压缩的网站。压缩后的图片也保留了很高的质量，在知乎上很多人推荐，不过免费版有限制。

  ![image-20200526173511503](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-tinypng.png)

- [caesium](https://saerasoft.com/caesium/)

  开源软件，支持Windows和macOS。可以批量压缩软件，无限制。

  ![image-20200526173316278](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-caesium.png)
  
-  [imgbot](https://github.com/marketplace/imgbot)

  imgbot 是一款 Github 插件。

  安装后，你上传图片到 Github 去，imgbot 会自动压缩图片并推送 PR，我们只需要合并 PR 就行

  你可以配置 imgbot 的检测方法、压缩方法（有损/无损），具体可以查看插件的文档

  ![image-20200830231742951](https://file.crazywong.com/gh/jerryc127/CDN/img/butterfly-enhance-imgbot.png)

  

## 插件推荐

- [hexo-abbrlink](https://github.com/rozbo/hexo-abbrlink)

  可以把链接permalink转为数字的插件，配置容易，生成时自动转为数字。

- [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) 

  生成RSS文件的插件
  
- [hexo-filter-nofollow](https://github.com/hexojs/hexo-filter-nofollow)

  为网站使用到的所有外链添加`rel="noopener external nofollow noreferrer"`, 可以有效地加强网站SEO和防止权重流失

- [hexo-generator-sitemap](https://github.com/hexojs/hexo-generator-sitemap)

  生成sitemap的插件

- [hexo-generator-baidu-sitemap](https://github.com/coneycode/hexo-generator-baidu-sitemap)

  看名字就知道，是专门为百度生成sitemap的插件