---
layout: article
title: 获得iPhone Wi-Fi热点pi-star的IP方法
categories: raspberry
#excerpt:
#tags: []
image:
    teaser: /raspberry/get_WiFi_HotSPOT_thumb.png
#    thumb:
---


> 本文介绍获得iPhone Wi-Fi热点pi-star的IP方法，实用iOS APP推荐

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 思路
来自Facebook讨论组 https://www.facebook.com/groups/pistar/

平时用iPhone Wi-Fi热点访问 pi-star 仪表盘最抓狂的事莫过于无法访问了，由于手机热点组网DHCP ARP等在Apple iOS中有很多限制，导致 hostname主机名 pi-star.local 迟迟未能被广播出来，另一种情况是一个wifi热点接入多个MMDVM热点板网关，pi-star冲突，无法得知到底该访问哪一个主机。http://pi-star.local 访问失败  
![osc_archi](/images/raspberry/get_WiFi_HotSPOT_IP2.png)

很庆幸的事我把这个问题在pi-star 讨论组一提出，就有全球各地的爱好者跟帖回复提供方案，  
![osc_archi](/images/raspberry/get_WiFi_HotSPOT_IP.png)

其中  
第一种是使用iPhone APP【Fing】，这种在Wifi热点所在的设备上是无法获得Wifi路由信息的，此时只有4G，只有安装在第二台接入wifi热点的iOS设备，才能获得当前局域网的所有IP列表，不实用放弃；

第二种是使用APP【iNet Network Scanner】，Good jobs！ It work！  App Store地址 
https://itunes.apple.com/cn/app/inet-network-scanner/id340793353?mt=8    

![osc_archi](/images/raspberry/get_WiFi_HotSPOT_Cut.png)
[点击查看大图](http://www.aprspi.org/images/raspberry/get_WiFi_HotSPOT_Cut.png)   

这里有个搞笑的事情：老外到底看不看得懂中文，利用Facebook的翻译？  
![osc_archi](/images/raspberry/get_WiFi_HotSPOT_CN.png)

结果是可以的，照样有跟帖。  
![osc_archi](/images/raspberry/get_WiFi_HotSPOT_CN2.png)

最后分享一款iOS的SSH客户端，可以直接ssh到pi-star，经试验大多数情况下使用pi-star.local 访问也是可以的。
https://itunes.apple.com/cn/app/termius/id549039908?mt=8 

吐槽一件事：  
关于翻墙，由于19大大，好几天往香港SS的VPN隧道被封禁，Twitter Facebook Google全不能上，感觉壮士断臂，无所适从。什么时候才不再闭关锁国？难道要等15亿中国农民民智全开？欲盖弥彰。  

提问题请加入Q群：树莓派APRS 290347330
（完）





