
### `docker-compose`安装

```shell
# 安装EPEL软件包
sudo yum -y install epel-release
# 安装pip3
sudo yum install -y python36-pip
# 升级
sudo pip3 install --upgrade pip
# 验证pip3版本
pip3 --version
# docker-compose安装
sudo pip3 install -U docker-compose
# 验证docker-compose版本
docker-compose --version
# 安装补全插件
# curl -L https://raw.githubusercontent.com/docker/compose/1.25.0/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose
```

### `docker-compose`卸载

```shell
pip3 uninstall docker-compose
```
