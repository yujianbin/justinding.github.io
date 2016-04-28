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

## 2,获取Homebrew.  

  
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

![图标2](http://7xi7a2.com1.z0.glb.clouddn.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-21%20%E4%B8%8A%E5%8D%882.19.43-1.jpg)  

## 3,1 [Ruby](https://www.ruby-lang.org/zh_cn/)安装也可以用Homebrew安装输入以下代码:
  
```
brew install ruby-install
```

## 3,2 安装Jekyllry最好的方式是通过RubyGems的  
  

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
**用RubyGems安装Jekyllry**  
  

```  
gem install jekyll  
```   
  
## 3,3 支持列表红宝石和他们的主要版本：  
  
```
brew tap homebrew/versions 
```    


## 4,1 从 [Ruby](https://github.com/postmodern/ruby-install#readme) 下载下来并安装：
![图片4](http://7xi7a2.com1.z0.glb.clouddn.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-21%20%E4%B8%8A%E5%8D%882.22.39-1.jpg)    

```
brew install ruby-install --HEAD
```

```
gem install jekyll
```  
  
```
ruby-install
```

**下面命令如果出现:  
ERROR: While executing gem ... 
(Gem::FilePermissionError)  
只要先在终端运行下面代码就修复了**
  
## 4,2用通过 **Homebrew** 安装GCC：
  

```
brew tap homebrew/versions
brew install gcc48
ruby-install ruby 1.9.3-p125 -- CC=gcc-4.8
```
  
**下面命令如果出现:
ERROR: While executing gem ... (Gem::FilePermissionError)  
只要先在终端运行下面代码就修复了.**

```  
gem update --system
gem sources --remove https://rubygems.org/
gem sources -a https://ruby.taobao.org/
gem sources -l
*** CURRENT SOURCES ***
https://ruby.taobao.org
请确保只有 ruby.taobao.org  
```  
![图片9](http://7xi7a2.com1.z0.glb.clouddn.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-21%20%E4%B8%8A%E5%8D%882.47.02-1.jpg)  

## 5,安装:"Node"  



![node](http://7xi7a2.com1.z0.glb.clouddn.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-21%20%E4%B8%8A%E5%8D%882.48.01-1.jpg)    

## 6,安装jekyll,

```
sudo gem install jekyll
```