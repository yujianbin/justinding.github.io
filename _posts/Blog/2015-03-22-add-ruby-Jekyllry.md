---
layout: post
title: Jekyllrb环境配置 ruby配置
category: Blog
tags: [Jekyll , ruby]
description: Jekyllrb环境配置
---

> ![jekyllrb](http://7xi7a2.com1.z0.glb.clouddn.com/Pasted%20Graphic.tiff)
**[jekyllrb](http://jekyllrb.com/docs/installation/):
将您的纯文本转换为静态的网站和博客.因为国内相关资料很久没有更新了,下文详细说明配置问题.**
  

## 1,安装xcode,然后软件更新一些命令支持,或打开终端输入:
  
  
```  
xcode-select --install
```

![xcode](http://7xi7a2.com1.z0.glb.clouddn.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-21%20%E4%B8%8A%E5%8D%882.12.26-1.jpg)

## 2,1获取Homebrew.  
![获取Homebrew](http://7xi7a2.com1.z0.glb.clouddn.com/Homebrew201600000.jpg)
  
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
``` 

## 2,2 [Ruby](https://www.ruby-lang.org/zh_cn/)安装也可以用Homebrew安装输入以下代码:
![Ruby](http://7xi7a2.com1.z0.glb.clouddn.com/Ruby2016000001.jpg)
  
```
brew install ruby
```

## 2.3 [RubyGems](https://rubygems.org/pages/download)下载安装：
1. 点击上面链接进入到官网，从顶部的链接下载压缩包；
2. 解压缩到指定文件夹，并通过 “cd” 指令进入到该文件夹；
3. “ruby setup.rb” 使用该命令安装（可能需要管理员权限，使用sudo）
4. 更多帮助请参考 “ruby setup.rb --help”

#### 升级、更新
```
$ gem update --system            #可能需要管理员权限
```
#### 注意：
RubyGems v1.1 和 v1.2 在升级方面有点问题，没有安装 rubygems-update 。如果看到提示 “Nothing to update” ，你将需要执行下面的命令来安装。如果你已经安装了一个比较旧版本的 RubyGems，你仍可以通过下面的指令升级：

```
$ gem install rubygems-update            #可能需要管理员权限
$ update_rubygems                        #这里也一样
```
## 2,4 安装:"[NodeJS](https://nodejs.org/en/)"  
![NodeJS](http://7xi7a2.com1.z0.glb.clouddn.com/NodeJS20160000001.jpg)

### 可以下载两个版本安装：
1. **[v4.4.3LTS](https://nodejs.org/dist/v4.4.3/node-v4.4.3.pkg)推荐**
2. **[v6.0.0 Current](https://nodejs.org/dist/v6.0.0/node-v6.0.0.pkg)**

## 2,5 安装:[Python](https://www.python.org/downloads/)
![Python](http://7xi7a2.com1.z0.glb.clouddn.com/Python2016000001.jpg)


### Python 下载地址：

1. [Python 3.5.1](https://www.python.org/ftp/python/3.5.1/python-3.5.1-macosx10.6.pkg)推荐
2. [Python 2.7.11](https://www.python.org/ftp/python/2.7.11/python-2.7.11-macosx10.6.pkg)

## 3 安装jekyllrb

**用RubyGems安装Jekyllry**  
  

```  
$ gem install jekyll 
```   


**下面命令如果出现:
ERROR: While executing gem ... (Gem::FilePermissionError)  
只要先在终端运行下面代码就修复了**


```  
gem update --system
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem sources -l
*** CURRENT SOURCES ***
https://ruby.taobao.org
请确保只有 ruby.taobao.org  
```    

## 4 jekyllrb 生成静态页面并访问
* 生成静态页面

```
 jekyll new myblog
```

* 启动服务

```
$ cd myblog/             cd 到博客文件夹
$ jekyll server
```

* 访问站点

```
http://127.0.0.1:4000/
```
