### 点击增加节点，选择相应版本的【节点安装包】，确定

<img src="http://img.threatbook.cn/hfish/20210616171500.png" alt="image-20210616171459269" style="zoom:50%;" />

```wiki
- 如果您在上面的操作中，选择的是linux安装包，在【确定】后，会出现如下页面，您可以用两种方式让您的节点主机完成部署。
1. 一句话脚本，直接在节点主机上运行
2. 下载可执行文件，并把这个文件上传到节点主机上运行

- 如果您在上面的操作中，选择的windows安装包，在【确定】后，只有一种方式供您选择。
1. 下载可执行文件，并把这个文件上传到节点主机上运行
```

<img src="http://img.threatbook.cn/hfish/20210616172029.png" alt="image-20210616172027825" style="zoom:50%;" />



### 节点关机自启动配置

#### Linux：

进入client的安装目录，执行：

```
sh <(curl -sSL https://hfish.io/autorun.sh)
```



#### Windows：

- 下载压缩包https://hfish.io/autorun.zip 
- 把autorun.bat和cron.xml解压，移到到client文件目录中
- 执行au- torun.bat即可。



### 为节点选择服务模板

> 展开蜜罐节点，选择上面创建的蜜罐模板

<img src="http://img.threatbook.cn/hfish/20210616173018.png" alt="image-20210616173015062" style="zoom:50%;" />



> 刚变更模板后的蜜罐服务状态为【启用】

<img src="http://img.threatbook.cn/hfish/20210616173055.png" alt="image-20210616173053947" style="zoom:50%;" />



> 节点正常完成模板加载后，服务状态应该为【在线】。如果是【离线】，说明蜜罐服务没有正常启动，请参考我们后面的【排错说明】，找到问题。

<img src="http://img.threatbook.cn/hfish/20210616173129.png" alt="image-20210616173128526" style="zoom:50%;" />



### 主机失陷检测

失陷蜜饵是部署在业务主机上的失陷检测蜜饵。在主机失陷情况下，通过部署虚假的账号、本地证书等失陷蜜饵，诱导攻击者转移攻击目标，并触发失陷告警。

其中，主机蜜饵是一种基于部署虚假的账号密码配置文件，诱导转移攻击者攻击目标的防御手段。

命令在主机运行后，会在本地生成一份虚假的“账号密码备份文件”。 当该主机被攻陷时，攻击者将被诱导，使用文件中的账号信息进行登录。借此，安全人员发现主机失陷情况。

<img src="https://hfish.cn-bj.ufileos.com/images/image-20210506162347469.png" alt="image-20210506162347469" style="zoom:50%;" />



![image-20210506162447618](https://hfish.cn-bj.ufileos.com/images/image-20210506162447618.png)



### 删除节点

如果您进行节点删除，那么

- 节点端进程会自动退出，但程序会保留在原有路径，需要手动二次删除。
- 所有攻击数据不会丢失，仍然能在所有数据中进行查看
