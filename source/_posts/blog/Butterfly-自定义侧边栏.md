---
title: Butterfly 自定义侧边栏
tags:
  - 教程
  - Hexo
  - 主题
  - butterfly
categories: 进阶教程
keywords: 'hexo,butterfly,主题,doc,教程,文档'
description: 自定义侧侧边栏
cover: 
abbrlink: ea33ab97
date: 2022-03-24 15:55:42
comments: false
---

{% note info %}

适用于 >= 3.8.0

{% endnote %}

侧边栏现在支持自定义了，可以添加自己喜欢的 widget。

可添加自己的 widget，也可以对现有的 widget 进行排序（`博客资料`和 `公告`这两个固定，其它的能排序）

##  widget 排序

只需要配置 `sort_order`就行。（使用了 `Flex` 布局的 `order` 属性，具体可查看 [mozilla 文档](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Ordering_Flex_Items)。简单来講，就是配置**数字**来实现排序，如果不配置，则默认为 0。数字越小，排序越靠前。

```yaml
aside:
 ...
  card_recent_post:
    sort_order: # Don't modify the setting unless you know how it works
  card_categories:
    sort_order: # Don't modify the setting unless you know how it works
  card_tags:
    sort_order: # Don't modify the setting unless you know how it works
  card_archives:
    sort_order: # Don't modify the setting unless you know how it works
  card_webinfo:
    sort_order: # Don't modify the setting unless you know how it works

newest_comments:
  enable: true
  sort_order: # Don't modify the setting unless you know how it works
```

## 自定义 widget

如果你想添加自己的内容到侧边栏去，你可以自定义。

### 创建 widget.yml

在Hexo博客目录中的`source/_data`（如果没有 _data 文件夹，请自行创建），创建一个文件 `widget.yml`

### 格式

```yaml
top:
  - class_name:
    id_name:
    name:
    icon:
    html:

bottom:
  - class_name:
    id_name:
    name:
    icon:
    order:
    html:
```

> 参数详解

**top**:  创建的 widget 会出现在非 sticky 区域（即所有页面都会显示)

**bottom**:  创建的 widget 会出现在 sticky 区域（除了文章页都会显示)

| 参数       | 解释                                    |
| ---------- | --------------------------------------- |
| class_name | 所创建的 widget  父类 class 名 （可选） |
| id_name    | 所创建的 widget  父类 id 名（可选）     |
| name       | 所创建的 widget 标题                    |
| icon       | 所创建的 widget 图标                    |
| order      | 所创建的 widget 排序 （可选）           |
| html       | 所创建的 widget 相关代码                |

![image-20201230223506507](https://file.crazywong.com/gh/jerryc127/CDN/img/adside-diy-parameter.png)

生成的 代码 为

```html
<div class="card-widget 所写的 class_name" id="所写的 id_name" style="order: 所写的 order">
    <div class="item-headline">
        <i class="所写的 icon"></i>
        <span>所写的 name</span>
    </div>
    <div class="item-content">
        所写的 html
    </div>
</div>
```

如果你需要对添加的 widget 进行 UI 调整，请自行添加 css 到 inject 去。

### 例子

以  [访客地图](https://clustrmaps.com/profile/1b7ep/widget/code/globe) 为例子

1. 获取访客地图的 html 代码

   ```html
   <script type="text/javascript" id="clstr_globe" src="//clustrmaps.com/globe.js?d=5V2tOKp8qAdRM-i8eu7ETTO9ugt5uKbbG-U7Yj8uMl8"></script>
   ```

2. 创建 widget.yml

   ```yaml
   bottom:
       - class_name: user-map
         id_name: user-map
         name: 访客地图
         icon: fas fa-heartbeat
         order:
         html: '<script type="text/javascript" id="clstr_globe" src="//clustrmaps.com/globe.js?d=5V2tOKp8qAdRM-i8eu7ETTO9ugt5uKbbG-U7Yj8uMl8"></script>'
   ```

3. 运行 hexo

   ![image-20201230224442356](https://file.crazywong.com/gh/jerryc127/CDN/img/aside-diy-sample.png)



