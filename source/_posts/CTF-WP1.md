---
title: CTF.WP - Explosion
tags:
  - 安全
  - CTF
  - Viking
categories: CTF
keywords: 'CTF,Viking'
description: Viking战队招新题 Misc - Explosion
swiper_index: 2
top_image: 'https://i.loli.net/2021/10/02/IsUwmJ4MSytVFkP.jpg'
cover: 'https://i.loli.net/2021/10/02/IsUwmJ4MSytVFkP.jpg'
abbrlink: 18371
date: 2021-09-26 00:00:00
---
## **Misc - Explosion**
题目地址[Explosion](http://139.196.79.159:8000/challenges#Explosion)
## **0x00 前言：**
此题用到 **Zip伪加密** ，**Zip明文破解** ，**CRC32爆破** 等。

![](https://pic.imgdb.cn/item/618aaea12ab3f51d91a4624f.png)


## **0x01 开始**


下载附件，发现是一张图片，属性里面查看详细信息，也没发现flag，所以先拖到Binwalk里面看看

![](https://pic.imgdb.cn/item/618aaf962ab3f51d91a4a9b4.png)

果然存在猫腻，图片里面还有个压缩文件，直接用 Binwalk 分离，发现有个flag.zip的加密压缩包，先放到010Editor里面看看

![](https://pic.imgdb.cn/item/618aaea12ab3f51d91a46253.png)

压缩源文件数据区

![](https://pic.imgdb.cn/item/618aaea12ab3f51d91a46258.png)

压缩源文件目录区

通过压缩源文件数据区和目录区的全局方式位标记可知，本压缩文件进行了伪加密，于是把压缩源文件目录区的两个全局方位标记改为 00 00 并保存，压缩文件就能打开了。

打开压缩文件，发现了一个 Readme.txt 和 flag.zip ，感觉事情还没那么简单

![](https://pic.imgdb.cn/item/618aaea12ab3f51d91a46260.png)

不出所料，Readme.txt 里面没有Flag，且 flag.zip 也被加密了，通过010Editor查看，也不是伪加密

![](https://pic.imgdb.cn/item/618aaea12ab3f51d91a46268.png)

flag.zip里面有一张图片和一个 Readme.txt ,比较两处 Readme.txt 发现他们的CRC32 值相同，这样可以尝试用明文爆破的方法是破解flag.zip的密码,于是用祖传的ARCHPR进行了明文破解

![](https://pic.imgdb.cn/item/618aaead2ab3f51d91a465ac.png)

大概跑了四分钟后，破解出了密码，打开压缩包，解压出里面的图片，也没发现什么关键信息flag，详细信息里面也没有flag 

![](https://pic.imgdb.cn/item/618aaead2ab3f51d91a465b4.png)

放到 Binwalk 也没发现什么信息，那就用010Editor看一下，

![](https://pic.imgdb.cn/item/618aaead2ab3f51d91a465ba.png)

CRC值不匹配，所以极有可能是修改过图片高度或宽度，所以把代表高度的 07 20 修改为 07 A0 看看，

![](https://pic.imgdb.cn/item/618aaead2ab3f51d91a465c4.png)

终于找到了flag ，所以这道题的Flag是Viking{BF5_1s_a_Good_Game}
