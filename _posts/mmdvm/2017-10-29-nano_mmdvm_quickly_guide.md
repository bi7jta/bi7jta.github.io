---
layout: article
title: MMDVM热点成品上手配置指引
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/nano_quickly_guide_thumb.png
#    thumb:
---

20171105 交流Q群 320533571     

> 本文内容：快速入门用于配置小蓝盒和jTA其他系列热点板

> 文章欢迎转载
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>   

## 获得设备    
[https://item.taobao.com/item.htm?id=561964266288](https://item.taobao.com/item.htm?id=561964266288)  

[https://shop113103301.taobao.com](https://shop113103301.taobao.com)  
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)      

MMDVM热点成品快速入门手册 V1   1 连接电源   使用标准的电源供电，5V2A（大屏幕），5V2A（小蓝盒），5V1A可能造成WiFi和RF不稳定，严禁使用大于5V 电压！如有外接大屏幕，正负极千万别接反，反接必然导致损坏内部电路！   2 连接网络，仪表盘用户名 pi-star 密码 raspberry   方法一：如有网线口，插入网线，等路由器自动分配IP地址，使用电脑浏览器（必须用火狐或Chrome）访问该IP地址，设置你的个人信息   方法二：打开手机，搜索加入 Pi-Star-setup 的WiFi热点，密码 raspberry，手机浏览器访问   http://192.168.50.1 ，在WiFi设置栏目新增你需要的WiFi（和你的新手机增加WiFi一个原理）  方法三：在手机或路由器，增加一个共享WiFi，盒子默认接入的WiFi：   SSID ：888888-2G  密码：0123456789 再访问仪表盘，方法如下   iOS 共享WiFi热点时：http://pi-star.local  其它设备共享WiFi时：http://pi-star  如果域名无法解释，使用工具找出盒子的IP地址  3 设置数字电台  盒子默认频率为 433.550MHz，DMR模式，时隙2，彩色码 1，DMRid 4600000仅监听； 
手台的发射联系人设为46001，接收列表必须包含46001，DMRid为你申请的全球ID，不支持多人共享。
完成后，手台单呼 9990 鹦鹉模式进行回音测试。  

双工mini中继盒默认频率为：   
RX 434.755MHz  对应电台的TX    
TX 439.755MHz  对应电台的RX  

双工DMR模式下，手台写频时要关掉 Talkaroud 模式，设置静态组，否则动态组15分钟后会被自动清掉      其它资源：  ，完整手册 [http://www.aprspi.org/mmdvm/nano_mmdvm_userguide/](http://www.aprspi.org/mmdvm/nano_mmdvm_userguide/)    
，误码率调整 [http://www.aprspi.org/mmdvm/abjust-BER/](http://www.aprspi.org/mmdvm/abjust-BER/)    
，MMDVM概念 [http://www.aprspi.org/mmdvm/mmdvm_userguide_view/](http://www.aprspi.org/mmdvm/mmdvm_userguide_view/)  
，DMRid申请 [http://www.aprspi.org/mmdvm/pistar_dmrid_reg/](http://www.aprspi.org/mmdvm/pistar_dmrid_reg/)  
，MMDVM日志分析 [http://www.aprspi.org/mmdvm/nano_view_log/](http://www.aprspi.org/mmdvm/nano_view_log/)  
，玩转MD380 [http://www.aprspi.org/mmdvm/diy_hytmd380_linker/](http://www.aprspi.org/mmdvm/diy_hytmd380_linker/)  

讨论Q群： 320533571   
QQ/微信：38091476  
微信公众号： bi7jta73  
（持续更新）







