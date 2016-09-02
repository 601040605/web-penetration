由于比赛是CTF和linux 实战渗透的结合，比赛的前后整理了关于主机常见端口漏洞。

## 21端口
FTP(file Transfer Protocol)文件传输协议  
1.匿名访问——未授权访问  
2.弱密码  
3.配置不当 直接 cd / && dir  
4.FTP使用明文传输技术-嗅探

## 22端口
SSH SSH服务基本会出现在我们的linux服务器、网络设备上，而且SSH服务开启后的设置很多都是默认的  
1.弱口令  
2.防火墙SSH后门  
3.28退格 OpenSSL

## 23端口
TLENET  
弱口令

## 53端口
DNS域传送信息泄露  dig axfr @xx.xx.xx.xx xx.xx.xx.xx  
DNS劫持  
DNS缓存投毒  
DNS欺骗  
DNS隧道技术刺穿防火墙

## 81端口
ipcam的web端口  
弱口令123端口  
NTP（Network Time Protocol）它是用来同步网络中各个计算机的时间的协议。  
1.可以基于NTP的反射和放大攻击  
2.NTP反射型doos攻击

## 389端口
LDAP协议 轻量级目录访问协议  
1.注入  
2.未授权访问  
3.弱密码

## 443端口
heartbleed心脏出血

## 873端口
RSYNC 远程同步功能  
1.匿名访问  
2.弱口令  
rsync xxx.xxx.xxx.xxx::

## 1352端口
Louts  
1.弱口令  
2.文件泄露  
http://**.**.**.**/names.nsf/

## 1433端口
mssql  
弱口令

## 1521端口
ocral  
1.弱口令  
2.溢出

## 2375端口
docker remote api  
接口未授权访问  
访问 http://xxx.xxx.xxx.xxx:2375/containers/json 会返回服务器的container列表  
docker -H tcp://xxx.xxx.xxx.xxx:2375 images  
docker -H tcp://xxx.xxx.xxx.xxx:2375 run -it --entrypoint /bin/bash ubuntu "-h"

## 3306端口
mysql  
弱口令  

## 5000端口
SysBase  
1.弱口令  
2.命令注入

## 5432端口
PostgreSQL  
弱口令

## 6379端口
redis  
未授权访问利用redis写getshall  
redis-cli -h xxx.xxx.xxx.xxx -p 6379

## 7001端口
weblogic  
弱口令   http://xxx.xxx.xxx.xxx:7001/console/login/LoginForm.jsp  
weblogic/weblogic  
可探测内网

## 8080端口
java web中间组件  
tomcat 弱口令 http://xxx.xxx.xxx.xxx:8080/manager/html 部署war包  
GlassFish  
1.弱口令  
2.任意文件读取  
3.认证绕过  
Resin  
1.目录遍历  
2.远程文件读取  
http://xxx.xxx.xxx.xxx/%20../web-inf/  
http://xxx.xxx.xxx.xxx:8088/resin-doc/resource/tutorial/jndi-appconfig/test?inputFile=/etc/passwd

## 8089端口
jboss 弱口令admin/admin 部署war包 getshell  
http://xxx.xxx.xxx.xxx/jmx-console/  
http://xxx.xxx.xxx.xxx/admin-console/  

## 8649端口
ganglia未授权访问  
通过http协议获取相关监控的xml信息  
nmap扫描脚本  nmap --script ganglia-info --script-args ganglia-info.timeout=60,ganglia-info.bytes=100000 -p <port> <tager>

## 9080 9081 9090端口
Websphere  
1.弱口令（console）  
2.任意文件泄露  
3.java反序列化  
可导致XML配置文件泄露http://xxx.xxx.xxx.xxx/ffp/à?/WEB-INF/modules/struts-config-codingShare.xml  
弱口令http://xxx.xxx.xxx.xxx:9080/ibm/console/secure/logon.do 

## 27017端口
MongoDBB  
弱口令  
未授权访问
