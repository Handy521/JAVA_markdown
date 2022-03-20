## 一 、server.xml
启动端口号配置

tomcat的默认端口号为：8080
mysql：3306
http：80
https：443

<Connector port="8081" protocol="HTTP/1.1"
connectionTimeout="20000"
redirectPort="8443" />
配置主机名称

默认的主机名为：localhost->127.0.0.1
默认网站应用存放的位置为：webapps

<Host name="www.qinjiang.com" appBase="webapps"
unpackWARs="true" autoDeploy="true">
这里改成其他域名访问不到，实际是访问127.0.0.1，需要配置host才能访问其他域名
## 二、请你谈谈网站是如何访问的:
1.输入网址 回车
2.检查本机的系统文件hosts配置文件下有没有这个域名映射
——-1.有:直接返回对应的ip地址,在这个地址中,有我们需要访问的web程序,可以直接访问
——-2.没有:去DNS服务器找,找到就返回,找不到就返回找不到
![](https://kuangstudy.oss-cn-beijing.aliyuncs.com/bbs/2021/07/08/kuangstudy7e6c7094-3b69-4b79-a24b-40c78f37e2cf.png)

## 三、发布一个网站
将自己写的网站，放到服务器（Tomcat）中指定的web应用文件夹（webapps）下，就可以访问网站应该有的结构
```	
--webapps： Tomcat服务器的web目录
   -ROOT
   -kuangstudy:网站的目录名
           - WEB-INF
	      -classes:
		  -lib:
	      -web.xml
	   - index.html
	   - static
	       -css
		   -js
		   -img
```
## TCP/IP 四层模型
应用层，传输层，网络层，网络接口层
### 应用层（Application layer）
应用层位于传输层之上，主要提供两个终端设备上的应用程序之间信息交换的服务，它定义了信息交换的格式，消息会交给下一层传输层来传输。我们把应用层交互的数据单元称为报文。应用层协议定义了网络通信规则，对于不同的网络应用需要不同的应用层协议。在互联网中应用层协议很多，如支持 Web 应用的 HTTP 协议，ftp ssh smtp  
telnet连接的时候直接建立TCP连接，所有传输的数据都是明文传输，所以是一种不安全的方式。  
SSH 为Secrue Shell的缩写，SSH 为建立在应用层基础上的安全协议，是比较可靠安全的协议。	
### 传输层（Transport layer）
传输层的主要任务就是负责向两台终端设备进程之间的通信提供通用的数据传输服务。 应用进程利用该服务传送应用层报文。“通用的”是指并不针对某一个特定的网络应用，而是多种应用可以使用同一个运输层服务。  
端口（port） ：端口的目的是为了确认对方机器的哪个进程在与自己进行交互。端口又称协议端口号。  
运输层主要使用以下两种协议：

传输控制协议 TCP（Transmisson Control Protocol）--提供面向连接的，可靠的数据传输服务。  
用户数据协议 UDP（User Datagram Protocol）--提供无连接的，尽最大努力的数据传输服务（不保证数据传输的可靠性）。  
19.运输连接的三个阶段，即连接建立，数据传送和连接释放。  
20.主动发起TCP连接建立的应用进程叫做客户，而被动等待连接建立的应用进程叫做服务器。TCP连接采用三报文握手机制。服务器要确认用户的连接请求，然后客户要对服务器的确认进行确认。
