---
layout: article
title: Nano HotSPOT MMDVM 热点板用户手册V1.1_1108
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
20171107 代申请DMR-ID访问 www.aprspi.org/raspberry/pistar_dmrid_reg  
20171106 刷pi-star固件需要使用Nano的版本，不能使用树莓派的版本，否则启动不了  
下载地址： http://www.pistar.uk/downloads/  
20171105 交流Q群 320533571   

## 第一步 连上有线网络，修改呼号
>没连上MMDVM网络服务器前，OLED显示屏是不会亮的，所以一定要完成此步骤，这个问题不用再提了  

接上网线，通电，等网卡绿灯闪烁时，在任何一台电脑访问 http://pi-star，点击右上角的【配置】，输入  
用户： pi-star   
密码： raspberry  

对于无法访问的情况，http://MMDVM热点的IP地址/ , 直接访问。如何获得IP地址有两种方法：  
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
DMR  ：参考群文件的特易通MD-380 MMDVM写频模板（其他牌子的手台也可以参考，用380软件打开模板），数字联系人增加460、46001、46007等三个通话组，MD380设备可以把呼号和DMR-ID改成你的，直接将模板写入你的手台即可。其它电台类型按群文件是否有，或咨询群友，或自行编辑。  

## 第四步 测试，开始QSO
八重洲：默认已连接 00325 TW YSF886 C4FM Taiwan房间，请使用标准通联用于进行QSO！  
DMR  ：默认连接的服务器为澳大利亚，将手台信道调到46001组，轻按PTT进入会话，守听，再进行QSO。  

鹦鹉测试：目的测试自己的回音  
八重洲：pi-star设置界面选择 00001 - Parrot -Parrot ，按下PTT测试（实际上并没有回音）    
DMR  ：手台添加通话组 99900，调到此信道，按下PTT（回音测试，但实际上并没有回音，可以上去喊喊，两个不在同一热点的HAM进入可以相互QSO）。  

## 几个概念
YSF  
反射器：服务器、房间，类似于DMR的群组，C4FM模式不能跨房间QSO  
鹦鹉：录音、回放程序，用于测试通联质量，丢包率，误码率等    

DMR    
全呼：全网广播形式，漫无目的骚扰大，不建议使用，可以理解为朋友圈状态；   
组呼：在特定的群组呼叫，如中国大陆有3个群组 460 46001 46007，只需登录任何一个BM服务器即可，可以理解为微信群；  
单呼：点对点呼叫，私聊，他人只能看到你的呼号，不能听到语音，与所在组无关，理解为微信一对一对话；  
数字联系人：通讯录，分为以上种类型，  
数字接收组：信道要监听的组呼列表，给信道使用  
组信息：对讲机可以有多个组，每个组下面包含多个信道成员，与组呼是两个概念，是手台外部按钮选择的信道分组    
扫描列表：待补充  
信道：每个联系人（单呼、组呼、全呼）一个通讯组，      
  

## 常见问题
>这种问题只想解释一次

1. 为什么首次上电后OLED屏幕不亮？需要接上网络，初始化完成，连上MMDVM服务器才能亮。  
2. Win7看到的SD卡只有60M或显示未被格式化，不要怀疑，是Win7不识别树莓派格式的磁盘。  
3. DMR模式手台如何进入46001？写频，手台调到对应的频道，按下PTT   

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





