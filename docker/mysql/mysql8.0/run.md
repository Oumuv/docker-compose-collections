### 创建compose并启动

```shell
docker-compose -f docker-compose.yml up -d
```

### 停止/启动

```shell
## 停止
docker-compose -f docker-compose.yml stop
## 启动
docker-compose -f docker-compose.yml start
```

### 停止容器并删除compose
```shell
docker-compose -f docker-compose.yml down
```