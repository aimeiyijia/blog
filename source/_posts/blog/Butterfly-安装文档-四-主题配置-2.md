---
title: Butterfly 安装文档(四) 主题配置-2
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: Docs文档
keywords: 'hexo,butterfly,主题,doc,教程,文档'
description: Butterfly安装文档-主题配置-2
cover: 
abbrlink: ceeb73f
date: 2022-03-24 15:12:42
comments: false
---

{% note green 'fas fa-rocket' %}

 📚  文档目录

{% post_link blog/Butterfly-安装文档-一-快速开始 ' 🚀 快速开始' %} - {% post_link blog/Butterfly-安装文档-二-主题页面 ' 📑 主题页面' %} - {% post_link blog/Butterfly-安装文档-三-主题配置-1 ' 🛠 主题配置-1' %} - {% post_link blog/Butterfly-安装文档-四-主题配置-2 ' ⚔️ 主题配置-2' %} - {% post_link blog/Butterfly-安装文档-五-进阶教程 ' ⚡️ 进阶教程' %} 

{% endnote %}



***

## 评论

{% tabs comments %}

<!-- tab 通用设置 -->

从3.0.0开始，开启评论需要在`comments-use`中填写你需要的评论。

支持双评论显示，只需要配置两个评论（第一个为默认显示）

```yaml
comments:
  # Up to two comments system, the first will be shown as default
  # Choose: Disqus/Disqusjs/Livere/Gitalk/Valine/Waline/Utterances/Facebook Comments/Twikoo
  use: Valine,Disqus
  text: true # Display the comment name next to the button
  # lazyload: The comment system will be load when comment element enters the browser's viewport.
  # If you set it to true, the comment count will be invalid
  lazyload: true
  count: true # Display comment count in top_img
  card_post_count: false # Display comment count in Home Page
```

| 参数            | 解释                                                         |
| --------------- | ------------------------------------------------------------ |
| use             | 使用的评论（请注意，最多支持两个，如果不需要请留空）<br>*注意：双评论不能是 Disqus 和 Disqusjs 一起，由于其共用同一个 ID，会出错* |
| text            | 是否显示评论服务商的名字                                     |
| lazyload        | 是否为评论开启lazyload，开启后，只有滚动到评论位置时才会加载评论所需要的资源（*开启 lazyload 后，评论数将不显示*） |
| count           | 是否在文章顶部显示评论数 <br/> livere、Giscus 和 utterances 不支持评论数显示 |
| card_post_count | 是否在首页文章卡片显示评论数<br/>gitalk、livere 、Giscus 和 utterances 不支持评论数显示 |

> 单评论

![image-20200731172506907](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-single-comments.png)

> 双评论

![image-20200731173006128](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-double-comments.png)

> 显示text

![image-20200731173006128](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-double-comments.png)

> 不显示text

![image-20200731173143712](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-double-comments-not-text.png)

<!-- endtab -->

<!-- tab Disqus -->

注册 [disqus](https://disqus.com/)，配置你自己的 disqus，然后在`Butterfly`里开启它。

修改 `主题配置文件`

```yaml
disqus:
  shortname:
```

![image-20201027211418161](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-disqus-new.png)

<!-- endtab -->

<!-- tab Disqusjs -->

与Disqus一样，但由于Disqus在中国大陆无法访问， 使用Disqusjs可以在无法访问Disqus时显示评论。具体可参考[Disqusjs](https://github.com/SukkaW/DisqusJS)。

修改 `主题配置文件`

```yaml
disqusjs:
  shortname:
  apikey:
  option:
```

> 当无法访问 Disqus 时，会显示

![image-20201027212543851](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-disqusjs-new.png)

<!-- endtab -->

<!-- tab livere（来必力） -->

注册[来必力](https://livere.com/)，配置你自己的来必力设置，然后在`Butterfly`里开启它。

修改 `主题配置文件`

```yaml
livere:
  uid:
```

laibili 的 uid 你能在这里找到:

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-laibili.jpg)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-laibili_2-new.png)

<!-- endtab -->

<!-- tab Gitalk -->

遵循 [gitalk](https://github.com/gitalk/gitalk)的指示去获取你的 github Oauth 应用的 client id 和 secret 值。以及查看它的相关配置说明。

然后修改 `主题配置文件`:

```yaml
gitalk:
  client_id:
  client_secret:
  repo:
  owner:
  admin:
  option:
```

![image-20201027212704930](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-gitalk-new.png)

<!-- endtab -->

<!-- tab Valine -->

遵循 [Valine](https://github.com/xCss/Valine)的指示去配置你的 LeanCloud 应用。以及查看相应的配置说明。

然后修改 `主题配置文件`:

```yaml
valine:
  appId: # leancloud application app id
  appKey: # leancloud application app key
  avatar: monsterid # gravatar style https://valine.js.org/#/avatar
  serverURLs: # This configuration is suitable for domestic custom domain name users, overseas version will be automatically detected (no need to manually fill in)
  bg: # valine background
  visitor: false
  option:
```

> 开启 visitor 后，文章页的访问人数将改为 Valine 提供，而不是 **不蒜子**

Valine于 v1.4.5 开始支持自定义表情，如果你需要自行配置，请在`emojiCDN`配置表情 CDN。

同时在Hexo 工作目录下的`source/_data/`创建一个json文件`valine.json`,等同于 Valine 需要配置的`emojiMaps`，`valine.json`配置方式可参考如下

> valine.json

```json
{ 
"tv_doge": "6ea59c827c414b4a2955fe79e0f6fd3dcd515e24.png",
"tv_親親": "a8111ad55953ef5e3be3327ef94eb4a39d535d06.png",
"tv_偷笑": "bb690d4107620f1c15cff29509db529a73aee261.png",
"tv_再見": "180129b8ea851044ce71caf55cc8ce44bd4a4fc8.png",
"tv_冷漠": "b9cbc755c2b3ee43be07ca13de84e5b699a3f101.png",
"tv_发怒": "34ba3cd204d5b05fec70ce08fa9fa0dd612409ff.png",
"tv_发財": "34db290afd2963723c6eb3c4560667db7253a21a.png",
"tv_可爱": "9e55fd9b500ac4b96613539f1ce2f9499e314ed9.png",
"tv_吐血": "09dd16a7aa59b77baa1155d47484409624470c77.png",
"tv_呆": "fe1179ebaa191569b0d31cecafe7a2cd1c951c9d.png",
"tv_嘔吐": "9f996894a39e282ccf5e66856af49483f81870f3.png",
"tv_困": "241ee304e44c0af029adceb294399391e4737ef2.png",
"tv_壞笑": "1f0b87f731a671079842116e0991c91c2c88645a.png",
"tv_大佬": "093c1e2c490161aca397afc45573c877cdead616.png",
"tv_大哭": "23269aeb35f99daee28dda129676f6e9ea87934f.png",
"tv_委屈": "d04dba7b5465779e9755d2ab6f0a897b9b33bb77.png",
"tv_害羞": "a37683fb5642fa3ddfc7f4e5525fd13e42a2bdb1.png",
"tv_尷尬": "7cfa62dafc59798a3d3fb262d421eeeff166cfa4.png",
"tv_微笑": "70dc5c7b56f93eb61bddba11e28fb1d18fddcd4c.png",
"tv_思考": "90cf159733e558137ed20aa04d09964436f618a1.png",
"tv_驚嚇": "0d15c7e2ee58e935adc6a7193ee042388adc22af.png"
} 

```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-valine.png)

> default_avatar

| 参数         | 效果                                                         |
| ------------ | ------------------------------------------------------------ |
| 留空（默认） | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000) |
| mp           | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=mp) |
| identicon    | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=identicon) |
| monsterid    | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=monsterid) |
| wavatar      | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=wavatar) |
| retro        | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=retro) |
| robohash     | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=robohash) |
| blank        | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=blank&f=y) |
| 404          | ![](https://www.gravatar.com/avatar/00000000000000000000000000000000?d=mp&f=y) |

<!-- endtab -->



<!-- tab Waline -->

Waline - 一款从 Valine 衍生的带后端评论系统。可以将 Waline 等价成 With backend Valine。

具体配置可参考 [waline 文档](https://waline.js.org/)

然后修改 `主题配置文件`:

```yaml
waline:
  serverURL: # Waline server address url
  bg: # waline background
  pageview: false
  option:
```

> 开启 pageview 后，文章页的访问人数将改为 Waline 提供，而不是 **不蒜子**

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-valine.png)

<!-- endtab -->

<!-- tab Utterances -->

与Gitalk一样，基于 GitHub issues 的评论工具。相对于Gitalk,其相对需要权限较少。具体配置可参考[Utterances](https://utteranc.es/)。

修改 `主题配置文件`:

```yaml
utterances:
  repo:
  # 可选 pathname/url/title/og:title
  issue_term: pathname
  # 可选 github-light/github-dark/github-dark-orange/icy-dark/dark-blue/photon-dark
  light_theme: github-light
  dark_theme: photon-dark
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-Utterances.png)

<!-- endtab -->

<!-- tab Facebook Comments -->

`Facebook Comments`是Facebook提供的评论插件，需要登陆Facebook才可评论。

修改 `主题配置文件`

```yaml
# Facebook Comments Plugin
# https://developers.facebook.com/docs/plugins/comments/
facebook_comments:
  app_id: 
  user_id: # optional
  pageSize: 10 # The number of comments to show
  order_by: social # social/time/reverse_time
  lang: en_US # Language en_US/zh_CN/zh_TW and so on
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-butterfly-docs-facebook-comments.png)

<!-- endtab -->

<!-- tab Twikoo -->

`Twikoo` 是一个简洁、安全、无后端的静态网站评论系统，基于[腾讯云开发](https://curl.qcloud.com/KnnJtUom)。

具体如何配置评论，请查看 [Twikoo文档](https://twikoo.js.org/quick-start.html#%E7%8E%AF%E5%A2%83%E5%88%9D%E5%A7%8B%E5%8C%96)

你只需要把获取到的 `环境ID (envId)` 填写到配置上去就行

修改 `主题配置文件`

```yaml
twikoo:
  envId:
  region:
  visitor: false
  option:
```

| 参数    | 解释                                                         |
| ------- | ------------------------------------------------------------ |
| envId   | 环境 ID                                                      |
| region  | 环境地域，默认为 ap-shanghai，如果您的环境地域不是上海，需传此参数 |
| visitor | 是否显示文章阅读数                                           |
| option  | 可选配置                                                     |

> 开启 visitor 后，文章页的访问人数将改为 Twikoo 提供，而不是 **不蒜子**

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-twikoo-comments.png)



<!-- endtab -->



<!-- tab Giscus -->

一个基于 *GitHub Discussions* 的评论

```yaml
# Giscus
# https://giscus.app/
giscus:
  repo:
  repo_id:
  category_id:
  theme:
    light: light
    dark: dark
  option:
```

具体配置的意思，请参考 Giscus 的[文档](https://giscus.app/zh-TW)

![](https://file.crazywong.com/gh/jerryc127/CDN@m2/img/hexo-theme-butterfly-docs-giscus.png)

<!-- endtab -->



<!-- tab remark42 -->

remark42 是一款只支持**私有部署**的评论

具体部署请查看 [Installation | Remark42](https://remark42.com/docs/getting-started/installation/)

```yaml
remark42:
  host: # Your Host URL
  siteId: # Your Site ID
  option:
```

![](https://cdn.jsdelivr.net/gh/jerryc127/CDN@m2/img/hexo-butterfly-docs-remark42.png)

<!-- endtab -->



<!-- tab artalk -->

artalk 是一款只支持**私有部署**的评论

具体部署请查看 [Artalk | 自託管评论系统](https://artalk.js.org/)

```yaml
artalk:
  server:
  site:
  visitor: false
  option:
```

![](https://cdn.jsdelivr.net/gh/jerryc127/CDN@m2/img/hexo-butterfly-docs-artalk.png)

<!-- endtab -->

{% endtabs %}

## 在线聊天

从3.0开始，Butterfly主题内置了多种在线聊天工具。你可以选择开启一种，方便你与访客的交流。

{% tabs online-chat %}

<!-- tab 通用设置 -->
这些工具都提供了一个按钮可以打开/关闭聊天窗口。
主题也提供了一个集合主题特色的按钮来替换这些工具本身的按钮，这个聊天按钮将会出现在右下角里。
你只需要把`chat_btn`打开就行。

修改 `主题配置文件`

```yaml
# Chat Button [recommend]
# It will create a button in the bottom right corner of website, and hide the origin button
chat_btn: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-button.png)

为了不影响访客的体验，主题提供一个`chat_hide_show`配置
设为`true`后，使用工具提供的按钮时，只有向上滚动才会显示聊天按钮，向下滚动时会隐藏按钮。

修改 `主题配置文件`

```yaml
# The origin chat button is displayed when scrolling up, and the button is hidden when scrolling down
chat_hide_show: true
```

{% note info %}
如果使用工具自带的聊天按钮，按钮位置可能会遮挡右下角图标，请配置`rightside-bottom`调正右下角图标位置
{% endnote %}
<!-- endtab -->

<!-- tab chatra -->
配置chatra,需要知道`Public key`

打开[chatra](https://chatra.com/)并注册账号。
你可以在`Preferences`中找到`Public key`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-chatra-id.png)

修改 `主题配置文件`

```yaml
# chatra
# https://chatra.io/
chatra:
  enable: true
  id: xxxxxxxx
```

`chatra`的样式你可以`Chat Widget`自行配置

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-chatra-ui-settings.png)

> Demo

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-chatra-ui-demo.png)

<!-- endtab -->

<!-- tab tidio -->
配置tidio,需要知道`Public key`

打开[tidio](https://www.tidio.com/)并注册账号。
你可以在`Preferences > Developer`中找到`Public key`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-tidio-id.png)

修改 `主题配置文件`

```yaml
# tidio
# https://www.tidio.com/
tidio:
  enable: true
  public_key: XXXX
```
`tidio`的样式你可以`Channels`自行配置

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-tidio-setting.png)

> Demo

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-tidio-demo.png)

<!-- endtab -->

<!-- tab daovoice -->
打开[daovoice](http://daovoice.io/)和注册账号
找到你的`app id`

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-daovoice-appid.png)

修改 `主题配置文件`

```yaml
# daovoice
# http://daovoice.io/
daovoice:
  enable: true
  app_id: xxxxx
```

可在`聊天设置`里配置聊天按钮等样式

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-daovoice-ui.png)

> Demo

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-daovoice-demo.png)

<!-- endtab -->

<!-- tab Gitter -->
打开[Gitter](https://gitter.im/)和注册账号
创建一个`community`或者`room`,复制名称到设置去

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-gitter-setting.png)

修改 `主题配置文件`

```yaml
# gitter
# https://gitter.im/
gitter:
  enable: true
  room: 
```

> Demo

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-chat-gitter-ui.png)

<!-- endtab -->



<!-- tab crisp -->

打开[crisp](https://crisp.chat/en/)并注册账号

找到需要的网站ID

```yaml
# crisp
# https://crisp.chat/en/
crisp:
  enable: false
  website_id: xxxxxxxx
```

![image-20200731183023863](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-buttefly-docs-chat-crisp.png)

![image-20200731183444781](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-crisp-demo.png)

<!-- endtab -->



<!-- tab messenger -->

messenger 为 Facebook 旗下的聊天服务

具体操作请查看 [Facebook 洽谈附加程序 - Messenger 平台](https://developers.facebook.com/docs/messenger-platform/discovery/facebook-chat-plugin/)

```yaml
messenger:
  enable: false
  pageID: xxxxx
  lang: zh_TW # Language en_US/zh_CN/zh_TW and so on
```



![](https://cdn.jsdelivr.net/gh/jerryc127/CDN@m2/img/hexo-butterfly-docs-messege.png)

<!-- endtab -->

{% endtabs %}

## 分享

> 只能选择一个分享服务商

{% tabs 分享 %}
<!-- tab AddThis -->

> 访问 [AddThis](https://www.addthis.com/) 官网
> 找到你的 pub-id

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-addthis.jpg)

修改 `主题配置文件`

```yaml
addThis:
  enable: true # or false
  pubid: 你的pub-id
```

<!-- endtab -->

<!-- tab Sharejs -->
如果你不知道 [sharejs](https://github.com/overtrue/share.js/)，看看它的说明。

修改 `主题配置文件`

```yaml
sharejs:
  enable: true
  sites: facebook,twitter,wechat,weibo,qq  #想要显示的内容
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-sharejs.png)
<!-- endtab -->

<!-- tab Addtoany -->
可以到[addtoany](https://www.addtoany.com/)查看使用说明

```yaml
addtoany:
  enable: true
  item: facebook,twitter,wechat,sina_weibo,facebook_messenger,email,copy_link
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-addtoany.png)

<!-- endtab -->
{% endtabs %}

## 搜索系统

{% tabs search %}
<!-- tab Algolia @fab fa-algolia -->

> 记得运行 hexo clean

> 如果你使用 [hexo-algoliasearch](https://github.com/LouisBarranqueiro/hexo-algoliasearch)，请记得配置 fields 参数的 `title`, `permalink` 和 `content`

1. 你需要安装 [hexo-algolia](https://github.com/oncletom/hexo-algolia)或 [hexo-algoliasearch](https://github.com/LouisBarranqueiro/hexo-algoliasearch). 根据它们的说明文档去做相应的配置。

2. 修改 `主题配置文件`

```yaml
algolia_search:
  enable: true
  hits:
    per_page: 6
```

<!-- endtab -->

<!-- tab 本地搜索@fas fa-search -->

> 记得运行 hexo clean

1. 你需要安装 [hexo-generator-search](https://github.com/PaicHyperionDev/hexo-generator-search)，根据它的文档去做相应配置

2. 修改 `主题配置文件`

```yaml
local_search:
  enable: false
  preload: false
  CDN:
```

| 参数    | 解释                                                         |
| ------- | ------------------------------------------------------------ |
| enable  | 是否开启本地搜索                                             |
| preload | 预加载，开启后，进入网页后会自动加载搜索文件。关闭时，只有点击搜索按钮后，才会加载搜索文件 |
| CDN     | 搜索文件的 CDN 地址（默认使用的本地链接）                    |

<!-- endtab -->

<!-- tab DocSearch @fas fa-search -->

DocSearch 是另一款由 algolia 提供的搜索服务，具体申请和使用请查看 [DocSearch 文档](https://docsearch.algolia.com/) 

```
docsearch:
  enable: false
  appId:
  apiKey:
  indexName:
  option:
```

| 参数      | 解释                                                         |
| --------- | ------------------------------------------------------------ |
| enable    | 【必须】是否开启 docsearch                                   |
| appId     | 【必须】你的 Algolia 应用 ID                                 |
| apiKey    | 【必须】你的 Algolia 搜索 API key                            |
| indexName | 【必须】你的 Algolia index name                              |
| option    | 【可选】其余的 docsearch 配置<br />具体配置可查[这里](https://docsearch.algolia.com/docs/api/) |

![DocSearch](https://file.crazywong.com/gh/jerryc127/CDN@m2/img/hexo-theme-butterfly-docs-docsearch.png)

<!-- endtab -->

{% endtabs %}

## 网站验证

如果需要搜索引擎收录网站，可能需要登录对应搜索引擎的管理平台进行提交。
各自的验证码可从各自管理平台拿到

修改 `主题配置文件`

```yaml
site_verification:
  # - name: google_site_verification
  #   content: xxxxxx
  # - name: baidu_site_verification
  #   content: xxxxxxx
```

## 分析统计

{% tabs 分析统计 %} 
<!-- tab 百度统计 -->
1. 登录百度统计的[官方网站](https://tongji.baidu.com/web/welcome/login)

2. 找到你百度统计的统计代码

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-baidu-tongji.jpg)

3. 修改 `主题配置文件`

```yaml
baidu_analytics: 你的代码
```

<!-- endtab -->

<!-- tab 谷歌分析 -->
1. 登录谷歌分析的[官方网站](https://www.google.com/analytics/)

2. 找到你的谷歌分析的跟踪 ID

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-google-analytics.jpg)

3. 修改 `主题配置文件`

```yaml
google_analytics: 你的代码 # 通常以`UA-`打头
```

<!-- endtab -->

<!-- tab Cloudflare分析 -->

1. 登录 Cloudflare 分析的[官方网站](https://www.cloudflare.com/zh-tw/web-analytics/)
2. 找到 `JavaScript 程序码片段`
3. 找到你的 `token`

![image-20201230195158742](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-cloudflare-analytics-id.png)

4. 修改 `主题配置文件`

   ```yaml
   # Cloudflare Analytics
   # https://www.cloudflare.com/zh-tw/web-analytics/
   cloudflare_analytics:
   ```

<!-- endtab -->

<!-- tab Microsoft Clarity -->

1. 登录 Clarity 的[官方网站](https://clarity.microsoft.com/)

2. 创建 `PROJECT`

3. 找到你的 `ID`![image-20201230195541443](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-clarity-id.png)

4. 修改 `主题配置文件`

   ```yaml
   # Microsoft Clarity
   # https://clarity.microsoft.com/
   microsoft_clarity:
   ```

<!-- endtab -->

{% endtabs %}

## 广告

{% tabs 广告 %}
<!-- tab 谷歌广告 -->
主题已集成谷歌广告（自动广告）

修改 `主题配置文件`

```yaml
google_adsense:
  enable: true
  auto_ads: true
  js: https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js
  client: # 填入个人识别码
  enable_page_level_ads: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-google-adsense1.png)
<!-- endtab -->

<!-- tab 手动广告配置 -->
主题预留了三个位置可供插入广告，分别为主页文章(每三篇文章出现广告)/aside公告之后/文章页打赏之后。
把html代码填写到对应的位置

修改 `主题配置文件`

```yaml
ad:
  index:
  aside:
  post:
```

例如:

```yaml
  index: <ins class="adsbygoogle" style="display:block" data-ad-format="fluid" data-ad-layout-key="xxxxxxxxxxxx" data-ad-client="ca-pub-xxxxxxxxxx" data-ad-slot="xxxxxxxxxx"></ins><script>(adsbygoogle=window.adsbygoogle||[]).push({})</script>
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-ad-post.png)
![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-ad-index.png)
<!-- endtab -->
{% endtabs %}

## Math 数学

{% tabs Math %}
<!-- tab MathJax -->

{% note warning flat %}
不要在标题里使用 mathjax 语法，toc 目录不一定能正确显示 mathjax，可能显示 mathjax 代码
{% endnote %}

> 建议使用 KaTex 获得更好的效果，下文有介绍！

修改 `主题配置文件`:

```yaml
mathjax:
  enable: true
  # true 表示每一页都加载mathjax.js
  # false 需要时加载，须在使用的Markdown Front-matter 加上 mathjax: true
  per_page: false
```

> 如果 `per_page` 设为 `true`,则每一页都会加载 Mathjax 服务。设为 `false`，则需要在文章 `Front-matter` 添加 `mathjax: true`,对应的文章才会加载 Mathjax 服务。

然后你需要修改一下默认的 `markdown` 渲染引擎来实现 MathJax 的效果。

查看: [hexo-renderer-kramed](https://www.npmjs.com/package/hexo-renderer-kramed)

以下操作在你 hexo 博客的目录下 (**不是 Butterfly 的目录**):

1. 安装插件

   ```bash
   npm uninstall hexo-renderer-marked --save
   npm install hexo-renderer-kramed --save
   ```

2. 配置 hexo 根目录的配置文件

   ```yaml
   kramed:
     gfm: true
     pedantic: false
     sanitize: false
     tables: true
     breaks: true
     smartLists: true
     smartypants: true
   ```

效果：

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-mathjax-2.jpg)

<!-- endtab -->

<!-- tab KaTeX -->

{% note warning flat %}
不要在标题里使用 KaTeX 语法，toc 目录不能正确显示 KaTeX。
{% endnote %}

首先禁用`MathJax`（如果你配置过 MathJax 的话），然后修改你的`主题配置文件`以便加载`katex.min.css`:

```yaml
katex:
  enable: true
  # true 表示每一页都加载katex.js
  # false 需要时加载，须在使用的Markdown Front-matter 加上 katex: true
  per_page: false
  hide_scrollbar: true
```

你不需要添加 `katex.min.js` 来渲染数学方程。相应的你需要卸载你之前的 hexo 的 markdown 渲染器，然后安装其它插件。

{% subtabs katex-plugins %}

<!-- tab hexo-renderer-markdown-it 【建议】 -->

卸载掉 marked 插件，安装 [hexo-renderer-markdown-it](https://github.com/hexojs/hexo-renderer-markdown-it)

```bash
npm un hexo-renderer-marked --save # 如果有安装这个的话，卸载
npm un hexo-renderer-kramed --save # 如果有安装这个的话，卸载

npm i hexo-renderer-markdown-it --save # 需要安装这个渲染插件
npm install katex @renbaoshuo/markdown-it-katex #需要安装这个katex插件
```

在 hexo 的根目录的 `_config.yml` 中配置

```yaml
markdown:
    plugins:
      - '@renbaoshuo/markdown-it-katex'
```

如需配置其它参数，请参考 [katex 官网](https://katex.org/docs/options.html)

<!-- endtab -->

<!-- tab hexo-renderer-markdown-it-plus -->

> 注意，此方法生成的 katex 没有斜体

卸载掉 marked 插件，然后安装新的`hexo-renderer-markdown-it-plus`:

```bash
# 替换 `hexo-renderer-kramed` 或者 `hexo-renderer-marked` 等hexo的markdown渲染器
# 你可以在你的package.json里找到hexo的markdwon渲染器，并将其卸载
npm un hexo-renderer-marked --save

# or

npm un hexo-renderer-kramed --save


# 然后安装 `hexo-renderer-markdown-it-plus`
npm i @upupming/hexo-renderer-markdown-it-plus --save
```

注意到 [`hexo-renderer-markdown-it-plus`](https://github.com/CHENXCHEN/hexo-renderer-markdown-it-plus)已经无人持续维护, 所以我们使用 [`@upupming/hexo-renderer-markdown-it-plus`](https://github.com/upupming/hexo-renderer-markdown-it-plus)。 这份 fork 的代码使用了 [`@neilsustc/markdown-it-katex`](https://github.com/yzhang-gh/markdown-it-katex)同时它也是 VSCode 的插件 [Markdown All in One](https://github.com/yzhang-gh/vscode-markdown)所使用的, 所以我们可以获得最新的 KaTex 功能例如 `\tag{}`。

你还可以通过 [`@neilsustc/markdown-it-katex`](https://github.com/yzhang-gh/markdown-it-katex)控制 KaTeX 的设置，所有可配置的选项参見 https://katex.org/docs/options.html。 比如你想要禁用掉 KaTeX 在命令行上输出的宂长的警告信息，你可以在根目录的 `_config.yml` 中使用下面的配置将 `strict` 设置为 false:

```yaml
markdown_it_plus:
  plugins:
    - plugin:
      name: '@neilsustc/markdown-it-katex'
      enable: true
      options:
        strict: false
```

当然，你还可以利用这个特性来定义一些自己常用的 `macros`。

<!-- endtab -->

{% endsubtabs %}



因为 KaTeX 更快更轻量，因此没有 MathJax 的功能多（比如右键菜单）。为那些使用 MathJax 的用户，主题也内置了 katex 的 [复制](https://github.com/KaTeX/KaTeX/tree/master/contrib/copy-tex) 功能。

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-katex.gif)

<!-- endtab -->
{% endtabs %}

## 美化/特效

### 自定义主题色

可以修改大部分UI颜色

修改 `主题配置文件`，比如：

> 颜色值必须被双引号包裹，就像`"#000"`而不是`#000`。否则将会在構建的时候报错！

```yaml
theme_color:
  enable: true
  main: "#49B1F5"
  paginator: "#00c4b6"
  button_hover: "#FF7242"
  text_selection: "#00c4b6"
  link_color: "#99a9bf"
  meta_color: "#858585"
  hr_color: "#A4D8FA"
  code_foreground: "#F47466"
  code_background: "rgba(27, 31, 35, .05)"
  toc_color: "#00c4b6"
  blockquote_padding_color: "#49b1f5"
  blockquote_background_color: "#49b1f5"
  scrollbar_color: "#49b1f5"
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-color_1.png)
![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-color_2.png)

### 网站背景

默认显示白色，可设置图片或者颜色

修改 `主题配置文件`

```yaml
# 图片格式 url(http://xxxxxx.com/xxx.jpg)
# 颜色（HEX值/RGB值/颜色单詞/渐变色)
# 留空 不显示背景
background:
```

*留意:* 如果你的网站根目录不是'/',使用本地图片时，需加上你的根目录。
例如：网站是 `https://yoursite.com/blog`,引用一张`img/xx.png`图片，则设置background为 `url(/blog/img/xx.png)
> background:'#49B202'

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-set-body-background-color.png)

> background: url(https://i.loli.net/2019/09/09/5oDRkWVKctx2b6A.png)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-set-body-background-img.png)

### footer 背景

修改 `主题配置文件`

```yaml
# footer是否显示图片背景(与top_img一致)
footer_bg: true
```

| 配置的值                                                     | 效果                         |
| ------------------------------------------------------------ | ---------------------------- |
| 留空/false                                                   | 显示默认的颜色               |
| img链接                                                      | 图片的链接，显示所配置的图片 |
| 颜色(<br>HEX值 - \#0000FF<br>RGB值 - rgb(0,0,255)<br>颜色单詞 - orange<br>渐变色 - linear-gradient( 135deg, #E2B0FF 10%, #9F44D3 100%)<br>） | 对应的颜色                   |
| true                                                         | 显示跟 top_img 一样          |

> true

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-footer-img.png)

### 打字效果

打字效果[activate-power-mode](https://github.com/disjukr/activate-power-mode)

修改 `主题配置文件`

```yaml
# Typewriter Effect (打字效果)
# https://github.com/disjukr/activate-power-mode
activate_power_mode:
  enable: true
  colorful: true # open particle animation (冒光特效)
  shake: true #  open shake (抖动特效)
  mobile: false
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-type-animation.gif)

### 背景特效
{% tabs 背景特效 %}
<!-- tab 静止彩带 -->
好看的彩带背景，可设置每次刷新更换彩带，或者每次点击更换彩带
修改 `主题配置文件`

```yaml
canvas_ribbon:
  enable: false
  size: 150
  alpha: 0.6
  zIndex: -1
  click_to_change: false  #设置是否每次点击都更换彩带
  mobile: false # false 手机端不显示 true 手机端显示
```

相关配置可查看[canvas_ribbon](https://github.com/hustcc/ribbon.js)

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-canvas-ribbon.png)
<!-- endtab -->

<!-- tab 动态彩带 -->
好看的彩带背景，会飘动
修改 `主题配置文件`

```yaml
canvas_fluttering_ribbon:
  enable: true
  mobile: false # false 手机端不显示 true 手机端显示
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-canvas-ribbon-piao.gif)
<!-- endtab -->

<!-- tab canvas-nest -->
修改 `主题配置文件`

```yaml
canvas_nest:
  enable: true
  color: '0,0,255' #color of lines, default: '0,0,0'; RGB values: (R,G,B).(note: use ',' to separate.)
  opacity: 0.7 # the opacity of line (0~1), default: 0.5.
  zIndex: -1 # z-index property of the background, default: -1.
  count: 99 # the number of lines, default: 99.
  mobile: false # false 手机端不显示 true 手机端显示
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-canvas_nest.gif)
<!-- endtab -->
{% endtabs %}

### 鼠标点击效果

{% tabs 鼠标点击效果 %}
<!-- tab 烟花 @fas fa-fire-alt -->

`zIndex`建议只在`-1`和`9999`上选
`-1` 代表烟火效果在底部
`9999` 代表烟火效果在前面

修改 `主题配置文件`

```yaml
fireworks:
  enable: true
  zIndex: 9999 # -1 or 9999
  mobile: false
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-firewall.gif)
<!-- endtab -->

<!-- tab 爱心 @fas fa-heart -->
修改 `主题配置文件`

```yaml
# 点击出现爱心
click_heart:
  enable: true
  mobile: false
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/click_love.gif)
<!-- endtab -->

<!-- tab 文字 @fab fa-amilia -->
修改 `主题配置文件`

```yaml
# 点击出现文字，文字可自行修改
ClickShowText:
  enable: false
  text:
    - I
    - LOVE
    - YOU
  fontSize: 15px
  random: false # 文字随机显示
  mobile: false
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/click_word.gif)
<!-- endtab -->
{% endtabs %}

### 页面美化

会改变ol、ul、h1-h5的样式

`field`配置生效的区域

- `post` 只在文章页生效
- `site` 在全站生效

修改 `主题配置文件`

```yaml
# 美化页面显示
beautify:
  enable: true
  field: site # site/post
  title-prefix-icon: '\f0c1'
  title-prefix-icon-color: "#F47466"
```

`title-prefix-icon`填写的是fontawesome的icon的Unicode数。
![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-fontwesome-unicode.png)

> 未开启美化

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-beautify.png)

> 开启美化

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-post-beautif.png)

### 自定义字体和字体大小

#### 全局字体

可自行设置字体的`font-family`
**如不需要配置，请留空**

修改 `主题配置文件`

```yaml
# Global font settings
# Don't modify the following settings unless you know how they work (非必要不要修改)
font:
  global-font-size:
  code-font-size:
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Helvetica Neue", Lato, Roboto, "PingFang SC", "Microsoft JhengHei", "Microsoft YaHei", sans-serif
  code-font-family: consolas, Menlo, "PingFang SC", "Microsoft JhengHei", "Microsoft YaHei", sans-serif
```
#### Blog 标题字体
可自行设置字体的`font-family`
**如不需要配置，请留空。**
**如不需要使用网络字体，只需要把font_link留空就行**

修改 `主题配置文件`

```yaml
# Font settings for the site title and site subtitle
# 左上角网站名字 主页居中网站名字
blog_title_font:
  font_link: https://fonts.googleapis.com/css?family=Titillium+Web&display=swap
  font-family: Titillium Web, 'PingFang SC', 'Hiragino Sans GB', 'Microsoft JhengHei', 'Microsoft YaHei', sans-serif
```

### 网站副标题

可设置主页中显示的网站副标题或者喜欢的座右铭。

修改 `主题配置文件`

```yaml
# 主页subtitle
subtitle:
  enable: false
  # Typewriter Effect (打字效果)
  effect: true
  startDelay: 300 # time before typing starts in milliseconds
  typeSpeed: 150 # type speed in milliseconds
  backSpeed: 50 # backspacing speed in milliseconds
  # loop (循环打字)
  loop: true
  # source 调用第三方服务
  # source: false 关闭调用
  # source: 1  调用一言网的一句话（简体） https://hitokoto.cn/
  # source: 2  调用一句网（简体） http://yijuzhan.com/
  # source: 3  调用今日诗詞（简体） https://www.jinrishici.com/
  # subtitle 会先显示 source , 再显示 sub 的内容
  source: false
  # 如果关闭打字效果，subtitle 只会显示 sub 的第一行文字
  sub:
    - 今日事&#44;今日毕
    - Never put off till tomorrow what you can do today
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-index-subtitle.gif)



### 主页top_img显示大小

> 适用于 版本号 >= V1.2.0

默认的显示为全屏。site-info的区域会居中显示

```yaml
# 主页设置
# 默认top_img全屏，site_info在中间
# 使用默认, 都无需填写（建议默认）
index_site_info_top: # 主页标题距离顶部距离  例如 300px/300em/300rem/10%
index_top_img_height:  #主页top_img高度 例如 300px/300em/300rem  不能使用百分比
```

注意：`index_top_img_height`的值不能使用百分比。
2个都不填的话，会使用默认值

举例，当

```yaml
index_top_img_height: 400px
```

效果

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-index-top-img-setting.png)



### 页面加载动画 preloader

当进入网页时，因为加载速度的问题，可能会导致 top_img 图片出现断层显示，或者网页加载不全而出现等待时间，开启preloader后，会显示加载动画，等页面加载完，加载动画会消失。

主题支持 pace.js 的加载动画，具体可查看 [pace.js](https://codebyzach.github.io/pace/)

配置 `butterly.yml`

```yaml
# 加载动画 Loading Animation
preloader:
  enable: false
  # source
  # 1. fullpage-loading
  # 2. pace (progress bar)
  source: 1
  # pace theme (see https://codebyzach.github.io/pace/)
  pace_css_url:
```

> fullpage-loading

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-preloader.gif)

## PWA

要为`Butterfly`配上 PWA 特性, 你需要如下几个步骤:

1. 打开 hexo 工作目录

2. `npm install hexo-offline --save` 或者 `yarn add hexo-offline`

3. 在根目录创建 `hexo-offline.config.cjs` 文件，并增加以下内容。

```js
// offline config passed to workbox-build.
module.exports = {
  globPatterns: ['**/*.{js,html,css,png,jpg,gif,svg,webp,eot,ttf,woff,woff2}'],
  // 静态文件合集，如果你的站点使用了例如 webp 格式的文件，请将文件类型添加进去。
  globDirectory: 'public',
  swDest: 'public/service-worker.js',
  maximumFileSizeToCacheInBytes: 10485760, // 缓存的最大文件大小，以字筛为单位。
  skipWaiting: true,
  clientsClaim: true,
  runtimeCaching: [ // 如果你需要加载 CDN 资源，请配置该选项，如果没有，可以不配置。
    // CDNs - should be CacheFirst, since they should be used specific versions so should not change
    {
      urlPattern: /^https:\/\/cdn\.example\.com\/.*/, // 可替换成你的 URL
      handler: 'CacheFirst'
    }
  ]
}
```

更多内容请查看 [hexo-offline](https://github.com/JLHwung/hexo-offline)的官方文档

4. 在`主题配置文件`中开启 pwa 选项。

```yaml
pwa:
  enable: true
  manifest: /img/pwa/manifest.json
  apple_touch_icon: /img/pwa/apple-touch-icon.png
  favicon_32_32: /img/pwa/32.png
  favicon_16_16: /img/pwa/16.png
  mask_icon: /img/pwa/safari-pinned-tab.svg
```

5. 在创建`source/`目录中创建`manifest.json`文件。

```json
{
    "name": "string",
    "short_name": "Junzhou",
    "theme_color": "#49b1f5",
    "background_color": "#49b1f5",
    "display": "standalone",
    "scope": "/",
    "start_url": "/",
    "icons": [
        {
          "src": "images/pwaicons/36.png",
          "sizes": "36x36",
          "type": "image/png"
        },
        {
            "src": "images/pwaicons/48.png",
          "sizes": "48x48",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/72.png",
          "sizes": "72x72",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/96.png",
          "sizes": "96x96",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/144.png",
          "sizes": "144x144",
          "type": "image/png"
        },
        {
          "src": "images/pwaicons/192.png",
          "sizes": "192x192",
          "type": "image/png"
        },
        {
            "src": "images/pwaicons/512.png",
            "sizes": "512x512",
            "type": "image/png"
          }
      ],
      "splash_pages": null
  }
```

你也可以通过 [Web App Manifest](https://app-manifest.firebaseapp.com/)快速创建`manifest.json`。（Web App Manifest 要求至少包含一个 512*512 像素的图标）

6. 可以通过`Chrome`插件`Lighthouse`检查 PWA 配置是否生效以及配置是否正确。
   
   - 打开博客页面
   - 启动`Lighthouse`插件 (`Lighthouse`插件要求至少包含一个 512*512 像素的图标)

关于 PWA（渐进式增强 Web 应用）的更多内容请参阅 [Google Tools for Web Developers](https://developers.google.com/web/tools/lighthouse/audits/address-bar)

## 字数统计

要为`Butterfly`配上字数统计特性, 你需要如下几个步骤:

1. 打开 hexo 工作目录

2. `npm install hexo-wordcount --save` or `yarn add hexo-wordcount`

3. 修改 `主题配置文件`:

```yaml
wordcount:
  enable: true
  post_wordcount: true
  min2read: true
  total_wordcount: true
```

![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-doc-word-count.png)
![](https://file.crazywong.com/gh/jerryc127/CDN/img/hexo-theme-butterfly-docs-wordcount-totalcount.png)

## 图片大图查看模式

{% note info %}

只能开启一个

{% endnote %}



{% tabs 图片大图查看模式 %}

<!-- tab 注意 -->

如果你并不想为某张图片添加大图查看模式，你可以使用 html 格式引用图片，并为图片添加 `no-lightbox` class 名。

<!-- endtab -->

<!-- tab fancybox -->
修改 `主题配置文件`

```yaml
# fancybox http://fancyapps.com/fancybox/3/
fancybox: true
```

![fancybox.gif](https://file.crazywong.com/gh/jerryc127/CDN/img/fancybox.gif)
<!-- endtab -->
<!-- tab medium_zoom -->
修改 `主题配置文件`

```yaml
medium_zoom: true
```

![medium_zoom.gif](https://file.crazywong.com/gh/jerryc127/CDN/img/medium_zoom.gif)
<!-- endtab -->
{% endtabs %}

## Snackbar 弹窗

Snackbar 弹窗,根据自己爱好开启

修改 `主题配置文件`

```yaml
# Snackbar 弹窗
# https://github.com/polonel/SnackBar
# position 弹窗位置
# 可选 top-left / top-center / top-right / bottom-left / bottom-center / bottom-right
snackbar:
  enable: true
  position: bottom-left
  bg_light: '#49b1f5' #light mode时弹窗背景
  bg_dark: '#2d3035' #dark mode时弹窗背景
```

> 未开启Snackbar

![snackbar_false.gif](https://file.crazywong.com/gh/jerryc127/CDN/img/snackbar_false.gif)

> 开启Snackbar

![snackbar_true.gif](https://file.crazywong.com/gh/jerryc127/CDN/img/snackbar_true.gif)

## 其它配置

### CSS 前缀

有些 CSS 并不是所有浏览器都支持，需要增加对应的前缀才会生效。

开启  `css_prefix` 后，会自动为一些 CSS 增加前缀。（会增加 20%的体積）

修改配置文件

```yaml
# Add the vendor prefixes to ensure compatibility
css_prefix: true
```

### Open Graph

在 `head` 里增加一些 meta 资料，例如缩略图、标题、时间等等。当你分享网页到一些平台时，平台会读取 Open Graph 的内容，展示缩略图，标题等等信息。

修改配置文件

```yaml
# Open graph meta tags
# https://developers.facebook.com/docs/sharing/webmasters/
Open_Graph_meta:
  enable: true
  option:
    # twitter_card:
    # twitter_image:
    # twitter_id:
    # twitter_site:
    # google_plus:
    # fb_admins:
    # fb_app_id:
```

### Instantpage

当鼠标悬停到链接上超过 65 毫秒时，Instantpage 会对该链接进行预加载，可以提升访问速度。

修改配置文件

```yaml
# https://instant.page/
# prefetch (预加载)
instantpage: true
```

### Pangu

> 如果你跟我一样，每次看到网页上的中文字和英文、数字、符号挤在一块，就会坐立难安，忍不住想在它们之间加个空格。这个插件正是你在网路世界走跳所需要的东西，它会自动替你在网页中所有的中文字和半形的英文、数字、符号之间插入空白。

修改配置文件

```YAML
# https://github.com/vinta/pangu.js
# Insert a space between Chinese character and English character (中英文之间添加空格)
pangu:
  enable: false
  field: post # site/post
```

`field`只支持两个参数，`post`(只在文章页生效)和`site`(全站生效)

## Pjax

当用户点击链接，通过ajax更新页面需要变化的部分，然后使用HTML5的pushState修改浏览器的URL地址。

这样可以不用重复加载相同的资源（css/js）， 从而提升网页的加载速度。

```yaml
# Pjax [Beta]
# It may contain bugs and unstable, give feedback when you find the bugs.
# https://github.com/MoOx/pjax
pjax: 
  enable: true
  exclude:
    - /music/
    - /no-pjax/
```
{% note info %}

对于一些第三方插件，有些并不支持 pjax 。
你可以把**网页**加入到 `exclude` 里，这个网页会被 pjax 排除在外。
点击该网页会重新加载网站

使用pjax后，一些自己DIY的js可能会无效，跳转页面时需要重新调用，请参考[Pjax文档](https://github.com/MoOx/pjax)
使用pjax后，一些个别页面加载的js/css，将会改为所有页面都加载

{% endnote %}

{% note warning %}

Butterfly的Pjax目前仍有一些问题，请留意

- 使用谷歌广告可能会报错（例如自动广告）

如果你在使用中发现问题，欢迎反馈Bugs

{% endnote %}

## Inject

> 2.3.0以上支持

如想添加额外的js/css/meta等等东西，可以在Inject里添加，支持添加到head(`</body>`标签之前)和bottom(`</html>`标签之前)。

请注意：以标准的html格式添加内容

例如

```yaml
inject:
  head:
  	- <link rel="stylesheet" href="/self.css">
  bottom:
  	- <script src="xxxx"></script>
```

*留意:* 如果你的网站根目录不是'/',使用本地图片时，需加上你的根目录。
例如：网站是 `https://yoursite.com/blog`,引用`css/xx.css`，则设置为`<link rel="stylesheet" href="/blog/css/xx.css">`

## CDN

配置文件中最后一部分CDN，里面是主题所引用到的文件，可自行配置CDN。（非必要请勿修改，配置后请确认链接是否能访问）

```yaml
CDN:
  # The CDN provider of internal scripts (主题内部 js 的 cdn 配置)
  # option: local/jsdelivr/unpkg/cdnjs/custom
  # Dev version can only choose. ( dev版的主题只能设置为 local )
  internal_provider: local

  # The CDN provider of third party scripts (第三方 js 的 cdn 配置)
  # option: local/jsdelivr/unpkg/cdnjs/custom
  # when set it to local, you need to install hexo-butterfly-extjs
  third_party_provider: jsdelivr

  # Add version number to CDN, true or false  
  version: false

  # Custom format
  # For example: https://cdn.staticfile.org/${cdnjs_name}/${version}/${min_cdnjs_file}
  custom_format:

  option:
    # main_css:
    # main:
    # utils:
    # translate:
    # local_search:
    # algolia_js:
    # algolia_search_v4:
    # instantsearch_v4:
    # pjax:
    # gitalk:
    # gitalk_css:
    # blueimp_md5:
    # valine:
    # disqusjs:
    # disqusjs_css:
    # twikoo:
    # waline_js:
    # waline_css:
    # sharejs:
    # sharejs_css:
    # mathjax:
    # katex:
    # katex_copytex:
    # mermaid:
    # canvas_ribbon:
    # canvas_fluttering_ribbon:
    # canvas_nest:
    # lazyload:
    # instantpage:
    # typed:
    # pangu:
    # fancybox_css_v4:
    # fancybox_v4:
    # medium_zoom:
    # snackbar_css:
    # snackbar:
    # activate_power_mode:
    # fireworks:
    # click_heart:
    # ClickShowText:
    # fontawesomeV6:
    # flickr_justified_gallery_js:
    # flickr_justified_gallery_css:
    # aplayer_css:
    # aplayer_js:
    # meting_js:
    # prismjs_js:
    # prismjs_lineNumber_js:
    # prismjs_autoloader:
```



| 参数                 | 解释                                                         |
| -------------------- | ------------------------------------------------------------ |
| internal_provider    | 主题内部文件<br />可选 local/jsdelivr/unpkg/cdnjs/custom<br />lcoal 为本地加载，custom 为自定义格式，需配置 `custom_format`<br />**注意:** 如果使用的是 Dev 版，只能设置为 local |
| third_party_provider | 第三方文件<br />可选 local/jsdelivr/unpkg/cdnjs/custom<br />lcoal 为本地加载，custom 为自定义格式，需配置 `custom_format`<br />**注意:**  如果你选择 local 需要安装 `hexo-butterfly-extjs`插件 |
| version              | true/false 为 cdn 加上指定版本号                             |
| custom_format        | 自定义格式                                                   |
| option               | 你可以在这里更换部分文件,会覆盖原有的配置                    |

### version

如需修改版本号，可修改`主题目录`的 'plugins.yml' 中对应插件的 version

请确保你修改的版本号，你所使用的 cdn 有**收录**

### custom_format

提供以下参数

| 参数           | 解释                               |
| -------------- | ---------------------------------- |
| name           | npm 上的包名                       |
| file           | npm 上的文件路徑                   |
| min_file       | npm 上的文件路徑（压缩过的文件）   |
| cdnjs_name     | cdnjs 上的包名                     |
| cdnjs_file     | cdnjs 上的文件路徑                 |
| min_cdnjs_file | cdnjs 上的文件路徑（压缩过的文件） |
| version        | 插件版本号                         |

部分可用的第三方 CDN 列表

> 请确保你选择的 CDN 有收录主题使用的第三方插件

| 提供商                                              | 格式                                                         | 备注        |
| --------------------------------------------------- | ------------------------------------------------------------ | ----------- |
| [Staticfile（七牛云）](https://www.staticfile.org/) | https://cdn.staticfile.org/${cdnjs_name}/${version}/${min_cdnjs_file} | 同步  cdnjs |
| [BootCDN](https://www.bootcdn.cn/)                  | https://cdn.bootcdn.net/ajax/libs/${cdnjs_name}/${version}/${min_cdnjs_file} | 同步  cdnjs |
| [Baomitu（360）](https://cdn.baomitu.com/)          | 最新版本： https://lib.baomitu.com/${cdnjs_name}/latest/${min_cdnjs_file}<br />指定版本： https://lib.baomitu.com/${cdnjs_name}/${version}/${min_cdnjs_file} | 同步  cdnjs |
| Elemecdn                                            | 最新版本： https://npm.elemecdn.com/${name}@latest/${file}<br />指定版本： https://npm.elemecdn.com/${name}@${version}/${file} | 同步  npm   |

{% btn '/posts/98d20436/',❓ Butterfly 安装文档(五) 主题问答,far fa-hand-point-right,block green right larger %}

