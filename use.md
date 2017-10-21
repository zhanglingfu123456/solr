## solr的使用

* 1.查询

  ```
  http://localhost:8080/solr/new_core/select?q=id:1
  http://localhost:8080/solr/new_core/selectq=*&facet_fields:price&fl=name,price
  聚合查询:http://localhost:8080/solr/new_core/select?q=*&facet=on&facet.field=id&facet.field=price
  ```

* 2.java的Demo，包括add和query都可以
   这个已经实现，具体的测试成功
