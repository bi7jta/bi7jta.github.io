---
layout: article
title: MMDVM Pi-Star Web控制台免登录使用
categories: raspberry
#excerpt:
#tags: []
image:
    teaser: /raspberry/disable_password_thumb.jpg
#    thumb:
---


> 本文介绍如何免登录使用Web管理控制台，适合局域网使用，暴露在公网时不建议使用。

> 文章欢迎转载，但转载时请保留本段文字，并置于文章的顶部  
> 作者：BI7JTA  
> 本文原文地址：<http://www.aprspi.org{{ page.url }}>

## 为什么要这样做？
资料来源：http://wiki.pistar.uk/Main_Page 
 
当我们使用手机WiFi热点+MMDVM热点时，很多时候需要访问pi-star的Web控制台，但每次进入配置界面都要输入用户名和密码，相当不友好。
![osc_archi](/images/raspberry/disable_password_big.jpg)

作者提供了免输入密码的方法。如图  

![osc_archi](/images/raspberry/disable_password.png)
 
适合局域网使用，暴露在公网时不建议使用。  

几条命令：

rpi-rw 

sudo nano /etc/nginx/sites-enabled/pi-star   
  #为注释掉的认证内容  

       location ^~ /admin {  
       #        try_files $uri $uri/ =404;  
       #        auth_basic "Restricted";  
       #        auth_basic_user_file /var/www/.htpasswd;  
               client_max_body_size 512K;    
       include             /etc/nginx/default.d/php.conf;
       }  
       
sudo systemctl restart nginx.service  

提问题请加入Q群：树莓派APRS 290347330    
（完）





