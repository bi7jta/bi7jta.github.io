---
layout: article
title: MMDVM-如何分析日志
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/view_log_thumb.png
#    thumb:
---


> 本文内容：如何分析和下载日志，

> 免责声明：本博只提供方法，不提供手把手指导！请多百度和QQ群交流，时间就是钱，你懂的，这种问题每天回答N遍，也很烦  
> 文章欢迎转载
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}> 


## 1 网页查看，最傻瓜！
http://pi-star/admin/live_modem_log.php  
把pi-star替换成IP地址，如果不能访问，至于如何做，复习本博【手册】文章。此方法缺点是只能看往后的日志，不能看之前的日志，鸡肋！  
用户： pi-star  
密码： raspberry  

![图片装载中](/images/mmdvm/viewlog_live_log.png)   

## 2 SSH终端实时查看  
该方法适合自行分析解决问题，强烈推荐，90%问题都能自己解决，看不懂英文截图放QQ群寻求帮助  
下载客户端，putty 
https://the.earth.li/~sgtatham/putty/latest/w32/putty.exe

![图片装载中](/images/mmdvm/viewlog_ssh_log.png)   

## 3 下载日志文件  
该方法适合自己搞不定，发完整日志给别人分析    
下载客户端 WinSCP 
http://sw.bos.baidu.com/sw-search-sp/software/3864375932977/WinSCP-5.11.2.7781-Setup.exe

![图片装载中](/images/mmdvm/viewlog_scp_log.png)   

## 广告
Nano创客空间(小店) MMDVM 热点/中继板/双工板/树莓派大板/3D打印：  
[https://shop113103301.taobao.com ](https://shop113103301.taobao.com )   
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)     



提问题请加入Q群 320533571  QQ/微信 8091676 
（持续更新）







