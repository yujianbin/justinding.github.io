---
layout: post
title: Mac OS X 系统移植游戏运行的注意事项
category: Mac
tags: Mac, 移植游戏, XQuartz, Wine
keywords: Mac,移植游戏,XQuartz,Wine

description: 
---
> 谁说 Mac 设备游戏少，玩游戏效果差？WeiOSX团队移植了一些经典游戏，兼容性越来越稳定，希望Mac用户喜欢。这次测试的设备是 2014年末的 MacBook Air 13寸 低配。运行经典游戏 《鬼泣三－但丁觉醒特别中文版》for Mac
> ![配置](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%885.07.26.jpg)


### 安装必备组件

>**从 Windows 系统移植过来的游戏，基本上都需要 XQuartz 的环境支持，XQuartz 是玩移植游戏必装的组件。**

1. **确认XQuartz安装状态**    
前往－应用程序－实用工具－运行 X11  
如果是以下的画面，可以确定 Mac 设备没有安装 XQuartz。
![XQuartz](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%884.14.08111.jpg)
2. 点击“继续”,来到苹果官网 《关于 X11 和 OS X》 的说明页面，点击第一段话的超链接。 [http://xquartz.macosforge.org](http://xquartz.macosforge.org)前往 xquartz 官方网站。
![macosforge.org](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%884.27.14111.jpg)

3. 下载 XQuartz-2.7.9.dmg  
 如果下载速度太慢，可以前往 **[WeiOSX.com 下载](http://www.weiosx.com/show-75-8640-1.html)**
![XQuartz-2.7.9.dmg](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%884.20.48111.jpg)

4. 安装 XQuartz  
安装会要求重启系统完成设置。重启后组件安装完成。


### 安装游戏

打开DMG镜像，拖拽游戏app到应用程序文件夹内。
![DMG安装](http://7xi7a2.com1.z0.glb.clouddn.com/DMG.gif)
这步如果报错，两个原因：下载的时候丢失了数据，DMG镜像不完整。或者服务器上的DMG镜像出现了问题，这种情况请及时通知我们。

### 运行游戏

![运行](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%885.04.55.png)

### 调整分辨率
* 游戏内调整  
![游戏内调整](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%885.08.55.png)

* 游戏包内查找有没有设置程序
应用程序文件夹－选择游戏－右键－显示包内容
做演示的这款由 WeiOSX团队移植的 《鬼泣三－但丁觉醒特别中文版》有很多分辨率调整程序，现在使用的设备是 MacBook Air 13寸，2014年末款。支持最大分辨率 1440x900；因为要录制，我选择 1280x800 进入游戏。  
![分辨率](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%88%86%E8%BE%A8%E7%8E%87.gif)

* 完美运行。

* 游戏包内除了分辨率调整程序，还有手柄设置程序
![手柄设置工具](http://7xi7a2.com1.z0.glb.clouddn.com/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202016-05-06%20%E4%B8%8B%E5%8D%885.29.30.png)

##### 希望简单的使用教程对你有帮助。有什么问题请到 WeiOSX.com 反馈。