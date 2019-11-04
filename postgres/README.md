## postgres 10.7 with some extensions:

* zombodb v10-1.0.3
* pipelinedb
* postgis-2.4


## Build

```
docker build -t jie123108/postgres10 ./
```

## 国内build

```bash
# 国内需要使用代理, 否则可能下载失败.
docker build -t jie123108/postgres10 --build-arg PROXY=http://你的代理IP:1087 ./
```