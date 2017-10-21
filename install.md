## solr安装步骤（kelen 2017-10-20 周六）

* 1.1.准备工作

      目前最新版本7
      Java JDK8 下载并安装jdk1.8（solr6.*是基于JDK1.8开发的）
      tomcat8.0 下载并解压tomcat8

  ​

  ###  下载地址：https://mirrors.tuna.tsinghua.edu.cn/apache/lucene/solr/7.1.0/*

  ###  2.在jetty服务器下运行

  solr解压之后目录结构如下:
  这里写图片描述

  solr5之后发布版本自带jetty服务器，可以自行启动。方式如下：
  进入DOS窗口，然后切换到solr解压后的bin目录下（我的目录是D:\solr-7.1.0\bin），然后输入solr.cmd start[-p port]即可启动，加上-p可指定端口，默认是8983，solr.cmd stop -p port即可关闭制定端口。运行结果如下：

* #### 这里报错，java7版本过低，重新安装java8，然后改变JAVA_HOME即可，重新打开dos窗口就可以

  输入：http://localhost:8983即可访问

  ##### 初步成功（2017-10-20周五）

  * 3.在tomcat服务器下运行（最终实现的）

  参考博客：http://blog.csdn.net/kaiwen666/article/details/78068837

  4.运行tomcat，访问http://localhost:8080/solr/index.html 即可
  这里写图片描述

* 5.在后台点击Core Admin菜单，如果没有Core，会弹出如下框，提示添加new_core。

* 6.点击documents，增加json类型的数据

* 7.实现浏览器的搜索

* 8.java进行Demo，add和update