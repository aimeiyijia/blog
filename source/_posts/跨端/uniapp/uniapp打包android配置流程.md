---
title: uniapp打包android配置流程
comments: false
abbrlink: 116f06eb
date: 2023-07-21 14:54:49
tags:
categories:
keywords:
description:
top_img:
cover:
---

## 下载必要的工具

#### 下载 android studio

[官方下载地址](https://developer.android.com/studio/install?hl=zh-cn)，选择操作系统对应的版本

#### 下载 jdk-8u202

{% note danger flat %}
jdk8 小版本不能大于**202**
{% endnote %}

[华为云 java 镜像地址](https://mirrors.huaweicloud.com/java/jdk/8u202-b08/)，选择操作系统对应的版本，如有需要自行配置环境变量

安装完成后打开命令行工具，输入`java -version`，查看版本是否是**1.8.0_202**

```bash
➜ java -version
java version "1.8.0_202"
Java(TM) SE Runtime Environment (build 1.8.0_202-b08)
Java HotSpot(TM) 64-Bit Server VM (build 25.202-b08, mixed mode)
➜
```

## 生成证书

#### 生成

```bash
命令格式:

keytool -genkey -alias 证书别名 -keyalg RSA -keysize 2048 -validity 证书的有效期 -keystore 证书文件名
```

{% note warning modern %}

1. 生成过程中会提示输入证书密码，请牢记，很重要。
2. 除第一个问题、最后一个问题需要输入外，均可以使用默认值，一路enter即可。

2. 最后一个问题是询问你是否正确，此时需要手动输入**是**。

{% endnote %}

#### 举例

以生成管理人平台app（manager-app）证书为例

```bash
keytool -genkey -alias manager-app -keyalg RSA -keysize 2048 -validity 36500 -keystore manager-app.keystore
```



### 查看

## 生成离线打包 Key

## 开始配置

[uniapp 离线打包流程](https://segmentfault.com/a/1190000040092971)
