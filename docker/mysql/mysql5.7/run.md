### 创建compose并启动

```shell
docker-compose -f docker-compose.yml -p mysql5.7 up -d
```

### 停止/启动

```shell
## 停止
docker-compose -f docker-compose.yml -p mysql5.7 stop
## 启动
docker-compose -f docker-compose.yml -p mysql5.7 start
```

### 停止容器并删除compose
```shell
docker-compose -f docker-compose.yml -p mysql5.7 down
```