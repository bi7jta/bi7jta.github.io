---
layout: article
title: 重刷Pi-Star系统指引  
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /mmdvm/flash_os_thumb.png
#    thumb:
---

交流Q群 320533571    

> 本文内容：如何刷卡升级系统，适用于不能在线升级系统的情况      


> 文章欢迎转载
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>   
 
#### 新博客更精彩 [http://mmdvm.io/](http://mmdvm.io/)  

## 目的
刷SD卡方式升级系统  
刷卡前可以尝试在线升级   

http://pi-star:2222 (或用IP地址)   
用户名： pi-star  
密 码： raspberry  
执行：  
sudo pistar-update && sudo pistar-upgrade  [多执行几遍一次升级一个版本]   

![图片装载中](/images/mmdvm/flash_os_online.png)   

Youku视频：  
[https://v.youku.com/v_show/id_XMzY5MjE5MjE4OA==.html?spm=a2hzp.8244740.0.0](https://v.youku.com/v_show/id_XMzY5MjE5MjE4OA==.html?spm=a2hzp.8244740.0.0)  

##### 使用HDMI高清输出检查系统启动日志
对应无法获得IP的情况，如果是树莓派用户，使用HDMI高清输出查看；对于NanoPi用户，可以用USBtoTTL连接电脑，查看系统启动日志。  
无法启动常见问题有：电源不符合5V2A，路由器不分配IP，刷错系统，SD卡不支持启动树莓派 等。


## 开始刷卡，步骤
1） 准备一张8G的SD卡，一个USB TF卡适配器，如图      
![图片装载中](/images/mmdvm/flash_os_adapter.png)    

2) 下载对应的镜像，NanoPi小蓝盒务必使用NanoPi的版本   
http://www.pistar.uk/downloads/  3B,Pi Zero W   
http://www.pistar.uk/beta/ 3B+ 
![图片装载中](/images/mmdvm/flash_os_download.png)  

3）准备两个写卡工具    
任意搜索引擎可以搜索并下载，QQ群696968360群文件也有下载   
SDFormatter 格式化工具    
Win32DiskImager 写卡工具  
![图片装载中](/images/mmdvm/flash_os_tools.png)  

4) 解压下载后的镜像文件，将.IMG文件写入到SD卡  
先用SDFormatter格式化  
![图片装载中](/images/mmdvm/flash_os_format.png)  

再选择.IMG镜像文件写入到SD卡（不是直接复制粘贴）   
![图片装载中](/images/mmdvm/flash_os_write.png)    

5）完成，先不要拔卡

## 配置网络  
如果有网线连接路由器，建议直接在Pi-Star配置页面，添加WiFi配置即可。不使用网线连接，直接配置WiFi如下：  
拷贝WiFi配置文件到SD卡根目录  
生成WiFi配置文件地址 http://www.pistar.uk/wifi_builder.php  
![图片装载中](/images/mmdvm/flash_os_WiFi.png)   

## 配置Pi-Star系统
只有正确配置完成，并正常联网后，才能点亮OLED屏幕！  
1） 将SD卡插入NanoPi或者树莓派，电脑浏览器访问 http://pi-star   
务必不要使用IE等浏览器，QQ 360等浏览器访问上述地址如果异常，则要找到NanoPi的IP地址，直接访问IP地址。   
推荐使用Chrome或火狐 http://www.firefox.com.cn/download/  

2） 参考以下图配置，请在测试时只选择一种模式，然后点击保存，待页面刷新后，详细配置才会出现。   
单工模式（适用于所有单工热点）  
![图片装载中](/images/mmdvm/flash_os_Config_SS.png)  

双工模式（适用于双工板，中继板）  


## 详细教程见
![图片装载中](/images/mmdvm/flash_os_guide_detail.png)   

http://www.aprspi.org/mmdvm/nano_mmdvm_userguide/  

如果误码率高，则进入高级模式调整RXOffSet TXOffSet  
http://www.aprspi.org/mmdvm/abjust-BER/    
建议DMR 1%， YSF 2%以内，不影响通联的情况下，视为正常。   

最后提议：   
多通联，涨经验。常守TG 46001, 460755 ，多来频率找我，少用QQ微信，当然关注我的微信朋友圈也是可以的，微信专注于业余无线电发烧，不定期放毒。  
个人微信QQ号：38091476   
MMDVM公众号：bi7jta73    

## 获得设备   
淘宝小店  
[https://shop113103301.taobao.com](https://shop113103301.taobao.com)    
![图片装载中](/images/mmdvm/nano_userguide_taobao.png)     

