## 与上游对比，更新内容

1. 支持最多10级文档树

## docker部署教程

1. clone源码到宿主机目录

```
cd /docker-volume/mrdoc
git clone https://github.com/lazzman/MrDoc.git volume
```

2. compose部署

```
services:

  mrdoc:
    # https://doc.mrdoc.pro/doc/3958/
    # https://hub.docker.com/r/zmister/mrdoc
    # 更新版本：在宿主机映射目录 执行 git fetch --all && git reset --hard origin/master && git pull ，然后重启docker服务
    image: zmister/mrdoc:v9.3
    restart: always
    ports:
      - 10086:10086
    volumes:
      - /docker-volume/mrdoc/volume:/app/MrDoc
```

3. 更新

在宿主机映射目录，执行`git fetch --all && git reset --hard origin/master && git pull`，然后重启docker服务