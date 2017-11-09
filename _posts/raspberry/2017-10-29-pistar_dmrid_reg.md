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
代申请DMR-ID请加Nano MMDVM交流群 320533571 后，按照以下的要求发送资料到我的邮箱 38091476@qq.com   
格式：你的姓名、所在城市（无需业余无线电执照），在收到邮件后按照提示回复执照拍照件即可    

https://www.dmr-marc.net/cgi-bin/trbo-database/userreg.cgi  
![osc_archi](/images/raspberry/reg_dmrid_notqrz.png)

![osc_archi](/images/raspberry/reg_dmrid_qrz.png)

完整的申请过程（24小时内完成）[点击查看大图](http://www.aprspi.org/images/mmdvm/dmr_id_reg.png)   
![osc_archi](/images/mmdvm/dmr_id_reg.png)

## qrz.com 注册地址（不玩短波请忽略）http://www.qrz.com/db/BI7JTA 说明：需要实名HAM先添加呼号到数据库，再注册，如有需要请 发邮件给我。qrz主要用于全球HAM查询QSL地址和记录短波QSO日志用，建议玩短波的都要注册，方便对方了解你。

## 其它说明
20171031补充：  
1、QQ邮箱证明是可以收到DMR确认邮件的；   
2、回复有效期内的业余无线电执照（带呼号那张），很快能收到DMR-ID；  
 
在MMDVM pi-star 配置界面，如果使用到DMR模式，则需要用到DMR-ID，否则无法联网。  其他模式可以不用申请，不过为了玩DMR设备做准备，建议还是申请一个，不玩DMR数字就白玩了，C4FM用多了会变傻，DMR有如CW，练脑。  
选择省份（State）时，必须选对你所在区的QSO，如你在7区，就选4607，其中460是中国，4607是中国的7区，其它类推，不用关注是否有你的省份，老外没考虑这么周全。  
![osc_archi](/images/raspberry/reg_dmrid_pistar.png)

## 导出全网DMR-ID
全球用户类型：  
http://www.dmr-marc.net/cgi-bin/trbo-database/datadump.cgi?table=users&format=csv&header=1  

全球中继类型：   
http://www.dmr-marc.net/cgi-bin/trbo-database/datadump.cgi?table= repeaters&format=csv&header=1  

作用：制作各种机型的通讯录  

## 一些技巧
1）DMR服务器状态在线查看：  
https://brandmeister.network/?page=hotspot-edit&id=4607064    
2）在线收听QSO：  
**地址待补充，欢迎加群提供  
3）修改DMR-ID的默认密码 passw0rd，避免他人盗用    
**地址待补充，欢迎加群提供 

提问题请加入Q群：Nano MMDVM技术交流 320533571 
（完）





