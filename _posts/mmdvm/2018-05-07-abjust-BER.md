---
layout: article
title: MMDVM热点板误码率调整方法 
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/BER_abjust_thumb.png
#    thumb:
---

20171105 交流Q群 320533571     

> 本文内容：阐述MMDVM热点板误码率的调整方法       


> 文章欢迎转载
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>   
 
## 概念
首先我们要了解什么是误码率  
误比特率（英语：bit error rate，BER）是指单位时间差错比特的数量。 比特差错率（即误码率，英语：bit error ratio，BER）是一段时间内差错比特的数量除以传输的总比特数。 BER是一种无单位的性能指标，通常以百分比的形式表示。  
比特误码率- 维基百科，自由的百科全书  
https://zh.wikipedia.org/zh-hans/比特误码率  

## 关键部件 
TCXO，晶振，知道有这个关键部件就好，不想阐述太多，因为一大波潜在的山寨王潜伏在周围，他们不玩无线电，甚至没有合法的业余无线电License，他们仅仅是个廉价货加工厂，软妹币复印机，这是我的观点。   

看一个热点板（TCXO）质量是否达标，一个重要的参数是   
1）误码率是否稳定，可调节，如果同一批次的晶振，有些高有些低（DMR模式或YSF-VW模式>2%），则会影响通联效果   
2）调整误码率到1%以内，RXOffset和TXOffset的值是否一致，如否，也不是好的   

据我所知，国内某些克隆成品，偏移量Offset甚至大于1000，大于等于500为凑合，不知道用户如何忍受。 
小蓝盒的偏移量在200以内，出厂默认值+200能获得0.5%以下甚至更低的误码率   

特别提醒，如果调整的Offset绝对值过大，说明所使用的晶振TCXO偏移量太大，使用了不合格的物料，正常情况下是 14.7456MHz，PPM在+-2.5ppm范围内（MMDVM原作者要求在2ppm范围内），大于1000且RXOffset，TXOffset不一致，建议直接垃圾桶，以免影响玩无线电的兴致，浪费的时间和省钱相比，不言而喻，所以不要贪图一时便宜。  

## 影响误码率的可能原因 
1 物料的选用，TCXO是关键，其次是收发模块    
2 接入电台频率偏移值（频偏）  
3 电磁环境，同频率干扰，障碍物（隔墙），距离，手台发射功率，  
4 电源供电，电源线规格等是否满足5V2A，是否稳定  
5 环境和主板温度，合理的CPU温度在30~60度之间  
如何应对？根据上面的原因区分对待调整，  
题外话：JTA系列的中继板，外接GM300等车台，实测误码率比内置模块要降低很多 

关于误码率，原因有很多，只要设置参数后不漂移，就可以了，合理值DMR在2%以内，YSF的DN模式会偏高，VW模式接近DM，YSF模式下可以再做细调。不同的终端存在不同的频偏，误码率可能不一样，在能正常通联话音不失真相互报告59的前提下，不建议过于纠结误码率，绝对0%没多大意义

## 如何降低误码率
先看两张截图  
[点击查看大图](http://www.aprspi.org/images/mmdvm/BER_abjust_Dashboard.png)   
![图片装载中](/images/mmdvm/BER_abjust_Dashboard.png)  

[点击查看大图](http://www.aprspi.org/images/mmdvm/BER_abjust_Expert.png)   
![图片装载中](/images/mmdvm/BER_abjust_Expert.png)  

1 如果误码率高，或者没收发，则进入高级（专家）模式，调整偏移参数Offset参数，官方版本的默认为0
参数说明：
RXOffset 接收偏移修正（终端电台到热点板，体现在pi-star仪表盘的误码率）  
TXOffset 发射偏移修正（热点板到终端电台，体现在手台解码时是否能正常解码）  
单工热点上面两个参数设置成一样即可，  
Nano hotSPOT 小蓝盒：Pi-star出厂默认+200，如果误码仍然偏高，则设置为0。  
 
其他热点偏移量：  
forRPi 带风扇热点板：-300  
Duplex hotSPOT 双工热点：-300    

中继板的误码率跟RX/TXLevel 有关，无需调整RX/TXOffset  

调整后点击【应用设置】，无需重启热点，在仪表盘页面，按PTT，看误码率，或者在SSH日志查看  
命令 tail -100f /var/log/pi-star/MMDVM-2018-03-04.log 截图1  

专家模式入口：http://pi-star/admin/expert/edit_mmdvmhost.php  
用户名：pi-star  
密码： raspberry  

建议打开一个专门的专家模式页签。也可以尝试按照二分法设置，以最终的误码率RF降到最低为准  

 更多内容也可以参考 @BG3DHE 整理的文档，来自 交流Q群 320533571 的文件共享     

## 其它技巧：  
1）多个热点板同时使用一个DMRid测试时，可以在DMRid后面添加两位数字，代表不同的识别。经测试，有时候不好用，发射后网络对方没有接收，或者收发只有一边正常。  

2）如果使用不同的DMRid、呼号、呼号后缀，访问MMDVM热点，则要将节点类型改为 【public】公开模式，默认的私有模式【private】只运行同DMRid和呼号完全匹配的数据转发。  

3）测试回音可以用 单呼4601国服的鹦鹉组 9990，得到自己的重放语音；或者使用单呼 4000，得到一个Disconected 的回波

其他：如何不刷卡直接升级到最新版本，待补充。  


小蓝盒以及MMDVM热板 https://shop113103301.taobao.com     
DMRid申请（新版） https://mmdvm.wufoo.com/forms/mmdvm-dmridaecee/    
我们只做精品  

## 获得设备    
[https://item.taobao.com/item.htm?id=561964266288](https://item.taobao.com/item.htm?id=561964266288)  

[https://shop113103301.taobao.com](https://shop113103301.taobao.com)    
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)     

