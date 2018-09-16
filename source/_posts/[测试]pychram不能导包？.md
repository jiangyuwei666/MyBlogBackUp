---
title: 【测试】Pychram不能导包？
tags:
  - 小东西
  - trap
  - python
toc: true
comment: true
---
### 震惊，为什么会这样
问题是这样发生的:
</br>我是直接用Anaconda直接装的Python3.6
<!--more-->
</br>因为爬虫需要很多库都在里面，直接一键全部安装
</br>安装完成了pycharm的时候就想试试环境是否搭建好了导入了requests库

```python
from lxml import etree
#这是对网页XML结构进行解析的模块
```
可是发现报错了，导不进去，刚开始以为是没有装这个模块
</br>到cmd里去下载

![cmd下载lxml](http://ww1.sinaimg.cn/large/006BhB5Ogy1fvb7oej6xdj30xz0hrmxy.jpg)

显示的已经安装了,只是叫我更新Anaconda，怀疑是Python没有安排上
</br>又去检查Python

![检查Python](http://ww1.sinaimg.cn/large/006BhB5Ogy1fvb7ofe9mkj30xz0hrq3r.jpg)

而且发现lxml也能导入

最后排查出来是Python的路径没有放对

![Python路径检查](http://ww1.sinaimg.cn/large/006BhB5Ogy1fvb7oejp34j30zp0opabm.jpg)

这里我们创建这个项目的时候，不知道什么原因它重新在一个目录里创建了一个python？显示是这么显示的。
</br>而且我记得以前创建一个项目的时候里面是什么东西都没有，现在多了个这个东西

![多的文件](http://ww1.sinaimg.cn/large/006BhB5Ogy1fvb7oeibdvj30dc07ijrp.jpg)

最后在正确的导入了Python后，打开的项目是这样的

![正常情况](http://ww1.sinaimg.cn/large/006BhB5Ogy1fvb7oel0y1j31hc0sm0up.jpg)

所以第一次使用Pycharm的时候出现这种错误的时候可以检查一下python的路径是否放对了1