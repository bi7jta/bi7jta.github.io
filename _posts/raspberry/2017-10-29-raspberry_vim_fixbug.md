---
layout: article
title: 树莓派系统Raspbian OS修复vim键盘bug
categories: raspberry
#excerpt:
#tags: []
image:
    teaser: /raspberry/vim_400.png
#    thumb:
---


> 本文介绍如何卸载树莓派系统精简版vim，安装完整版vim

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 为什么要这样做？
树莓派系统（raspbian OS debian的一个子版本）默认的vim编辑器很蛋疼，进入编辑装在键盘上下键全变成了CCC+换行，这是因为系统默安装了精简版的vim，要使用完整版的vim才符合我们使用习惯。当然你临时用的话，直接用 nano 命令编辑文本文件也可以，如：
sudo nano /home/pi/nanoHotSPOT.txt 但在NanoPi 系统中，并没有安装nano编辑器。  

树莓派重新安装vim  
sudo apt-get -y remove vim-common  
sudo apt-get install -y vim  

如果出错，  
Package vim is not available, but is referred to by another package  
或 
E: Package 'vim' has no installation candidate
则先执行  
apt-get update  
apt-get upgrade 
 
最好先设置翻墙代理，国内的网络玩树莓派很蛋疼，虽然可以改apt-get安装源为国内的镜像，但某些宽带运营商，如长城宽带会做CDN缓存，缓存规则是一坨屎，永远不会更新，md5 Hash Sum mismatch 检验也是错的，

树莓派的apt-get代理配置：
sudo nano /etc/apt/apt.conf.d/10proxy   
增加一行：
Acquire::http::Proxy "http://翻墙服务器IP:PORT"; （一定要带后面的；）

如果没有安装nano编辑器，则者用WinSCP等工具把文件10proxy编辑好，上传到/etc/apt/apt.conf.d目录

例行配图：
![osc_archi](/images/raspberry/vim.png)

提问题请加入Q群：树莓派APRS 290347330
（完）





