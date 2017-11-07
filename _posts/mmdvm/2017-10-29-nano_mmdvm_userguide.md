---
layout: article
title: Nano HotSPOT MMDVM 热点板用户手册V1.0
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/nano_userguide_thumb.png
#    thumb:
---


> 本文介绍内容：热点板GPIO定义、pi-star配置、SSH后台登录查看日志、设置Wi-Fi联网、使用的一些注意事项以及部分扩展功能。 

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 近期公告
20171107 代申请DMR-ID访问 www.aprspi.org/raspberry/pistar_dmrid_reg  
20171106 刷pi-star固件需要使用Nano的版本，不能使用树莓派的版本，否则启动不了  
下载地址： http://www.pistar.uk/downloads/  
20171105 交流Q群 320533571  

## 必备工具
1）局域网IP扫描  
苹果手机 https://itunes.apple.com/cn/app/inet-network-scanner/id340793353?mt=8    
安卓手机 http://as.baidu.com/software/11330188.html   
安卓WiFi热点查IP http://mobile.baidu.com/item?docid=11483202&source=s1001  

## 入门配置(和配置路由器一样简单）
接上网线，在任何一台电脑访问 http://pi-star，点击配置，输入  
用户： pi-star   
密码：raspberry  
对于无法访问的情况，登录路由器查看网线连接的终端，显示名称为pi-star  
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_1.png) 
![osc_archi](/images/mmdvm/pistar_conf_1.png)   

[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_2.png) 
![osc_archi](/images/mmdvm/pistar_conf_2.png)   
遇到疑难杂症加Q 38091476  

## 设置Wi-Fi联网
方法一：直接插网线口，等待路由器分配IP后，局域网访问 http://pi-star 进入Web页面配置，如图  
[点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_wifi_web.png) 
![osc_archi](/images/mmdvm/nano_userguide_wifi_web.png)   

方法二：直接写SD卡，使用TF卡套，插入电脑USB口  
![osc_archi](/images/mmdvm/nano_userguide_wifi_conf.png)   
1、先访问 http://www.mw0mwz.co.uk/pi-star/wifi.php?fref=gc 输入你家的Wi-Fi用户名密码，生成配置文件（官方的链接不会泄露密码）  
2、把下载到的文件拷贝到SD卡的根目录，启动NanoPi即可实现接入Wi-Fi  
3、测试是否成功，上路由器看看有没有名称为pi-star 的主机  

方法三：Setup WPA over SSH  
参考：http://wiki.pistar.uk/Setup_WPA_over_SSH  
这是截图：  
![osc_archi](/images/mmdvm/nano_userguide_wifi_ssh.png) 

## 更高级设置
### 1、专家模式：  
http://pi-star/admin/expert/edit_mmdvmhost.php  
作用: 为修改偏频，延时等参数，建议按照上图调整为默认的配置  

### 2、SSH后台登录查看日志
需要有一点Linux知识，这不是傻瓜教程 ^_^  
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_ssh_login_err.png) 
![osc_archi](/images/mmdvm/pistar_ssh_login_err.png) 

## 注意事项
正确的Nano 热点板的使用姿势：    
1、插入、拔出GPIO插座用力均匀，轻轻用力摇出来，必要时用小螺丝刀顶起  
2、插拔先关机断电，勿带电操作  
3、多使用软关机：http://pi-star/admin/power.php ，直接拔电伤SD卡 
4、尽量不去拔NanoPi的MicroUSB接口，拔大USB插头来断电  
5、刷系统前先格式化磁盘，否则OLED会花屏  
6、尽量使用一种模式工作，多种模式会有切换20秒延时，且不可控

## GPIO定义
与NanoPi NEO搭配使用 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_gpio.png) 
 ![osc_archi](/images/mmdvm/nano_userguide_gpio.png)  

在树莓派3B使用，注意插座顺序 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_rasp3b.png) 
![osc_archi](/images/mmdvm/nano_userguide_rasp3b.png)  

## 功能扩展
1、 需要蓝牙模块+BlueDV APP使用，可以自行参照GPIO 串口的定义，增加蓝牙模块，适合动手能力强的HAM DIY；  
2、需要连接Windows BlueDV 桌面程序使用，可以自行参照GPIO 串口的定义，增加USB to TTL模块，适合动手能力强的HAM DIY   
3、还支持iOS版BLE、PC版MMDVM的扩展，需要可以加群讨论，我们玩的就是动手能力     
![osc_archi](/images/mmdvm/nano_userguide_usb.png) 

Nano HotSPOT for MMDVM热点板链接：  
[https://item.taobao.com/item.htm?id=560320395097](https://item.taobao.com/item.htm?id=560320395097)   

提问题请加入Q群：320533571  
（未完待续）





