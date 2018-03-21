---
layout: article
title: 
categories: mmdvm
#excerpt:
#tags: []
image:
    teaser: /support/duplex_userguide_thumb.png
#    thumb:
---
 
> summary： Guidance for Nano Series Duplex hotSPOT
 
> Collate： bi7jta@gmail.com   
 
### How to use Nano Series Duplex hotSPOT?  
#### 1st  Get ready for pi-star OS,Connect SMA ANT,Connect RPi to hotSPOT use GPIO.   
#### 2nd  Controller Mode:Duplex Repeater (also make sure expert Duplex flag 1 not 0)  
http://pi-star/admin/configure.php  
http://pi-star/admin/expert/edit_mmdvmhost.php   

#### 3rd  set RX/TX Frequency ,support UHF and VHF,like  
RXFrequency  434755000  
TXFrequency  439755000   
NOTE: set UHF TX - RX > 5MHZ to Get better performance 
Just work at amateur frequencies, and different countries have different amateur frequencies.    

#### 4th set Offset in section   
RXOffset=-300    
TXOffset=-300  
NOTE：If not set,Error Rate % will hight, -300 is the offset of this bath 14.7456MHz TCXO offset.
You can also abjust the parameters that make the Error Rate % to the lowest.

#### 5th DMR, Set Static Talkgroups for Timeslot 1 and Timeslot 2  (Fist Login)  
eg. https://brandmeister.network/?page=hotspot-edit&id=4600060    
NOTE:Can use 4600060XX XX is 01~99 ,for different hotSPOT  

### All update status will publish to email group  
https://groups.io/g/nano-mmdvm or join facebook userGroup   
https://www.facebook.com/groups/nano.mmdvm/  

![图片装载中](/images/user_guide_where_tx.png)   
[点击查看大图](https://github.com/nano-mmdvm/Duplex_hotSPOT/raw/master/images/user_guide_where_tx.png)  
 
 

Continue update ...   

Contract me: bi7jta@gmail.com  







