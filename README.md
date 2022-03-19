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
# JAVA_markdown
