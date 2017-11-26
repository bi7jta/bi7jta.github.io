---
layout: article
title: Nano MMDVM 用户手册V_1125
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/nano_userguide_thumb.png
#    thumb:
---


> 本文内容：MMDVM热点Wi-Fi配置、呼号DMRID配置、热点板GPIO定义、使用的一些注意事项以及部分扩展功能。  
> 现在就开始你的 MMDVM 之旅 Let ‘s go！  
> 
> 文章欢迎转载，但转载时请保留本小段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 近期公告
20171125 增加大屏幕版WiFi配置说明、增加MD380/MD380G写频软件和模板下载地址、电台写频指引、增加pi-star提供的DMR群组列表  
20171116 增加隐藏WiFi、pistar访问异常的场景问题、C4FM国内房间地址更新、Nano+大屏豪华版链接
20171111 增加优酷视频：Nano热点盒开箱指引，观看地址见下  
20171107 代申请DMR-ID访问 www.aprspi.org/raspberry/pistar_dmrid_reg  
20171106 刷pi-star固件需要使用Nano的版本，不能使用树莓派的版本，否则启动不了  
下载地址： http://www.pistar.uk/downloads/  
20171105 交流Q群 320533571   

## 开箱指引视频
优酷主页：http://i.youku.com/bi7jta  （超清模式观看效果更佳）    
共三集，总时长23分钟，声明：本视频仅给入门ham友提供指引，抛砖引玉，不做技术探讨用，可能存在非专业的表述和遗漏，请各取所需，也可以在优酷跟帖评论提出你的看法。  
这是截图，不要点击！！          
![osc_archi](/images/mmdvm/nano_userguide_openbox_video.png)  
欢迎提供在QQ群中分享Nano热点的使用小视频，一经采纳即更新到优酷主页，并将注明视频的原创呼号。  

## 第一步 连上有线网络，修改呼号
>没连上MMDVM网络服务器前，OLED显示屏是不会亮的，所以一定要完成此步骤  

接上网线，通电，等网卡绿灯闪烁时，在任何一台电脑访问 http://pi-star，点击右上角的【配置】，输入  
用户： pi-star   
密码： raspberry  

说明：由于Nano+大屏幕版 树莓派0没有网线接口，需要使用使用电脑将WiFi配置写入SD卡，请准备一个TF写卡器，参考下面的WiFi配置方法二。如果没有不懂操作，请在下单时备注WiFi ID和密码，强烈建议自行设置！  

对于无法访问的情况，大部分情况是浏览器做了域名解释到外网去了，请使用Chrome或火狐浏览器。或  
使用 http://MMDVM热点的IP地址/ 直接访问。如何获得IP地址有两种方法：  
1 登录路由器查看网线连接的终端，查看名称为pi-star的设备的IP地址   
2 使用文章后面的【辅助工具】，查看名称为pi-star的设备的IP地址      
开始配置呼号和DMR-ID，  
这里我默认设置了DMR和YSF两种模式，方便大家测试，请只保留一种和你手台一致的模式   
 
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_1.png)   
![osc_archi](/images/mmdvm/pistar_conf_1.png)   

[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_2.png)   
![osc_archi](/images/mmdvm/pistar_conf_2.png)   
遇到疑难杂症加Q 38091476  

## 第二步 设置无线Wi-Fi，无线使用
>强烈建议用第一种方法，成本最低！如果打算插网线使用，这步骤请忽略  

方法一：直接插网线口，等待路由器分配IP后，局域网访问 http://pi-star 进入Web页面配置，如图   
注意： 配置完成后，刷新一遍当前网页，如果看到WiFi配置栏（wireless Configuration)能显示IP地址，则正常，否则重新配置，直到看到，注意WiFi的ID和密码输入区分大小写  
[点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_wifi_web.png) 
![osc_archi](/images/mmdvm/nano_userguide_wifi_web.png)   

方法二：将Wi-Fi配置文件写入SD卡，使用TF卡套，插入电脑USB口  
![osc_archi](/images/mmdvm/nano_userguide_wifi_conf.png)   
1. 先访问 http://www.mw0mwz.co.uk/pi-star/wifi.php?fref=gc 输入你家的Wi-Fi用户名密码，生成配置文件（官方的链接不会泄露密码）  
2. 把下载到的文件拷贝到SD卡的根目录，启动NanoPi即可实现接入Wi-Fi  
3. 测试是否成功，上路由器看看有没有名称为pi-star 的主机  

方法三：Setup WPA over SSH  
参考：http://wiki.pistar.uk/Setup_WPA_over_SSH  
这是截图：  
![osc_archi](/images/mmdvm/nano_userguide_wifi_ssh.png) 

## 第三步 设置手台，接入热点
八重洲：手置频率为433.550MHz，DN数据模式，按下PTT看热点板的仪表盘是否有TX动作      
DMR  ：参考群文件的特易通MD-380 MMDVM写频模板（其他牌子的手台也可以参考，用380软件打开模板），数字联系人增加460、46001、46007等三个通话组  
MD380/MD380G写频模板和写频软件如下，两型号通用，  

MD380G写频线制作：http://www.aprspi.org/mmdvm/diy_hytmd380_linker    
MD380G写频软件：http://39.106.17.242/download/TYT_MD-380G.rar  
MD380G MMDVM写频模板：http://39.106.17.242/download/TYT_MD380_BI7JTA_v1119.rar  

特别说明：  
1 请一定要把里面的呼号和DMRid改成自己的，否则会影响我登录，没有申请的看http://www.aprspi.org/raspberry/pistar_dmrid_reg   
2 这里只告知大家一种入门的方法，高级玩法如刷机请加群 320533571 看资料、向群友提问  
3 需要购买MD380系列手台请入小店看链接咨询   
4 MD380G玩转APRS定位也请进Q群 683111553 看资料  
虽然本人QQ常年在线，但在忙活混饭吃，除非你发个大红包把我激活O(∩_∩)O~   

图示：  
![osc_archi](/images/mmdvm/nano_userguide_md380g_write1.png)    
![osc_archi](/images/mmdvm/nano_userguide_md380g_write3.jpg)     

## 第四步 测试，开始QSO
八重洲：默认已连接 00325 TW YSF886 C4FM Taiwan房间，请使用标准通联用于进行QSO！  
DMR  ：默认连接的服务器为澳大利亚，将手台信道调到46001组，轻按PTT进入会话，守听，再进行QSO。  

鹦鹉测试：目的测试自己的回音  
八重洲：pi-star设置界面选择 00001 - Parrot -Parrot ，按下PTT测试（实际上并没有回音）    
DMR  ：手台添加通话组 99900，调到此信道，按下PTT（回音测试，但实际上并没有回音，可以上去喊喊，两个不在同一热点的HAM进入可以相互QSO）  

## 在线收听某个组的QSO
https://hose.brandmeister.network/46001/  

## 备份配置
![osc_archi](/images/mmdvm/nano_userguide_backup.png)   

## 重刷系统
准备工作：一张8G SD卡，USB卡套，   
下载地址： http://www.pistar.uk/downloads/  选择Nano版本的pi-star  

## 几个概念
YSF  
反射器：Reflector 服务器(代理）、房间，作用同DMR的群组，C4FM（YSF）模式不能跨房间QSO  
鹦鹉：录音、回放程序，用于测试通联质量，丢包率，误码率等    

DMR    
全呼：全网广播形式，漫无目的骚扰大，不建议使用，可以理解为广播；   
组呼：在特定的群组呼叫，如中国大陆有3个群组 460 46001 46007，只需登录任何一个BM服务器即可，可以理解为群聊；  
单呼：点对点呼叫，私聊，他人只能看到你的呼号，不能听到语音，与所在组无关，理解为一对一对话；  
数字联系人：通讯录，分为以上种类型，  
数字接收组：信道要监听的组呼列表，给信道使用  
组信息：对讲机可以有多个组，每个组下面包含多个信道成员，与组呼是两个概念，是手台外部按钮选择的信道分组    
扫描列表：待补充  
信道：每个联系人（单呼、组呼、全呼）一个通讯组，      
  

## 常见问题 Q&A
1. 为什么首次上电后OLED屏幕不亮？需要接上网络，初始化完成，连上MMDVM服务器才能亮。  
2. Win7看到的SD卡只有64M或显示未被格式化，不要怀疑，是Win7不识别树莓派格式的磁盘。  
3. DMR模式手台如何进入46001？写频，手台调到对应的频道，按下PTT   
4. 直接访问 http://pi-star 有可能被QQ百度360等浏览器自作聪明重定向到官网，选用Chrome或IE 火狐即可，或者直接用IP地址访问 @BD7LYV 反馈  
![osc_archi](/images/mmdvm/nano_userguide_pistar_err.png)   
5. 隐藏WiFi 无法连接问题 @BH7JTB 提供的方法，增加scan_ssid=1参数  
![osc_archi](/images/mmdvm/nano_userguide_hide_wifi.png)  
6. 仪表盘页面在线更新没响应，建议使用ssh命令行更新  
![osc_archi](/images/mmdvm/nano_userguide_QA_updateWeb.png)   

![osc_archi](/images/mmdvm/nano_userguide_QA_updateSSh.jpg)   

7. DMR模式长时间没有接收，仪表盘看到的网络状态正常，需要进入后台看日志，如果频频出现以下日志，  
DMR, Login to the master has failed, retrying network ...  
DMR, Closing DMR Network  
DMR, Opening DMR Network  
则说明服务器连接异常，更换服务器，  
![osc_archi](/images/mmdvm/nano_userguide_connectClose.png)   
正常连接服务器的日志  
![osc_archi](/images/mmdvm/nano_userguide_connectOK.png)   

更多：等待你的补充，一起完善  
带解：同名WiFi多点部署漫游接入问题      

## 辅助工具
>当直接访问http://pi-star 不可用时，务必使用这些工具获得pi-star的IP，使用IP访问

局域网IP扫描：     
苹果手机 https://itunes.apple.com/cn/app/inet-network-scanner/id340793353?mt=8    
安卓手机 http://as.baidu.com/software/11330188.html   
安卓WiFi热点查IP http://mobile.baidu.com/item?docid=11483202&source=s1001  


## 高级设置
1. 专家模式：  
http://pi-star/admin/expert/edit_mmdvmhost.php  
作用: 为修改偏频，延时等参数，建议按照上图调整为默认的配置  

2. SSH后台登录查看日志
需要有一点Linux知识，这不是傻瓜教程 ^_^  
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_ssh_login_err.png) 
![osc_archi](/images/mmdvm/pistar_ssh_login_err.png) 

## 特别提醒
1.    

2. 不要点恢复出厂配置  
![osc_archi](/images/mmdvm/nano_userguide_fallback01.png)   
![osc_archi](/images/mmdvm/nano_userguide_fallback02.png)   

3. 使用SD卡重刷系统前，先备份配置文件，再导入配置，方法    
建议执行update即可    

## 注意事项
正确的Nano 热点板的使用姿势：    
1. 插入、拔出GPIO插座用力均匀，轻轻用力摇出来，必要时用小螺丝刀顶起  
2. 插拔先关机断电，勿带电操作  
3. 多使用软关机：http://pi-star/admin/power.php ，直接拔电伤SD卡 
4. 尽量不去拔NanoPi的MicroUSB接口，拔大USB插头来断电  
5. 刷系统前先格式化磁盘，否则OLED会花屏  
6. 尽量使用一种模式工作(DMR/YSF/DSTSR/P25)，多种模式会有切换20秒延时，且不可控

## GPIO定义
与NanoPi NEO搭配使用 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_gpio.png) 
 ![osc_archi](/images/mmdvm/nano_userguide_gpio.png)  

在树莓派3B使用，注意  
1. 插座顺序，Nano板规则边紧靠树莓派尾巴端，见图1    
[点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_rasp3b.png) 
![osc_archi](/images/mmdvm/nano_userguide_rasp3b.png)  

## 功能扩展
1、 需要蓝牙模块+BlueDV APP使用，可以自行参照GPIO 串口的定义，增加蓝牙模块，适合动手能力强的HAM DIY；  
2、需要连接Windows BlueDV 桌面程序使用，可以自行参照GPIO 串口的定义，增加USB to TTL模块，适合动手能力强的HAM DIY   
3、支持iOS版BLE、PC版MMDVM的扩展，需要可以加群讨论，需要动手能力     

## DMRid增长情况
![osc_archi](/images/mmdvm/nano_dmr_id_20171114.png)  

## 比较热闹的组
4400,United Kingdom  
45004,韩国    
46600 TW 闽南语为主     
46601 TW  
440 日本  
9  91  92  
454 HK  

国内：
46001 深圳
46007 深圳
46073 深圳
46076 深圳

官方公布的DMR组
http://www.pistar.uk/dmr_bm_talkgroups.php 


Nano HotSPOT for MMDVM热点板链接：  
Nano小蓝盒快速入门版：  
[https://item.taobao.com/item.htm?id=561964266288](https://item.taobao.com/item.htm?id=561964266288)   
Nano+大屏豪华版：  
[https://item.taobao.com/item.htm?id=561607171659](https://item.taobao.com/item.htm?id=561607171659)   
Nano创客空间(小店)：  
[https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02](https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02)  
![osc_archi](/images/mmdvm/nano_userguide_taobao.png)     



提问题请加入Q群： 320533571  微信： 38091676
（持续更新）





