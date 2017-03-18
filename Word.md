## 相关概念


Core: 对应 standalone (独立模式)
Collection: :对应于solrCloud（云模式)

注意: 独立模式以 Core 来管理, 云模式以 collection 来管理.

------

facet: 维度，相当于对查询结果的统计
constraints: 约束,维度的子类
breadcrumb: 面包屑, 根据选择, 列出的导航路径（选中列表）

![](/word/facet.png)

-----

### 基本元素

Document:
    - 作为 solr 索引和搜索的 *基本单元*, 包括一个或者多个字段(Field)
    - 类似于数据库里的一条记录
Sechema:
    - 在添加到索引中时需要制定 Sechema, 包括: 字段,字段类型,唯一键
    - 类似于关系数据库的表结构
Field:
    - 构成 Document 的基本单元
    - 对应数据库表中的某一列
FieldType:
    - 每个字段都有一个对应的字段类型
solrConfig:
    - 它定义 Solr 如何处理索引,高亮,搜索等很多请求, 同时还指定了缓存策略
    - 如果把 Sechma 定义为 Solr 的 Model, 那么 SolrConfig 就是 Solr 的 Configuration,
requestHanlder:
    - 请求处理器用于接受 http 请求,处理搜索后, 返回相应的结果.
    




---
