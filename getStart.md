# 快速开始

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

## 启动一个示例

Solr还提供了一些有用的示例，以帮助您了解主要功能。
您可以使用-e标志启动示例。
例如，要启动“techproducts”示例

```
$ bin/solr -e techproducts
Creating Solr home directory /Users/theone/theone/solr/software/solr/example/techproducts/solr

Starting up Solr on port 8983 using command:
bin/solr start -p 8983 -s 'example/techproducts/solr'

...

{
  "responseHeader":{
    "status":0,
    "QTime":5956},
  "core":"techproducts"}

Indexing tech product example docs from /Users/theone/theone/solr/software/solr/example/exampledocs
SimplePostTool version 5.0.0
Posting files to [base] url http://localhost:8983/solr/techproducts/update using content-type application/xml...
POSTing file gb18030-example.xml to [base]

...

Solr techproducts example launched successfully. Direct your Web browser to http://localhost:8983/solr to visit the Solr Admin UI
```


## 检测状态
如果你想确认 solr 是否在运行.

```
$ bin/solr status

Found 1 Solr nodes:

Solr process 54691 running on port 8983
{
  "solr_home":"/Users/theone/theone/solr/software/solr/example/techproducts/solr",
  "version":"6.4.2 34a975ca3d4bd7fa121340e5bcbf165929e0542f - ishan - 2017-03-01 23:30:23",
  "startTime":"2017-03-16T13:27:33.288Z",
  "uptime":"0 days, 0 hours, 8 minutes, 50 seconds",
  "memory":"49.8 MB (%10.1) of 490.7 MB"}
```

## 创建一个 Core

如果你没有启动一个示例, 你需要创建一个 core, 为了能够索引和搜索.

```bash
$ bin/solr create -c <name>
```
这将创建一个核心，它使用数据驱动模式，在向索引中添加文档时尝试猜测正确的字段类型。

查看创建新 core 的所有可用选项

```bash
$ bin/solr create -help
```

## 添加文档

Solr用于查找匹配查询的文档,
Solr的 Schema(模式) 提供了如何结构化内容的概念,
在此之前,需要往里添加文档.

在此之前你可以尝试往里添加一些内容,
在 example 下有一些 案例文档.


`bin/post` 可以添加多种类型的文档.包括 xml, json, csv, 目录, (...).


`bin/post -help` 可以查看 post 帮助

```bash
$ bin/post -c gettingstarted example/exampledocs/*.xml
```

把所有的 `*.xml` 数据导入到 gettingstarted

### Ask Question

现在您已建立索引文档，您可以执行查询,
最简单的方法是构建一个包含查询参数的URL,
这结构与任何其他HTTP网址完全相同

例如, 以下实例是查询所有文档的领域中查询 'video'

```
http://localhost:8983/solr/gettingstarted/select?q=video
```

一旦掌握了查询的基本概念，就可以很容易地添加增强功能来探索查询语法。
这一个和以前一样，但每个返回结果只包含 ID, name, and price
如果不指定所需的字段，则返回所有字段

```
/select?q=video&fl=id,name,price
```
另一个例子只在`name` 字段中搜索 'black'.

```
/select?q=name:black
```

您可以提供字段的范围。以下查询查找价格介于$ 0和$ 400之间的每个文档

```
/select?q=price:[0%20TO%20400]&fl=id,name,price
```

分面浏览 是solr 关键的特征, 它允许用户以对您的应用程序有意义的方式缩小搜索结果范围.

## 快速描述

你可以通过solr 做一些有趣的事情,

![](getetingStarted/sample-client-app-arch.png)























- - -
