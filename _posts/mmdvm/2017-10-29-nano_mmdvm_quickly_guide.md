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
[https://shop113103301.taobao.com](https://shop113103301.taobao.com)  
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)      

#### 新博客更精彩 [http://mmdvm.io/](http://mmdvm.io/)   

MMDVM热点成品快速入门手册 V201812  
准备：路由器管理界面，或 手机安装一个叫 Fing 扫描IP地址手机的App  
1 连接电源    
使用标准的电源供电，最低要求5V1A（NanoPi官方要求5V2A），虚标可能造成WiFi和RF不稳定，严禁使用大于5V 电压！Pi-Star默认登录认ID：pi-star ,密码 raspberry  
  
2 连接网络(仪表盘用户名 pi-star 密码 raspberry)   
方法1：如有网线口（含USB网线），插入网线，等路由器自动分配IP地址，使用电脑浏览器（必须用火狐或Chrome）访问http://IP地址，设置你的个人信息  
  
方法2：当OLED屏幕亮后，树莓派会自建一个Wi-Fi AP热点，打开手机或笔记本搜索 SSID 为Pi-Star的网络，输入 raspberry 密码后，浏览器打开http://pi-star 或 http://192.168.50.1  进入设置界面添加常用Wi-Fi，重启。  （NanoPi小蓝盒没有AP）

方法3：先访问 http://www.mw0mwz.co.uk/pi-star/wifi.php?fref=gc 输入你家的Wi-Fi用户名密码，生成配置文件（官方的链接不会泄露密码）  
把下载到的文件拷贝到SD卡的根目录，启动NanoPi即可实现接入Wi-Fi  
测试是否成功，上路由器看看有没有名称为pi-star 的主机  
  
方法4：在手机或路由器，增加一个共享WiFi，盒子默认接入的WiFi：   
SSID ：888888-2G 密码：0123456789 再访问仪表盘，方法如下   
iOS 共享WiFi热点时：http://pi-star.local  
其它设备共享WiFi时：http://pi-star 如果域名无法解释，使用工具找出盒子的IP地址  
重要：以上方法让你可以把热点盒连接上路由器，接通互联网，管理界面 为http://pi-star 或 http://IP地址(此IP地址是你的路由器DHCP分配的，主机名默认叫 Pi-Star)  
  
3 设置数字电台  
盒子默认频率为 433.550MHz，DMR模式，时隙2，彩色码 1，DMRid 4600000仅监听； 手台的发射联系人设为46001，接收列表必须包含46001，DMRid为你申请的全球ID，不支持多人共享。 完成后，手台单呼 9990 鹦鹉模式进行回音测试。   
鹦鹉回音测试：   
  
C4FM：pi-star设置界面选择 FCS00199 - ECHO，手台设置DN模式 ，按下PTT测试   
DMR：手台添加单呼通讯录 9990 ，调到此信道，按下PTT（组呼没回音，单呼才有） ；或者添加 4000，单呼组呼均可，  呼叫后会有“Disconnect …” 反馈。   
 
TYT-MD-380G设置参考  
单工模式（热点直频）：  
[点击查看大图](http://www.aprspi.org/images/mmdvm/DMR_Radio_Setting_Simplex.jpg)     
![图片装载中](/images/mmdvm/DMR_Radio_Setting_Duplex.jpg)

双工模式（中继）：   
[点击查看大图](http://www.aprspi.org/images/mmdvm/DMR_Radio_Setting_Duplex.jpg)   
![图片装载中](/images/mmdvm/DMR_Radio_Setting_Duplex.jpg)   

各种手台模版下载：  
[https://mmdvm.io/files/radioCPS_MMDVM/](https://mmdvm.io/files/radioCPS_MMDVM/)  
  其它资源：  ，完整手册 [http://www.aprspi.org/mmdvm/nano_mmdvm_userguide/](http://www.aprspi.org/mmdvm/nano_mmdvm_userguide/)    
，误码率调整 [http://www.aprspi.org/mmdvm/abjust-BER/](http://www.aprspi.org/mmdvm/abjust-BER/)    
，MMDVM概念 [http://www.aprspi.org/mmdvm/mmdvm_userguide_view/](http://www.aprspi.org/mmdvm/mmdvm_userguide_view/)  
，DMRid申请 [http://www.aprspi.org/mmdvm/pistar_dmrid_reg/](http://www.aprspi.org/mmdvm/pistar_dmrid_reg/)  
，MMDVM日志分析 [http://www.aprspi.org/mmdvm/nano_view_log/](http://www.aprspi.org/mmdvm/nano_view_log/)  
，玩转MD380 [http://www.aprspi.org/mmdvm/diy_hytmd380_linker/](http://www.aprspi.org/mmdvm/diy_hytmd380_linker/)  

讨论Q群： 320533571   
QQ/微信：38091476  
微信公众号： bi7jta73  
（持续更新）







