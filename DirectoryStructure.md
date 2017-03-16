# 目录结构

## solr 二进制包目录结构

build ：在solr 构建过程中放置已编译文件的目录。
client ：包含了一些特定语言调用Solr 的API 客户端程序，目前只有Ruby 可供选择，Java 客户端叫SolrJ 在src/solrj 中可以找到。
dist ：存放Solr 构建完成的JAR 文件、WAR 文件和Solr 依赖的JAR 文件。
example ：是一个安装好的Jetty 中间件，其中包括一些样本数据和Solr 的配置信息。
example/etc ：Jetty 的配置文件。
example/multicore ：当安装Slor multicore 时，用来放置多个Solr 主目录。
example/solr ：默认安装时一个Solr 的主目录。
example/webapps ：Solr 的WAR 文件部署在这里。
src ：Solr 相关源码。
src/java ：Slor 的Java 源码。
src/scripts ：一些在大型产品发布时一些有用的Unix bash shell 脚本。
src/solrj ：Solr 的Java 客户端。
src/test ：Solr 的测试源码和测试文件。
src/webapp ：Solr web 管理界面。管理界面的Jsp 文件都放在web/admin/ 下面，可以根据你的需要修改这些文件。
