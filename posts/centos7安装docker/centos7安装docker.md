

**1.查看当前的内核版本**

```
uname -r
```
**2.使用 root 权限更新 yum 包**
```
yum -y update
```
**3.卸载旧版本（如果之前安装过的话）**
```
yum remove docker  docker-common docker-selinux docker-engine
```
**4.安装需要的软件包， yum-util 提供yum-config-manager功能，另两个是       devicemapper驱动依赖**
```
yum install -y yum-utils device-mapper-persistent-data lvm2
```
**5.设置 yum 源**
设置一个yum源，下面两个都可用
```
yum-config-manager --add-repo http://download.docker.com/linux/centos/docker-ce.repo（中央仓库）

yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo（阿里仓库）
```
**6.选择docker版本并安装**
（1）查看可用版本有哪些
```
yum list docker-ce --showduplicates | sort -r
```
（2）选择一个版本并安装：yum install docker-ce-版本号
```
yum -y install docker-ce-xxx
```
**7.启动 Docker 并设置开机自启**
```
systemctl start docker
systemctl enable docker
```