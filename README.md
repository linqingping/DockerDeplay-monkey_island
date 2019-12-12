Infection Monkey是一个开放源代码安全工具，用于测试数据中心对外围漏洞和内部服务器感染的恢复能力。Monkey使用各种方法在整个数据中心进行自我传播，并向集中的Monkey Island服务器报告成功情况。
![image](https://github.com/linqingping/DockerDeplay-monkey_island/blob/master/images/map-full.png)
![image](https://github.com/linqingping/DockerDeplay-monkey_island/blob/master/images/Security-overview.png)

Infection Monkey由两部分组成：
1.猴子-感染其他机器并传播到其他机器的工具
2.Monkey Island-专用服务器，用于控制和可视化感染猴子在数据中心内部的进度
要了解有关猴子的更多信息，请访问http://infectionmonkey.com
# 以下内容将介绍如何用docker部署monkey_island服务器
```
https://www.guardicore.com/infectionmonkey/index.html
fill out the form to receive an email with a link to the Infection Monkey package/image  choose docker
官方地址填写邮箱在收到的邮件中选择Docker的连接会下载 dk.monkeyisland.latest.tar
```
```
项目资源相关镜像包已经同步到百度网盘也可以从百度网盘直接导入docker镜像包
链接:https://pan.baidu.com/s/1g9tTCq4Uho1pPbUoWUw7Uw 提取码:f1c5
```
## step：
```
sudo docker load -i dk.monkeyisland.latest.tar
sudo docker load -i mongo.tar 
sudo mkdir -p /var/monkey-mongo/data/db
sudo docker run --name monkey-mongo --network=host -v /var/monkey-mongo/data/db:/data/db -d mongo
sudo docker run --name monkey-island --network=host -d guardicore/monkey-island:1.7.0
```
