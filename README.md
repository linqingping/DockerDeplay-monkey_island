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
