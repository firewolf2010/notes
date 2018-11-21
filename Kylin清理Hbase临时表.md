## Kylin清理Hbase临时表

&emsp;***Kylin 2.3.0 在创建cube过程中会在HDFS上生成中间数据。另外，当我们对cube执行purge/drop/merge时，一些HBase的表可能会保留在HBase中，而这些表不再被查询，尽管Kylin会做一些自动的垃圾回收，但是它可能不会覆盖所有方面，所以需要我们能够每隔一段时间做一些离线存储的清理工作。具体步骤如下：***

---

1. 检查

   ```shell
   ${KYLIN_HOME}/bin/kylin.sh org.apache.kylin.storage.hbase.util.StorageCleanupJob --delete false
   ```

2. 删除

   ```shell
   ${KYLIN_HOME}/bin/kylin.sh org.apache.kylin.storage.hbase.util.StorageCleanupJob --delete true
   ```

