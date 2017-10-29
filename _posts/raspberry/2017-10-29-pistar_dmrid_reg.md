---
layout: article
title: MMDVM DMR-ID注册注意事项
categories: raspberry
#excerpt:
#tags: []
image:
    teaser: /raspberry/reg_dmrid_thumb.png
#    thumb:
---


> 本文介绍注册DMR-ID的技巧和DMR-ID查询和导出全网通讯录

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 注册地址（需要翻墙）
https://www.dmr-marc.net/cgi-bin/trbo-database/userreg.cgi  
![osc_archi](/images/raspberry/reg_dmrid_notqrz.png)

![osc_archi](/images/raspberry/reg_dmrid_qrz.png)

## qrz.com 注册地址：
 
MMDVM pi-star 配置界面如果用到DMR模式，则需要用到DMR-ID，否则无法联网。  
![osc_archi](/images/raspberry/reg_dmrid_pistar.png)

## 导出全网DMR-ID
全球用户类型：  
http://www.dmr-marc.net/cgi-bin/trbo-database/datadump.cgi?table=users&format=csv&header=1  

全球中继类型：   
http://www.dmr-marc.net/cgi-bin/trbo-database/datadump.cgi?table= repeaters&format=csv&header=1  

作用：制作各种机型的通讯录  

## DMR服务器状态在线查看
状态：  
https://brandmeister.network/?page=hotspot-edit&id=4607064  

收听QSO：
待补充

提问题请加入Q群：树莓派APRS 290347330
（完）




