---
layout: post
title: 在Mac OSX 10.10 Yosemite安装mcrypt的php到开发服务器
category: Mac
tags: mcrypt
keywords: Mac,mcrypt,php,服务器
description: 
---  

> **mcrypt** 是使用安全技术来交换数据文件加密方法. 这是必需的，例如一些Magento的Web应用程序,购物车软件或一个PHP框架，比如 **Laravel**. 本教程在 OS X 10.10 Yosemite 经过测试.

>本指南是真正为用户提供了 PHP 运行于 OSX Yosemite 的 5.5.14 版本. 其他下载 AMP stacks 已经有**mcrypt**在出炉.  

## Command Line Tools  

首先需要OSX 10.10版本的 Command Line Tools，你可以通过在 App Store 可用的更新下载.

在终端上运行

```
xcode-select --install
```

## 在 OS X Yosemite 10.10 系统内得到 mcrypt.

本教程主要集中在 **Terminal** ,从 /应用程序/实用工具 位置启动。更改目录 (cd) 到 家庭帐户，让你将工作集中在一个目录, 更名为 **mcrypt**

```
cd ~ ; mkdir mcrypt ; cd mcrypt
```

[从 Sourceforge 获得 libmcrypt 2.5.8,](http://sourceforge.net/projects/mcrypt/files/Libmcrypt/2.5.8/libmcrypt-2.5.8.tar.gz/download)这是直接下载链接.

[获取在 PHP 中 tar.gz 或 .bz2 中的代码](http://php.net/releases/index.php)- (版本 5.5.14 是目前支持 OSX 10.10)

移动这两个文件下载到你的工作目录中 – **mcrypt**   
在这种情况下，返回到终端

```
cd ~/mcrypt
```

通过命令行展开这两个文件或者只是在Finder中双击他们:

```
tar -zxvf libmcrypt-2.5.8.tar.gz
```

```
tar -zxvf php-5.5.9.tar.gz
```

删除压缩档案

```
rm *.gz
```

在命令行中包括任何错误 C++ 和 g++ 大多是由于命令行工具缺失.

## 配置libmcrypt

* 更改目录到libmcrypt

```
cd libmcrypt-2.5.8
```

* Libmcrypt需要配置，输入

```
./configure
make
sudo make install
```

等 libmcrypt 配置和库现在安装,现在我们完善 mcrypt 扩展.

## 安装 Autoconf

> 安装 **Autoconf**   
> 一些较为繁重的 **Terminal** 操作:

```
cd ~/mcrypt
curl -O http://ftp.gnu.org/gnu/autoconf/autoconf-latest.tar.gz
tar xvfz autoconf-latest.tar.gz
cd autoconf-2.69/
./configure
make
sudo make install
```

## 编译 mcrypt 的 PHP扩展

```
cd ../php-5.5.9/ext/mcrypt/
/usr/bin/phpize
```
输出应该类似于：  
`Configuring for:`  
`PHP Api Version: 20121113`  
`Zend Module Api No: 20121212`  
`Zend Extension Api No: 220121212`  
  
```
./configure
make
sudo make install
```  
  
这样做的结果应该类似于:

`Installing shared extensions:  /usr/lib/php/extensions/no-debug-non-zts-20121212/`

## 启用 mcrypt.so PHP扩展

打开`/etc/php.ini`并添加下面的一行结束

```
extension=mcrypt.so
```

如果没有`php.ini`文件,那么你需要做一个 php.ini .默认在同一位置像这样:

```
sudo cp /etc/php.ini.default /etc/php.ini
```
并允许写入功能

```
sudo chmod u+w  /etc/php.ini
```
然后用你最喜爱的文本编辑器添加这行:

```
sudo nano /etc/php.ini
```

或

```
sudo vi /etc/php.ini
```
并添加这行:

```
extension=mcrypt.so
```

## 重新启动 Apache

```
sudo apachectl restart
```

就这样，创建一个带phpinfo()功能的PHP页面;看它是否正确装入.

![phpinfo](http://image.weiosx.com/osx-yosemite-mcrypt.png)

如果没有加载,您可能需要在`/etc/php.ini`声明扩展目录

```
extension_dir = "/usr/lib/php/extensions/no-debug-non-zts-20100525/"
```

![php](http://image.weiosx.com/php-extension-directory-lion-mcrypt1.png)