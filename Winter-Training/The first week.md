今天已然星期六了，是时候写下writeup了（本来应该是做完就写的，太懒了，拖到现在一块写）

#web

* ### web从0开始之0	 
        WEB页面的HTML，CSS，JS客户端是可以查看的哦～你能在平台的源码中找到FLAG么？
直接f12搜hctf

* ### web从0开始之0.1
        你知道一个网页从输入URL到显示出页面，都经历了啥么？http://ctf.lazysheep.cc:8080/
用firebug查看http header 里面有flag

* ### web从0开始之0.2	
        你知道啥是cookie吗？那么你会修改它吗？http://ctf.lazysheep.cc:8080/web0-2.php
谷歌了下cookie的相关知识（对于这题来说没必要）
chrome下了个修改cookie的扩展

    ![Paste_Image.png](http://upload-images.jianshu.io/upload_images/1561592-0371e7039f2435e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    发现其值为false，便修改为true，刷新，得flag
 
---

# MISC

* ### MISC从0开始之编码0
base64解密

* ### MISC从0开始之Steganography0
给出了一张图片，用stegesolve打开

    ![Paste_Image.png](http://upload-images.jianshu.io/upload_images/1561592-ab4b3b0ba6159d7b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    flag直接包含在了图片信息里
  
    可以看下这篇文章，介绍的很不错 http://drops.wooyun.org/tips/4862

* ### MISC从0开始之流量分析0	
题目给了一个pcap文件，用wireshark分析后发现一个请求特别大，于是追踪tcp流，发现flag

* ### CTF coding step0	
        打CTF就是拿工具？ 不不不，也要写很多代码的。这个系列就是让你熟悉CTF风格的编程题目，具体的要求见题目吧のの 就是让你们多看点英文：nc 115.29.77.78 9999
第一次做时连上后出来一堆英语（挺简单的英语==所以以后再见到有英语的题不要怕），就是让你向这个服务器的端口发送几百个A，知道是写个程序实现，但完全没学过            

  等过了几天又想来试一下，学习了socket编程，照着网上的代码敲了一遍，不会的再去搜（坑太多了），就这样做了出来。不过写个程序拿flag的感觉比用工具爽多了！
  
---

#密码学
* ### 密码学从0开始之0	

        ojam{AopzpzJhlzhyWhzzdvyk}
凯撒密码

---

#PENTEST

* ### lightless的渗透教室-1

        http://120.27.53.238/pentest/01/http-method.php
向该页面同时发送GET和POST请求，之前一直用的工具，突然想用curl命令，结果成功了（原来敲命令这么简单==） 

        curl 120.27.53.238/pentest/01/http-method.php?param1=HelloGet curl -X POST --data "param2=HelloPost" 120.27.53.238/pentest/01/http-method.php
由此也发现了ubuntu命令可以多个同时执行

后来才发现是理解错了，以为是同时发送两个请求，事实是用一个post请求来实现

---

**总结：
第一周的培训还是以基础为主，通过做题学到了有关http请求的知识，一些ctf工具大致会用了。
但花的时间也过长。
路漫漫其修远兮，吾将上下而求索**
