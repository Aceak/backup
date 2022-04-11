---
title: IDM + 暴力猴实现百度网盘满速下载
tags:
  - IDM
  - 暴力猴
  - 百度网盘
categories:
  - 百度网盘
  - IDM的花式用法
description: 通过IDM和油猴脚本实现百度网盘满速下载
swiper_index: 1
top_img: 'https://pic.imgdb.cn/item/6172cde62ab3f51d911a4ede.jpg'
cover: 'https://pic.imgdb.cn/item/6172cf9a2ab3f51d911c90f0.jpg'
abbrlink: 64753
date: 2021-10-22 22:00:00
updated:
keywords:
---
# **通过IDM实现百度网盘不限速下载**

## **0x00 前言**
众所周知，百度网盘的下载速度很慢，即使买了SVIP会员，也没法满速下载。于是网上就时不时的出现一些百度网盘不限速下载的方法，我在这里分享一个目前较为稳定的下载方法。  
## **0x01 工具/原料**
- 一台搭载Windows系统电脑（ 此方法只能用于在电脑上不限速下载百度网盘里面的文件 ）
- 百度网盘账号
- 新版 Microsoft Edge 浏览器（推荐）
- 暴力猴或油猴插件
- Internet Download Manager  

## **0x02 IDM的下载和配置**
作为十分强大的下载工具，IDM付费也是应该的，但并非每个人都能有能力买到正版软件，我在这里推荐用俄罗斯大神破解并重新打包的版本  
  
### **1. 下载链接**  

> 官方正版：[IDM下载](https://www.internetdownloadmanager.com/)  
> 俄罗斯大神版：[IDM下载](https://lrepacks.net/repaki-programm-dlya-interneta/56-internet-download-manager-repack.html)  
> 国内网盘(俄罗斯大神版):[IDM下载](https://wwe.lanzouw.com/b01uppjcd)  提取码:stxw

### **2. 语言改为中文**
下载安装后打开IDM ,  一次点 `View` - `Language` - `简体中文` , 设置完成后IDM会重启 。  

![](https://pic.imgdb.cn/item/6172c1932ab3f51d910abad3.jpg)
### **3. 修改线程和用户代理UA（关键一步）**
打开IDM后点 `选项` - `下载` , 然后将以下代码复制到 `手动添加下载任务时使用的用户代理(UA)`
``` UA
netdisk;7.2.6.2;PC;PC-Windows;6.3.9600;WindowsBaiduYunGuanJia
```
![](https://pic.imgdb.cn/item/6172c42e2ab3f51d910de5c7.png)  
  
然后点击 `连接` , 将下面的 `最大连接数` 改为 4 （只能改成4，改成其他会失败）然后点确定。  

![](https://pic.imgdb.cn/item/6172c6ed2ab3f51d911131c4.png)
## **0x03 使用步骤**
### **1. Edge浏览器下载暴力猴（或油猴插件）**
> 点击浏览器右上角的 **三个横点（ ··· ）**，再点击扩展，然后点获取 Microsoft Edge 扩展  
> 
> ![](https://pic.imgdb.cn/item/61729b6e2ab3f51d91df935e.jpg)  
> 
> 搜索 '暴力猴' 并安装 ，安装成功后浏览器右上角会出现一个猴头  
> 
> ![](https://pic.imgdb.cn/item/61729f242ab3f51d91e2c537.png)
### **2. 下载不限速插件**
> 打开新页面下载 [百度网盘简易下载助手](https://greasyfork.org/zh-CN/scripts/418182-%E7%99%BE%E5%BA%A6%E7%BD%91%E7%9B%98%E7%AE%80%E6%98%93%E4%B8%8B%E8%BD%BD%E5%8A%A9%E6%89%8B-%E7%9B%B4%E9%93%BE%E4%B8%8B%E8%BD%BD%E5%A4%8D%E6%B4%BB%E7%89%88) 并安装  
> 
> ![](https://pic.imgdb.cn/item/6172bc242ab3f51d910384b3.jpg)  

### **3. 用百度网盘下载文件**
浏览器打开[百度网盘网页版](https://pan.baidu.com/) ， 登陆自己的账号 ，选中需要下载的文件，再点 `简易下载助手` , 在弹出来的窗口点 `点击获取直连地址`, 然后再点 `复制直连地址`  
**注:** 第一次使用时需要关注 **`软件小妹`** 获取验证码  

![](https://pic.imgdb.cn/item/6172ca5a2ab3f51d9115b96c.jpg)  

然后打开IDM点击 `新建任务` 在地址栏粘贴刚刚复制的直连点确定，然后选择保存地址( 一般默认即可 ) ， 点确定即可百度网盘享受全速下载 。

### ⭐⭐如果这篇文章对你有帮助的话，请收藏本网站，后期我会分享更多 IDM 高阶玩法⭐⭐
🌟使用过程中若遇到其他问题，请直接在底部评论区中回复🌟
