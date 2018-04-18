---
layout: post
title: 关于如何在Hexo上添加原生HTML页面
date: 2018-03-22 15:24:30
category: 关于Hexo
tag: Hexo
---

之前写了一个简单的HTML格式的简历页面托管在github上，现在用了这个域名来托管了自己新建的博客，就在想能不能把原生的CV页面也做成一个子页面；

<!--more-->

由于Hexo原生是用Markdown进行渲染的，所以这里直接加上原生的HTML页面无法成功渲染，再加上我想把页面加到[about](https://tailsxky.github.io/about/)中直接显示，而不是子级页面，参考了许多别人的方法，最终解决如下：

1. 首先hexo new page "about"， 在source folder下面会生成一个about文件夹，about文件夹下面会有一个index的文件夹和一个index.md文件，而index文件夹下还有一个index.html子文件；

2. 将CV的HTML内容替换index.html文件，在文件头部加上layout: false阻止渲染；

3. 其实完成这个步骤以后，清除缓存启动hexo server正常情况下就能访问了，只不过地址为localhost/about/index/index.html；

4. 如何直接打开about页面就能显示呢，尝试了各种方法最终发现直接删掉index文件夹，把index.html直接放在about文件夹下就可以正常使用；

5. 在deploy的时候偶尔会不成功导致打开是空白的页面，可以上github上看看源文件，如果文件没问题的话就肯定没问题了；

这种方法加入的HTML文件暂时使用的内联加载css和外部加载js，不知道Hexo能否保存调用css和js文件，需要再研究；

参考： [博客中跳过渲染，创建自定义网页](https://login926.xyz/%e5%9c%a8-hexo-%e5%8d%9a%e5%ae%a2%e4%b8%ad%e8%b7%b3%e8%bf%87%e6%b8%b2%e6%9f%93%ef%bc%8c%e5%88%9b%e5%bb%ba%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bd%91%e9%a1%b5)
