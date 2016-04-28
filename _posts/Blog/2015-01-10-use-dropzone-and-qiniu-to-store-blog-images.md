---
layout: post
title: 使用Dropzone和七牛云存储来优化博客图床
category: Blog
tags: Blog
keywords: Dropzone,Qiniu,七牛,博客
description: 
---
> 之前在 GitHub 看到 [闫肃的博客](http://yansu.org)推荐七牛帐号云存储＋Dropzone工具实现快速上传图片获得公共链接的方法，Mac OS X 系统升级到 10.11.4 以后，配置会出现很多错误问题，造成上传报错。下面会告诉大家解决方法。

#####下面是我使用 Dropzone 插件启动ImageOptim 压缩图片，再使用 Dropzone 七牛插件上传图片和获得URL的操作，整个操作不超过3秒。

![七牛操作流](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone3.gif)

## 设置七牛帐号

> [七牛](http://www.qiniu.com)是国内口碑不错的一个云存储为主的公司。它的特点应该就在图片存储上，有非常方便的上传SDK和图片处理流，用来作为博客图床非常合适，而且价格不贵，每月有免费的10G流量。

1. 去七牛注册帐号

    刚刚创建的帐号是测试帐号，完成个人认证就可以成为标准帐号，获得10G的存储空间和各10G的上传下载流量。

    ![标准帐号](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00001.jpg)

2. 创建一个空间

    创建空间也比较容易，记得选择公开空间。
    
    ![创建空间](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00002.jpg)
    
## 设置Dropzone[^1]

> 是我很早就非常喜欢的一个软件。它通过拖拽的方式，增强了文件的处理流程。一直懒得给它开发插件，没想到七牛的SDK如此好用，所以今天折腾了一下搞定了。

1. 下载软件

    这个软件可以在App Store上直接购买，但是买到的是功能受限的，它不能操作外部文件。不过没有关系，再从官网上下载非沙箱版本，然后覆盖掉Application文件夹下的即可。
    
    
2. 安装**Qiniu插件**[^2]

    下载后的是一个zip包，把这个包解压以后双击安装即可。
    
3. 安装Qiniu的Ruby库

    ```
    sudo gem install qiniu
    ```
   **OS X 10.11 后的新系统安装报错？查看解决办法。**
   
   
   - 重启 Mac ，按住 Command＋R进入恢复模式。在 实用工具 内找到 终端 启动运行输入

   ```
   csrutil disable; reboot
   ```
   - 终端显示系统保护被关闭字样，并且重新启动。回到系统后，安装 Qiniu 的 Ruby 库。
   
   - 安装完成后建议用户重复1部分操作到恢复模式的终端输入
   
   ```
   csrutil enable; reboot
   ```
   - 开启 Rootlees 安全机制，避免系统安全风险。

4. 启用插件

    从增加列表中选择我们安装好的七牛插件。

    ![启用插件](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00003.jpg)
    
    然后填写配置：
    
    - server: 七牛上的空间名
    - username: 七牛的access_key
    - password: 七牛的secret_key    
    - remote path(可选): 本地同步图片的目录，如果你希望本地也存一份图片，选一个地址即可
    - root url: 七牛的公共链接根目录
    
    ![access key](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00004.jpg)

    ![root url](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00005.jpg)
    
###上传报错问题解决###
![上传报错](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00007.jpg)

报错主要分为两种：

#### ruby 路径设置错误。
1. 检查系统 ruby 路径，终端输入：

   ```
   which ruby
   ```	
   
   终端返回 ruby 路径： `/usr/local/bin/ruby` 或 `/usr/bin/ruby`
2. 修改 Dropzone - `Qiniu 插件`设置：
Dropzone - Preferences - User Actions 
   
   选择 Qiniu 1.0 - ➡️Reveal 。

![Qiniu插件设置](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00008.jpg)

   3.选择 `Qiniu.dzbundle` 右键 `显示包内容` 。

   4.文本打开 `action.rb` 找到 `RubyPath:` 修改成第一步终端得到的 ruby 路径。

![Qiniu插设置](http://7xi7a2.com1.z0.glb.clouddn.com/Dropzone00010.jpg)


#### Qiniu ruby包安装失败

找到原因，重新安装` Qiniu ruby包`。


## ImageOptim[^4] 压缩图片

利用 Dropzone 还有很多可利用的技巧，例如增加一个 ImageOptim 应用来压缩图片，然后再进行上传。

下载后拖拽到应用程序文件夹内，在 Dropzone 内 Open Applications 选中 ImageOptim 。ImageOptim 出现在 Dropzone 快捷栏，直接拖拽图片上去，就能压缩图片。

[^2]: [Qiniu 插件下载](7xi7a2.com1.z0.glb.clouddn.com/Qiniu.dzbundle.zip)
[^4]: ImageOptim[下载地址](http://www.weiosx.com/show-50-311-1.html)
[^1]: Dropzone[试用版下载](http://www.weiosx.com/show-70-8668-1.html/)；Dropzone[官网](https://aptonic.com/dropzone3/)售价10美金；Dropzone[Mac App Store](https://itunes.apple.com/cn/app/dropzone-3/id695406827?mt=12) 售价¥68元人民币
