---
layout: article
title: MMDVM(Multi-Mode Digital Voice Modem)入门介绍
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm_arch_l.jpg
#    thumb:
---


> 本文会简要介绍 MMDVM(Multi-Mode Digital Voice Modem)

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

### 前言

#### 新博客更精彩 [http://mmdvm.io/](http://mmdvm.io/)  

凑个热闹，最近HAM友圈玩得很多的MMDVM数字电台网关，初步统计了下，截止2017-10-13，中国的爱好者接入525个（以DMR id注册数量）。很多HAM初次听闻MMDVM，不知道是什么干什么用的，原介绍多来英文资料，国内ham写的多是项目介绍和配置说明，偏技术，为了让小白快速入门，本博把自己的理解分享一下，引你入坑，非专业写手。


## 1.MMDVM是什么？

MMDVM(Multi-Mode Digital Voice Modem)，中文翻译为：多模式数字语音调制调解器。简单的说就是数字语音猫，数字电台互联网关，实现各种数字制式，如C4FM/DMR/D-STAR/P25协议全球互联。  
它英国HAM G4KLX发起的开源项目，声明为GPL v2协议，旨在成为开源的多模式数字语音调制解调器，利用ARM处理器和一块简单的模拟接口板。最初，它将支持D-Star和DMR，系统融合和P.25将在以后推出，以及一个内置的FM中继器控制器。对于除DMR和FM以外的所有模式，调制解调器可用于单工或双工模式，而对于DMR和FM全双工则必须使用（部分内容翻译自互联网资料）。  


图解MMDVM（一）What is it ？  [点击查看大图](http://www.aprspi.org/images/What-is-mmdvm.png) 
![osc_archi](/images/What-is-mmdvm.png)
  

图解MMDVM（二）How to do ？  [点击查看大图](http://www.aprspi.org/images/How-to-do-mmdvm.jpg) 
![osc_archi](/images/How-to-do-mmdvm.jpg)

开源项目：  
https://github.com/g4klx/MMDVM  

开源协议：  
This software is licenced under the GPL v2 and is intended for amateur and educational use only. Use of this software for commercial purposes is strictly forbidden.  

关联项目：  
MMDVM_HS  
YSFClients  
MMDVMHost  
DMRGateway  
MMDVMCal    
Pi-Star_DV_Dash  
MMDVM_HS_Hat   
MMDVM_pog  

同类产品：   
DVMEGA 

和Echolink的区别： -    
和公网对讲机的区别： -   
和数字集群网的区别： -    

## 2.MMDVM应用场景？
目标用户

## 3.MMDVM如何使用？
需要买哪些设备  
联网条件

## 4.MMDVM的贡献者
 

## 5.MMDVM社区支持？


## 项目的展望

## 常见问题
申请DMR-ID快速通过技巧  
常用服务器，运营商限制  
使用USB和蓝牙连接MMDVM  
使用Windows版MMDVM程序  
使用DlueDV客户端连接MMDVM  

## 一些技巧
去掉pistar WebConsole密码  
SD卡扩容  
局域网访问  
增加Wifi连接  
Wifi名区分大小写  
OLED 显示雪花屏  
频偏导致热点RF无收发  

Nano HotSPOT for MMDVM热点板链接：  
Nano小蓝盒快速入门版：  
[https://item.taobao.com/item.htm?id=561964266288](https://item.taobao.com/item.htm?id=561964266288)   
Nano+大屏豪华版：  
[https://item.taobao.com/item.htm?id=561607171659](https://item.taobao.com/item.htm?id=561607171659)   
Nano创客空间(小店)：  
[https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02](https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02)  
![osc_archi](/images/mmdvm/nano_userguide_taobao.png)   

Q群技术讨论组：320533571  

（未完待续）





