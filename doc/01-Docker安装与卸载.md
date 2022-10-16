### Docker安装

> 可参考 https://docs.docker.com/engine/install/centos
>
> tips: 基于 CentOS Linux release 7.6.1810 (Core)

```shell
# 卸载已存在旧的docker
sudo yum remove docker docker-client docker-client-latest docker-common docker-latest docker-latest-logrotate docker-logrotate docker-selinux docker-engine-selinux docker-engine

# 配置yum源
sudo yum install -y yum-utils device-mapper-persistent-data
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

# 通过yum源安装docker
# sudo yum -y install docker
# 指定版本安装
sudo yum install -y docker-ce-20.10.7 docker-ce-cli-20.10.7 containerd.io-1.4.6

# 启动docker
sudo systemctl start docker
# 重启docker
sudo systemctl restart docker
# 开机自启
sudo systemctl enable docker
# 设置开机自启 & 现在启动
sudo systemctl enable --now docker

# 查看运行情况
sudo systemctl status docker

# 测试
docker run --rm alpine ping -c 5 baidu.com
```

### Docker卸载

```shell
# 查看yum安装的docker软件包
yum list installed |grep docker
# 删除相关软件包
yum -y remove docker* containerd.io
# 删除关联数据
rm -rf /var/lib/docker
rm -rf /var/lib/containerd
```

### 配置镜像加速器

```shell
# 修改daemon配置文件`/etc/docker/daemon.json`
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https//registry.docker-cn.com","https://docker.mirrors.ustc.edu.cn","https://hub-mirror.c.163.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
# 查看 `Registry Mirrors`
docker info
```
