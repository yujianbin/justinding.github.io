---
layout: post
title: debian系统的vps上搭建Shadowsocks-libev
category: Server
tags: shadowsocks
keywords: vps,vpn,shadowsocks,debian,服务器
description: 
---

## Shadowsocks[^1]类型

[^1]: *Shadowsocks 是一个轻量级隧道代理，用来穿过防火墙*
* shadowsocks-nodejs
* shadowsocks-libev
* shadowsocks-Python
* shadowsocks-go

## libev特点

1. 版本更新及时，新功能支持的较多。比如目前最新的1.4.1版就支持UDP、多端口等最新功能。  
2. 资源占用极少，内存、CPU占用都非常低，即使是最低档64M内存的VPS都照跑不误。  
3. 部署、调试非常简单直观。
  

## apt方式安装shadowsocks  
 

### 追加软件源 

#### debian 6系统执行以下命令

```
echo "deb http://shadowsocks.org/debian squeeze main" >> /etc/apt/sources.list
```  
  
#### debian 7系统执行以下命令

  
```
echo "deb http://shadowsocks.org/debian wheezy main" >> /etc/apt/sources.list
```  
  
### 然后更新源并安装  
  
```  
apt-get update  
apt-get install shadowsocks  
```  
    
### 使用 Vi命令 [^2] 打开config.json配置文件

[^2]:*Vi：文档编辑工具`vi `编辑,`/ `查找下一个,`? `查找上一个,`n `下一条符合的记录,查找xx字符，可以输入`/xx`,`i`进入编辑模式,`ESC `退出编辑模式,`:q `未做任何修改退出,`:q!`不保存修改退出,`:wq`保存该修改并退出*



```  
vi /etc/shadowsocks/config.json  
```  
  
### 编辑config.json配置文件 
```
{
          "server":"vps的ip",
          "server_port":8388,   #服务器端口，与SSH端口不一样
          "local_port":1080,
          "password":"barfoo!", #认证密码
          "timeout":60,
          "method":"aes-256-cfb" #加密方式，推荐使用aes-256-cfb
} 
```  
  
### 重启shadowsocks服务  

```
/etc/init.d/shadowsocks stop
/etc/init.d/shadowsocks start
```

## 编译方式[^3]安装shadowsocks

[^3]: 编译方式安装特点版本新

- 如果你已经采用apt方式安装过shadowsocks，那么使用如下命令删除已安装的shadowsocks

```
dpkg -P shadowsocks
```  
  
  
### 安装编译所需包  


```  
apt-get update
apt-get install build-essential autoconf libtool libssl-dev git
```  
  
### 然后通过git下载源码  


```  
git clone https://github.com/madeye/shadowsocks-libev.git
```  
  
### 进入目录编译安装  

  
```  
cd shadowsocks-libev
./configure --prefix=/usr
make && make install
```  
  
### 配置服务及配置文件  

  
```
mkdir -p /etc/shadowsocks-libev
cp ./debian/shadowsocks-libev.init /etc/init.d/shadowsocks-libev
cp ./debian/shadowsocks-libev.default /etc/default/shadowsocks-libev
cp ./debian/config.json /etc/shadowsocks-libev/config.json
chmod +x /etc/init.d/shadowsocks-libev  
```
  
### 配置shadowsocks配置文件  

  
```  
vi /etc/shadowsocks-libev/config.json
```
  
```
{
          "server":"vps的ip",
          "server_port":8388,   #服务器端口，与SSH端口不一样
          "local_port":1080,
          "password":"barfoo!", #认证密码
          "timeout":60,
          "method":"aes-256-cfb" #加密方式，推荐使用aes-256-cfb
}  
```
  
### 重启shadowsocks服务  
  
```
/etc/init.d/shadowsocks-libev stop
/etc/init.d/shadowsocks-libev start
```  
