---
layout: post
title: debian_shadowsocks_libev一键安装脚本
category: Server
tags: shadowsocks
keywords: shadowsocks,debian,VPS,
description: 
---

### **下载**

```
wget --no-check-certificate https://raw.githubusercontent.com/tennfy/shadowsocks-libev/master/debian_shadowsocks_tennfy.sh
chmod a+x debian_shadowsocks_tennfy.sh
```


### **安装Shadowsocks-libev**
 
1. 执行以下命令:

   ```
   bash debian_shadowsocks_tennfy.sh
   ```
2. 安装中出现的选择界面，请一律选择YES，然后回车。
3. 安装过程中脚本会提示输入server_port及password,server_port建议取小一些，如443,80等。password自定.如下图所示:

   `#############################################################`
   `#`
   `# Please input your shadowsocks server_port and password`
   `#`
   `#############################################################`
   `input server_port(443 is suggested):`
   `443`
   `input password:`
   `weiosx.com`

4. 输入之后，脚本会自动配置shadowsocks，完成之后出现如下界面：

   ```
Congratulations, shadowsocks-libev install completed!
Your Server IP: xxx.xxx.xxx.xxx
Your Server Port: 443
Your Password: tennfy.com
Your Local Port: 1080
Your Encryption Method:rc4-md5
```
**请保存该信息，方便在客户端连接服务器**

  
    
### **卸载shadowsocks-libev**

```
bash debian_shadowsocks_tennfy.sh update
```

  
### **更新shadowsocks-libev**
    
    
    bash debian_shadowsocks_tennfy.sh update
    
    **更新命令实际上是先执行卸载，然后重新安装。所以安装时的提示请参考第一步。**

    

### **相关操作**
    
   1. **shadowsocks配置文件位置**
   
      ```
      /etc/shadowsocks-libev/config.json
      ```

      **编辑该文件从而修改密码、服务器端口及加密方式，修改之后记得保存重启。**

   2. **重启shadowsocks服务**
   
      ```
      /etc/init.d/shadowsocks-libev stop
      /etc/init.d/shadowsocks-libev start
      ```

   3. **脚本已加入shadowsocks服务开机自启**   