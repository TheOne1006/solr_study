# solr 学习

## 下载 二进制 安装包


> 1.下载对应版本, 如:

```bash
wget http://mirror.bit.edu.cn/apache/lucene/solr/6.4.2/solr-6.4.2.tgz
```

> 2. 解压

```bash
tar zxf solr-x.y.z.tgz
```

## 基本操作
> 1. 启动

```bash
$cd solr
$bin/solr start
Waiting up to 180 seconds to see Solr running on port 8983 [|]
Started Solr server on port 8983 (pid=48690). Happy searching!
```

> 2. 查看 ui 界面

```bash
$open localhost:8983
```

> 3. 停止

```bash
$ bin/solr stop
```

## 启动示例
solr