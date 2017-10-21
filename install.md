## solr安装步骤（kelen 2017-10-20）

* 1.1.准备工作

      目前最新版本7
      Java JDK8 下载并安装jdk1.8（solr6.*是基于JDK1.8开发的）
      tomcat8.0 下载并解压tomcat8

  ​

  ###  下载地址：https://mirrors.tuna.tsinghua.edu.cn/apache/lucene/solr/7.1.0/

  2.在jetty服务器下运行

  solr解压之后目录结构如下:
  这里写图片描述

  solr5之后发布版本自带jetty服务器，可以自行启动。方式如下：
  进入DOS窗口，然后切换到solr解压后的bin目录下（我的目录是D:\solr-7.1.0\bin），然后输入solr.cmd start[-p port]即可启动，加上-p可指定端口，默认是8983，solr.cmd stop -p port即可关闭制定端口。运行结果如下：

* #### 这里报错，java7版本过低，重新安装java8，然后改变JAVA_HOME即可，重新打开dos窗口就可以

  输入：http://localhost:8983即可访问

  ##### 初步成功（2017-10-20周五）

  3.在tomcat服务器下运行

  为了加入自己的特性，以及在solr基础之上的应用，solr也可运行在tomcat服务器下，具体配置过程如下：
  1. 将solr-6.2.1\server\solr-webapp下的webapp文件夹拷贝到tomcat\webapps目录下，并将webapp重命名为solr（可以重命名为取任意名称）。
  2. 将solr-6.2.1\server\lib\ext下的所有jar包拷贝到tomcat\webapps\solr\WEB-INF\lib下
     3.在WEB-INF下创建一个classses文件夹，并将solr-6.2.1\server\resources下的log4j.properties配置文件拷贝到classes文件夹下
     4.在tomcat\webapps\solr下创建文件夹solrhome(可任意取名)，将solr-6.2.1\server\solr下的所有内容拷贝到solrhome下面，此时tomcat\webapps\solr和tomcat\webapps\solr\solrhome文件夹目录结构如图
     这里写图片描述

  这里写图片描述

  5.修改tomcat\webapps\solr\WEB-INF\web.xml,找到图示代码进行修改（第40行左右，默认注释掉了）
  这里写图片描述

  6.运行tomcat，访问http://localhost:8080/solr/index.html 即可
  这里写图片描述