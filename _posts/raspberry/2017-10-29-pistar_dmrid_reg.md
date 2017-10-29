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

## qrz.com 注册地址：http://www.qrz.com/db/BI7JTA 说明：需要实名HAM先添加呼号到数据库，再注册，如有需要请在Q群里[290347330]联系我，提供图示的信息，申请一天后查看自己的邮箱，如果提示要执照，拍照回复。
 
MMDVM pi-star 配置界面如果用到DMR模式，则需要用到DMR-ID，否则无法联网。  其他模式可以不用申请，不过为了玩DMR设备做准备，建议还是申请一个。  选择省份时，必须选对，否则组呼所在区的QSO，会被忽略掉（类似于组群）。  
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





