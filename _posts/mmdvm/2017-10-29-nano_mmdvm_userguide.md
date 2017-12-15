---
layout: article
title: Nano MMDVM 用户手册V_1211
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
> 
> 感谢我的搭档 @BH7NJF 于2017将 MMDVM 引入中国，并牺牲在家半年休假的时间，看英文资料、做开发板、研究固件/系统、先行研究、实践了目前在中国所看到的MMDVM热点板（各种大板、小板、Nano板），让中国HAM用上廉价的热点板，功不可没。请向默默无闻的幕后英雄致敬！  

## 近期公告
20171211 增加常见问题10 同时守听多组答疑、更新第四步后的热闹DMR组推荐     
20171209 增加md380刷机调低功率教程   
20171205 增加代申请DMRid的表单入口 https://mmdvm.wufoo.com/forms/mmdvm-dmridaecee  
20171201 增加大屏幕显IP驱动 PI-STAR重刷镜像方法  
20171127 增加DMR长时间没收发的网络诊断方法    
20171125 增加大屏幕版WiFi配置说明、增加MD380/MD380G写频软件和模板下载地址、电台写频指引、增加pi-star提供的DMR群组列表、  
20171116 增加隐藏WiFi、pistar访问异常的场景问题、C4FM国内房间地址更新、Nano+大屏豪华版链接
20171111 增加优酷视频：Nano热点盒开箱指引，观看地址见下       
20171106 刷pi-star固件需要使用Nano的版本，不能使用树莓派的版本，否则启动不了  
下载地址： http://www.pistar.uk/downloads/  
20171105 交流Q群 320533571   

## 开箱指引视频
优酷主页：http://i.youku.com/bi7jta  （超清模式观看效果更佳）    
共三集，总时长23分钟，声明：本视频仅给入门ham友提供指引，抛砖引玉，不做技术探讨用，可能存在非专业的表述和遗漏，请各取所需，也可以在优酷跟帖评论提出你的看法。  
这是截图，不要点击！！          
![图片装载中](/images/mmdvm/nano_userguide_openbox_video.png)  
欢迎提供在QQ群中分享Nano热点的使用小视频，一经采纳即更新到优酷主页，并将注明视频的原创呼号。  

## 第一步 连上有线网络，修改呼号
>没连上MMDVM网络服务器前，OLED显示屏是不会亮的，所以一定要完成此步骤  

接上网线，通电，等网卡绿灯闪烁时，在任何一台电脑访问 http://pi-star，点击右上角的【配置】，输入  
用户： pi-star   
密码： raspberry  

强烈建议用Chrome或火狐浏览器访问，其它浏览器存在问题  
火狐地址：http://www.firefox.com.cn/download/  

说明：由于Nano+大屏幕版 树莓派0没有网线接口，需要使用使用电脑将WiFi配置写入SD卡，请准备一个TF写卡器，参考下面的WiFi配置方法二。如果没有不懂操作，请在下单时备注WiFi ID和密码，强烈建议自行设置！  

对于无法访问的情况，大部分情况是浏览器做了域名解释到外网去了，请使用Chrome或火狐浏览器。或  
使用 http://MMDVM热点的IP地址/ 直接访问。如何获得IP地址有两种方法：  
1 登录路由器查看网线连接的终端，查看名称为pi-star的设备的IP地址   
2 使用文章后面的【辅助工具】，查看名称为pi-star的设备的IP地址      
开始配置呼号和DMR-ID，  
这里我默认设置了DMR和YSF两种模式，方便大家测试，请只保留一种和你手台一致的模式   
 
[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_1.png)   
![图片装载中](/images/mmdvm/pistar_conf_1.png)   

[点击查看大图](http://www.aprspi.org/images/mmdvm/pistar_conf_2.png)   
![图片装载中](/images/mmdvm/pistar_conf_2.png)   
遇到疑难杂症加Q 38091476  

## 第二步 设置无线Wi-Fi，无线使用
>强烈建议用第一种方法，成本最低！如果打算插网线使用，这步骤请忽略  

方法一：直接插网线口，等待路由器分配IP后，局域网访问 http://pi-star 进入Web页面配置，如图   
注意： 配置完成后，刷新一遍当前网页，如果看到WiFi配置栏（wireless Configuration)能显示IP地址，则正常，否则重新配置，直到看到，注意WiFi的ID和密码输入区分大小写  
[点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_wifi_web.png) 
![图片装载中](/images/mmdvm/nano_userguide_wifi_web.png)   

可以增加多个WiFi保存，如手机热点的WiFi，但同一时候只会连接第一次接入的WiFi，测试手机WiFi时，要走到没有路由器WiFi信号的地方，或关闭路由器的WiFI，或通过网线接入，删除pi-Star里的路由器的WiFi   
![图片装载中](/images/mmdvm/jiqiao_MobileWiFi_hotSPOT.png) 

方法二：将Wi-Fi配置文件写入SD卡，使用TF卡套，插入电脑USB口（适合Nano+大屏幕版）    
![图片装载中](/images/mmdvm/nano_userguide_wifi_conf.png)   
1. 先访问 http://www.mw0mwz.co.uk/pi-star/wifi.php?fref=gc 输入你家的Wi-Fi用户名密码，生成配置文件（官方的链接不会泄露密码）  
2. 把下载到的文件拷贝到SD卡的根目录，启动NanoPi即可实现接入Wi-Fi  
3. 测试是否成功，上路由器看看有没有名称为pi-star 的主机  

方法三：Setup WPA over SSH  
参考：http://wiki.pistar.uk/Setup_WPA_over_SSH  
这是截图：  
![图片装载中](/images/mmdvm/nano_userguide_wifi_ssh.png) 

## 第三步 设置手台，接入热点
C4FM模式：设置呼号，手置频率为433.550MHz，DN数据模式，按下PTT看热点板的仪表盘是否有TX动作      
DMR模式：参考群文件的特易通MD-380 MMDVM写频模板（其他牌子的手台也可以参考，用380软件打开模板），数字联系人增加460、46001、46007等三个通话组  
MD380/MD380G写频模板和写频软件如下，两型号通用，  

MD380G写频线制作：http://www.aprspi.org/mmdvm/diy_hytmd380_linker    
MD380G写频软件（官方）：http://39.106.17.242/download/TYT_MD-380G.rar  
MD380G MMDVM写频模板：http://39.106.17.242/download/TYT_MD380G_BI7JTA_v1206_EN_CN.zip   
P8668 MMDVM频模板和教程：http://39.106.17.242/download/p8668_ctb_template_bi7mtd.zip    

安装380驱动和写频软件图示：   
![图片装载中](/images/mmdvm/nano_userguide_md380g_write1.png)    
![图片装载中](/images/mmdvm/nano_userguide_md380g_write3.jpg)   

如果仍然出现无法识别的设备，则手动重装驱动，下载本博提供的STM32驱动包，此问题通常出现在md380G设备，  
http://39.106.17.242/download/md380USB_Driver_BI7JTA.zip  

![图片装载中](/images/mmdvm/jiqiao_380_driver_unknow.png)   

![图片装载中](/images/mmdvm/jiqiao_380_driver_file.png)  

![图片装载中](/images/mmdvm/jiqiao_380_driver_qudongjingl.png)  


特别说明：  
1 请一定要把里面的呼号和DMRid改成自己的，没有申请的看http://www.aprspi.org/raspberry/pistar_dmrid_reg   
2 这里只告知大家一种入门的方法，高级玩法如刷机请加群 320533571 看资料、向群友提问  
3 MD380G玩转APRS定位也请进Q群 683111553 看资料  
4 md380/md380g刷机和调小功率到0.1瓦教程 见本书册最后部分  

D-star iCOM MMDVM设置教程，进群咨询，  
P25 MOTO，MMDVM设置教程，进群咨询，    
  

这里暗示一下：需要入手md380系列数字手台、moto p8668的朋友群里找我，ham渠道，透明放心。  

## 第四步 测试，开始QSO
八重洲：默认已连接 CN #3房间，请先守听，再使用标准通联用于进行QSO，插入先提出申请！  
DMR  ：默认连接的服务器为澳大利亚，将手台信道调到46001组，轻按PTT进入会话，守听，再进行QSO。  

鹦鹉测试：目的测试自己的回音  
八重洲：pi-star设置界面选择 00001 - Parrot -Parrot ，按下PTT测试（实际上并没有回音）    
DMR  ：手台添加通话组 9990，调到此信道，按下PTT（回音测试，但实际上并没有回音，可以上去喊喊，两个不在同一热点的HAM进入可以相互QSO）  

## 在线收听某个组的QSO
在线语音：  
https://hose.brandmeister.network/46001/ 
热点地图（翻墙）：  
https://brandmeister.network/?page=networkmap  

## 比较热闹的组推荐，按PTT进入守听  
提示： MD380/380g可写上面的MMDVM模板见【第三步】，调到相应的组   

3100  美国，和中国时差12~14小时  
9     世界组，进入：单呼4400，退出：单呼4000，注意单呼4400后会霸占信道，慎入！  
91    欧洲组，比较热闹，欧洲HAM都会在里面，周六台网点名   
92    英国组，暂未监听   
欧洲和中国的时差为8小时左右  
45004 韩国 热闹     
46600 台湾 闽南语为主，人气一般         
46601 台湾 人气一般    
440 日本 人气不旺，玩短波多      
454 HK 人气不高，据说HK HAM很忙    

国内：
46001 中国大组  
46007 深圳小组        
460075 Nano小蓝盒QSY专用  
各分区如：46002、46003...      

本博md380预设置的常守组，其中：  
460075为小蓝盒测试专用，可以从46001 相约QSY到此组，  
460755 为新增深圳接入点预留组，目前暂未开放   
![图片装载中](/images/mmdvm/jiqiao_changshouzu_dmr.png)  

刷机380 tool的用英文模板，看刷机部分说明获得下载地址  

官方公布的DMR组
http://www.pistar.uk/dmr_bm_talkgroups.php 

## 备份配置
![图片装载中](/images/mmdvm/nano_userguide_backup.png)   

## 重刷pi-star系统
准备工作：一张8G SD卡，USB卡套，   
下载地址： http://www.pistar.uk/downloads/  
Nano大屏幕版，选择 Pi-Star_RPi_XXX.zip  
Nano小蓝盒，选择 Pi-Star_NanoPi_XXX.zip  不要用错，用错启动不了！  
![图片装载中](/images/mmdvm/nano_userguide_reflashOS.png)   

1 安装格式化工具，格式化SD卡:  
下载地址：http://39.106.17.242/download/SDFormatterv4.zip  
2 安装镜像写入工具，写入pi-star镜像：
这里特别提醒，不格式化直接写入新的镜像，会导致oled屏幕花屏！  
http://39.106.17.242/download/win32diskimager-1.0.0-install.zip  
3 生成WiFi配置文件，拷贝到SD卡根目录，见本手册Wi-Fi配置部分，小蓝盒有网线口，此步骤可以忽略，大屏幕版没有网线，需要此操作。  

@BG2KJT @BG5UER 专为Nano小蓝盒提供了OLED显示IP/温度的镜像，方法见如下   

## 小蓝盒增加IP地址+温度显示  
此方法适合所有用户，操作简单，看图，刷前先准备一张空白的SD卡，一个SD卡USB卡套，用原来的SD卡也可以，4G以上建议8G，文件在群： 320533571        
![图片装载中](/images/mmdvm/jiqiao_FlashOSWithIP_TEMP.png)  


## Nano+大屏幕版显示IP地址
20171201 增加IP显示  
![图片装载中](/images/mmdvm/nano_userguide_nextion_ip.png)   

步骤  
1 下载驱动 http://39.106.17.242/download/NX4024T032_IP_BI7JTA.rar    
2 准备一张空白的SD卡，一个SD卡USB卡套，解压后将*.tft粘贴到SD卡根目录   
3 将屏幕上电，等待升级完成，如有异常则说明版本不对，目前仅支持Nextion 3.2寸屏幕，型号为 NX4024T032_11，其它规格加群索取  
4 断电，拔掉SD卡，正常启动pi-star系统  



## 几个概念
YSF  
反射器：Reflector 服务器(代理）、房间，作用同DMR的群组，C4FM（YSF）模式不能跨房间QSO  
鹦鹉：录音、回放程序，用于测试通联质量，丢包率，误码率等    

### DMR    
全呼：全网广播形式，漫无目的骚扰大，不建议使用，可以理解为广播；   
组呼：在特定的群组呼叫，如中国大陆有3个群组 460 46001 46007，只需登录任何一个BM服务器即可，可以理解为群聊；  
单呼：点对点呼叫，私聊，他人只能看到你的呼号，不能听到语音，与所在组无关，理解为一对一对话；  
数字联系人：通讯录，分为以上种类型，  
数字接收组：信道要监听的组呼列表，给信道使用  
组信息：对讲机可以有多个组，每个组下面包含多个信道成员，与组呼是两个概念，是手台外部按钮选择的信道分组    
扫描列表：待补充  
信道：每个联系人（单呼、组呼、全呼）一个通讯组，      
  

## 常见问题 Q&A
0. 如果切换到YSF模式出现无法连接网关、OLED显示 Startup，原因是装配时导入了旧的网关地址，需要更新pistar系统，点击右上角菜单的【更新/update】按钮即可  
![osc_archi](/images/mmdvm/nano_userguide_QA_ysferr.png)

1. 为什么首次上电后OLED屏幕不亮？需要接上网络，初始化完成，连上MMDVM服务器才能亮。  
2. Win7看到的SD卡只有64M或显示未被格式化，不要怀疑，是Win7不识别树莓派格式的磁盘。  
3. DMR模式手台如何进入46001？写频，手台调到对应的频道，按下PTT   
4. 直接访问 http://pi-star 有可能被QQ百度360等浏览器自作聪明重定向到官网，选用Chrome或火狐即可，或者直接用IP地址访问 @BD7LYV 反馈  
火狐浏览器地址：http://www.firefox.com.cn/download/  
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
![图片装载中](/images/mmdvm/nano_userguide_connectClose.png)   
正常连接服务器的日志  
![图片装载中](/images/mmdvm/nano_userguide_connectOK.png)   
Facebook讨论组提出过此问题，Pi-Star作者Andrew Taylor答复是：
目前，仪表板状态只检查从MMDVMHost到DMR网络的连接，所以在使用DMRGateway时 - 只能表明已经连接到DMRGateway（如澳大利亚、韩国是网关，澳大利亚到BM总服务器是上级链路）
![图片装载中](/images/mmdvm/nano_userguide_connectFacebook.png)   
建议：当怀疑连接异常是，点击仪表盘【Admin】【Live Log】看日志（要等一会才有日志，看历史日志使用SSH登录，见前面的截图方法）  
![图片装载中](/images/mmdvm/nano_userguide_liveLogs_menu.png)   
![图片装载中](/images/mmdvm/nano_userguide_liveLogs.png)   
 
8. TG9组霸占信道的解决方法  
原因： 曾经单呼/组呼了4400组，会一直占用信道，pi-star状态为 Active Ref
![图片装载中](/images/mmdvm/jiqiao_ActiveRef.jpg)  
作者提供的解决方法：单呼 4000，退出4400组（TG9），操作方法为手台添加一个联系人，单呼即可  
![图片装载中](/images/mmdvm/jiqiao_AndyAnswer.jpg)  
原理：TG9为特殊的组，不能通过触按PTT直接进入，需要拨号进入，拨号退出。 其实如想守听英国组，进入TG91即可，详见本博提供的MD380写频模板，其它机型一样的设置。   

9. 手台监听多个组的答疑  
关于md380同时监听多个组的问题，@BG5HRD 提出，  
同时监听多个组需满足以下条件：  
1 手台监听列表设置多个组（这里的多个组指的是“列表内的组的DMR数据过来会解码，不在列表的组信号会屏蔽，只会看到接收灯亮，这就是我们监听了3100美国组，切到46001后，灯闪但没有语音的原因），
2 触发网关监听，手台切到要监听的组46001，短按ptt，守听；再切到要监听的组460075（小蓝盒用户组），短按ptt，实现同时监听两个以上的组（实际上md380不用刷破解固件也可以同时监听），如图    
![图片装载中](/images/mmdvm/jiqiao_DynamicTGs.png)  

@BD7MQB：动态组好像是15分钟无发射就自动退出（待验证，据我观察只会不在仪表盘的动态监听出现，但一旦有数据过来，仍然会监听，但最多好像只能监听2个组）      

总结：具体能能同时监听多少个组，与pistar系统有关，和手台无关，手台只是解码和屏蔽。

静态监听组：BM网站设置
动态监听组：见上
Active Ref 嘈杂模式，如拨号把世界组TG9加入后，不管在不在手台的监听列表，都会解码，名副其实的流氓模式。  
![图片装载中](/images/mmdvm/jiqiao_activeRef.png)  


更多：等待你的补充，一起完善  
待解：同名WiFi多点部署漫游接入问题    
   

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
![图片装载中](/images/mmdvm/pistar_ssh_login_err.png) 

## 特别提醒
1.    

2. 不要点恢复出厂配置  
![图片装载中](/images/mmdvm/nano_userguide_fallback01.png)   
![图片装载中](/images/mmdvm/nano_userguide_fallback02.png)   

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
NanoPi_NEO 官方Wiki http://wiki.friendlyarm.com/wiki/index.php/NanoPi_NEO/zh  
DIY安装小风扇可以从GPIO取电 3.3V/GND，经测试3.3V足以，温度能降到40度，5.0V噪音略大。    

与NanoPi NEO搭配使用 [点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_gpio.png) 
 ![图片装载中](/images/mmdvm/nano_userguide_gpio.png)  

在树莓派3B使用，注意  
1. 插座顺序，Nano板规则边紧靠树莓派尾巴端，见图1    
[点击查看大图](http://www.aprspi.org/images/mmdvm/nano_userguide_rasp3b.png) 
![图片装载中](/images/mmdvm/nano_userguide_rasp3b.png)  

## 安装超薄风扇和散热片
待续

## 功能扩展
1、 需要蓝牙模块+BlueDV APP使用，可以自行参照GPIO 串口的定义，增加蓝牙模块，适合动手能力强的HAM DIY；  
2、需要连接Windows BlueDV 桌面程序使用，可以自行参照GPIO 串口的定义，增加USB to TTL模块，适合动手能力强的HAM DIY   
3、支持iOS版BLE、PC版MMDVM的扩展，需要可以加群讨论，需要动手能力     

## DMRid增长情况
![图片装载中](/images/mmdvm/nano_dmr_id_20171114.png)  


## md380/md380g刷机和调小功率到0.1瓦教程
参考BG5UER/VR2XKP教程  
玩转md380 QQ群：683111553    
### 刷机 
本教程刷机用于获得自动更新的全球DMRid呼号对应的通讯录  
注意点：  
1  刷机先把手台语言设置为英文，否则会乱码，具体在对讲机设置，菜单8；  
2  写入本博整理的英文的写频模板，中文模板必然乱码，写频方法见手册对讲机写频部分，   
MMDVM写频模板(英文)：http://39.106.17.242/download/TYT_MD380G_BI7JTA_v1206_EN_CN.zip   
MD380G写频软件（官方）：http://39.106.17.242/download/TYT_MD-380G.rar   
3 下载刷机工具包：http://39.106.17.242/download/TyteraFlashTool_v1_08_BETA.zip   
4 进入刷机模式方法：   
![配图加载失败](/images/mmdvm/nano_userguide_md380_flash_in_mode.png)   
  

### 图解刷机  
1 刷固件  
说明：这里在线下载通讯录后应该会显示全球Id数量，但没有显示不知何解@BH7JTB，该通讯录会每天更新，重复该操作即可同步通讯录    
![配图加载失败](/images/mmdvm/nano_userguide_md380_flash_BI7JTA.png)   

2  手台打开全球通讯录（只需执行一次）   
截图来自群文件《MD-380_380G 三方固件刷USERDB简易教程 - by BG5UER.pdf》  
![配图加载失败](/images/mmdvm/nano_userguide_md380_flash_ShowCallSign.png) 

3 效果图，如果达不到此效果，则重头再来  
![配图加载失败](/images/mmdvm/nano_userguide_md380_flash_result.png)  

### 调小到0.1瓦功率，保护你的秀发  
截图摘自群文件 《MD-380 多檔輸出火數初探 _ VR2XKP\'s blog.pdf》   
1 设置测试模式    
![配图加载失败](/images/mmdvm/nano_userguide_md380_LowPWR_setting.png)   

2 打开MD380G写频软件（官方），按Ctrl+T快捷键进入测试模式，修改参数如图    
![配图加载失败](/images/mmdvm/nano_userguide_md380_LowPWR_UISetting.png)   

有问题Q群交流，谢谢！附上@BD7ILU 大神的刷机视频  
http://i.youku.com/bi7jta  


## 广而告之：Nano小蓝盒 for MMDVM热点板链接 
Nano小蓝盒快速入门版：  
[https://item.taobao.com/item.htm?id=561964266288](https://item.taobao.com/item.htm?id=561964266288)   
Nano+大屏豪华版：  
[https://item.taobao.com/item.htm?id=561607171659](https://item.taobao.com/item.htm?id=561607171659)   
Nano创客空间(小店)：  
[https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02](https://shop113103301.taobao.com/?spm=2013.1.1000126.d21.767a371c9FIc02)  
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)     



提问题请加入Q群： 320533571  QQ/微信：38091676
（持续更新）







