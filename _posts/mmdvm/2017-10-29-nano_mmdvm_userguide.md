---
layout: article
title: Nano 热点板用户手册
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/nano_userguide_thumb.png
#    thumb:
---


> 热点板用在NanoPi NEO时，直插即可，用在NEO之外的派，如树莓派，香橙派时，请按照以下图示安装，VCC插反会烧坏主板。

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 热点板GPIO定义
与NanoPi NEO搭配使用 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_gpio.png) 
 ![osc_archi](/images/mmdvm/nano_userguide_gpio.png)  

在树莓派3B使用，注意插座顺序 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_rasp3b.png) 
![osc_archi](/images/mmdvm/nano_userguide_rasp3b.png)  

## pi-star配置
接上网线，在任何一台电脑访问 http://pi-star，点击配置，输入  
用户： pi-star   
密码：raspberry  
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_1.png) 
![osc_archi](/images/mmdvm/pistar_conf_1.png)   

[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_2.png) 
![osc_archi](/images/mmdvm/pistar_conf_2.png) 

专家模式：  
http://pi-star/admin/expert/edit_mmdvmhost.php  
作用: 为修改偏频，延时等参数，建议按照上图调整为默认的配置  

## 配置视频
待补充  

## 注意事项
正确的Nano 热点板的使用姿势：    
1、插入、拔出GPIO插座用力均匀，轻轻用力摇出来，必要时用小螺丝刀顶起  
2、插拔先关机断电，勿带电操作  
3、多使用软关机：http://pi-star/admin/power.php  
4、尽量不去拔NanoPi的MicroUSB接口，拔大USB插头来断电  
5、刷系统前先格式化磁盘，否则OLED会花屏  

Nano HotSPOT for MMDVM热点板链接：  
[https://item.taobao.com/item.htm?id=560320395097](https://item.taobao.com/item.htm?id=560320395097)   

提问题请加入Q群：树莓派APRS 290347330  
（未完待续）





