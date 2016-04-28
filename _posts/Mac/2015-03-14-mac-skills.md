---
layout: post
title: Mac系统优化
category: Mac
tags: Mac
keywords: Mac,优化,Dashboard,
description: 
---

> Mac OS X 系统现在已经更新到了 Yesemite 10.10.2 ,对电脑配置要求非常高，我们可以关闭一些系统无关紧要的项目来降低内存消耗，从而提升性能。![图片标题](http://image.weiosx.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-14%20%E4%B8%8A%E5%8D%881.06.40.jpg)

## **关闭 Dashboard**

##### 如果一直不使用 Dashboard[^1] 功能，那么用终端命令停用它以帮助用户以节省空间。 
   
[^1]: 是苹果公司 Mac OS X v10.4 Tiger 操作系统中的应用程式，是将多个仪表、图表、报表等内容整合在一个页面上进行显示的仪表盘工具。  

   - **关闭**
   
```
defaults write com.apple.dashboard mcx-disabled -boolean YES
killall Dock
```

   - **开启**
   
```
defaults write com.apple.dashboard mcx-disabled -boolean NO
killall Dock
```
