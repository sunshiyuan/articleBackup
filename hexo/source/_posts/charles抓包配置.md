---
title: charles抓包配置
date: 2018-05-09 09:54:27
tags:
---
### charles抓包配置
1. HTTP抓包
2. HTTPS抓包
#### charles配置
##### charles安装下载
 官方地址:<a href="https://www.charlesproxy.com/download/">https://www.charlesproxy.com/download/</a>
官网下载安装可使用不购买的话大概是30分钟断开一次，需要重新连接
破解地址:<a href="http://xclient.info/s/charles.html?t=c5c0a61812b8ac452505575bedc9601108f24fe5">http://xclient.info/s/charles.html?t=c5c0a61812b8ac452505575bedc9601108f24fe5</a>

<!-- more -->
##### http抓包
保证电脑和手机在同一网段上，让手机连上电脑的热点
查看本机ip地址
![](2018-05-09-11-01-38.jpg)
手机HTTP代理设置
HTTP代理设置成手动方式，服务器地址设置为电脑ip地址，端口号为8888
![](2018-05-09-11-05-51.jpg)
需要在电脑上打开charles才能上网
##### https抓包
https抓包方式是在http基础上进行配置的
首先对charles配置证书 charles中Help-->SSL Proxying--> install Charles Root Certificate 证书 
![](2018-05-09-11-10-35.jpg)
在钥匙串中找到这个证书设置成始终信任
![](2018-05-09-11-20-28.jpg)
端口配置
proxy------> Proxy settings端口号配置成 8888  
![](2018-05-09-11-13-38.png)
proxt ----->ssl proxying setting
配置所有网址443端口的https请求
![](2018-05-09-11-16-09.png)
手机端证书的安装
Help--------->SSL Proxying --->install charles root certificate on a mobile device
或者 CA证书下载链接：https://www.charlesproxy.com/documentation/additional/legacy-ssl-proxying/

![](2018-05-09-11-18-11.jpg)
弹出
![](2018-05-09-11-19-03.jpg)
在手机浏览器上输入 chls.pro/ssl 下载证书安装
在iOS 10.3系统，需要在 设置→通用→关于本机→证书信任设置 里面启用完全信任Charles证书


![](91AC3335179CD117BD44CBC38B6098F0.png)

这样就可以抓取https包啦 如下
![](2018-05-09-11-26-41.jpg)
可以抓取某个host的https包
![](2018-05-09-11-27-48.jpg)


ln  -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport  /usr/local/Cellar/aircrack-ng
