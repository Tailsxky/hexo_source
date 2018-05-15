---
title: Ubuntu下的NodeJs升级
date: 2018-05-15 17:28:09
tags: NodeJs
category: NodeJs
---

今天在Ubuntu虚拟机下面用Nodejs做一个博客系统，测试时发现Node不支持ES的async特性，上网一查发现是该版本不支持。

<!--more-->

在网上查了升级办法，可以用Node Binary管理模块"n"。

1. 首先安装n模块： npm install -g n；

2. 然后便可以升级到指定版本，如 n 6.9.1, 或者安装最新稳定版本 n stable, 同时也可以使用 n ls查看可升级的版本；

3. 之后在查看node -v 就可以见到node已经升级到指定版本；

如果发现升级之后版本还是没有改变，可能的原因是版本没有安装的正确的路径，在我的机器上node是安装在/usr/local/bin/node，因此我直接进入该文件夹，进行上述的升级操作，就可以了。
