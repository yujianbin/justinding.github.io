---
layout: post
title: 使用 Karabiner 实现 Mac 拼音输入法默认输出英文符号!
category: Mac
tags: Mac 技巧 Karabiner 输入法 
keywords: Mac,技巧,Karabiner,输入法
description: 
---

> 经常使用 Mac 编写代码的朋友都会遇到一个烦恼的事情,切换到中文输入法后,忘记切换回英文输入法或者忘了按caps lock键,然后产生删除输入错误的符号,无形中浪费了1-2秒的时间,以前用第三方的输入法来解决这个问题,最近放弃使用第三方的输入法,发现可以用第三的开源免费软件 "[Karabiner](https://pqrs.org/osx/karabiner)" 执行一段代码后解决这个问题。

![Karabiner](http://image.weiosx.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-15%20%E4%B8%8B%E5%8D%8810.45.42.jpg)

## 安装
![安装](http://image.weiosx.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-15%20%E4%B8%8B%E5%8D%8810.47.38.jpg)  
  
## 打开 karabiner


![Karabiner](http://image.weiosx.com/karabiner.jpg)
![进入](http://image.weiosx.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-15%20%E4%B8%8B%E5%8D%8810.49.34.jpg)

### 进入 Misc & Uninstall 界面,点击 Open private.xml

![进入Misc & Uninstall](http://image.weiosx.com/%E2%80%9CJustin%E2%80%99%E6%88%AA%E5%9B%BE%E2%80%9D%202015-03-15%20%E4%B8%8B%E5%8D%8810.53.41.jpg)

### 打开 private.xml 文件
![编辑](http://image.weiosx.com/“Justin’截图”%202015-03-15%20下午11.04.54.jpg)  
  
### 输入下面代码后保存文件
  
```
<?xml version="1.0"?>
<root>
    <appdef>
        <appname>APPSTORE</appname>
        <equal>com.apple.appstore</equal>
    </appdef>
    <appdef>
        <appname>sublimetext</appname>
        <equal>com.sublimetext.3</equal>
    </appdef>
    
    <item>
        <name>系统拼音:使用英文标点符号</name>
        <identifier>private.quick_dotOfEnglish</identifier>
        <inputsourceid_equal>com.apple.inputmethod.SCIM.ITABC</inputsourceid_equal>
        <inputsourceid_equal>AXTextArea, AXTextField</inputsourceid_equal>
        
        <autogen>__KeyToKey__
            KeyCode::COMMA,
            KeyCode::CAPSLOCK,
            KeyCode::COMMA,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::COMMA, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::COMMA, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::DOT,
            KeyCode::CAPSLOCK,
            KeyCode::DOT,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::DOT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::DOT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::DOT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::DOT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::COMMA, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::COMMA, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SLASH,
            KeyCode::CAPSLOCK,
            KeyCode::SLASH,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SLASH, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::SLASH, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SLASH, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::SLASH, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SEMICOLON,
            KeyCode::CAPSLOCK,
            KeyCode::SEMICOLON,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SEMICOLON, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::SEMICOLON, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::SEMICOLON, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::SEMICOLON, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::QUOTE,
            KeyCode::CAPSLOCK,
            KeyCode::QUOTE,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::QUOTE, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::QUOTE, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::QUOTE, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::QUOTE, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_LEFT,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_LEFT,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_LEFT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_LEFT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_LEFT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_LEFT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_RIGHT,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_RIGHT,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_RIGHT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_RIGHT, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BRACKET_RIGHT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::BRACKET_RIGHT, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BACKSLASH,
            KeyCode::CAPSLOCK,
            KeyCode::BACKSLASH,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BACKSLASH, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::BACKSLASH, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::BACKSLASH, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::BACKSLASH, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::MINUS,
            KeyCode::CAPSLOCK,
            KeyCode::MINUS,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::MINUS, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::MINUS, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::MINUS, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::MINUS, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::EQUAL,
            KeyCode::CAPSLOCK,
            KeyCode::EQUAL,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::EQUAL, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::EQUAL, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::EQUAL, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::EQUAL, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::KEY_1, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::KEY_1, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::KEY_1, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::KEY_1, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::KEY_2, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
            KeyCode::KEY_2, ModifierFlag::SHIFT_R,
            KeyCode::CAPSLOCK,
        </autogen>
        
        <autogen>__KeyToKey__
            KeyCode::KEY_2, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
            KeyCode::KEY_2, ModifierFlag::SHIFT_L,
            KeyCode::CAPSLOCK,
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_3, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_3, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_3, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_3, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_4, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_4, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_4, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_4, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_5, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_5, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_5, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_5, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_6, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_6, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_6, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_6, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_7, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_7, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_7, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_7, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_8, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_8, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_8, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_8, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_9, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_9, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_9, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_9, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_0, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_0, ModifierFlag::SHIFT_R, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
        <autogen>__KeyToKey__ 
            KeyCode::KEY_0, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
            KeyCode::KEY_0, ModifierFlag::SHIFT_L, 
            KeyCode::CAPSLOCK, 
        </autogen> 
        
    </item>
</root> 
```
![输入代码](http://image.weiosx.com/“Justin’截图”%202015-03-15%20下午11.05.55.jpg)  

### 来到 Karabiner 的 Change Key 页面,点击 Reload XML 完成修改.  
  
![运行](http://image.weiosx.com/“Justin’截图”%202015-03-15%20下午11.10.19.jpg)  
  
### 好了,修改完毕,正在使用中,暂时没发现任何兼容问题.
