# Hbase高效使用注意事项

#### 一、Row Key设计原则

---



#### 二、Region 预分

---



#### 三、Region Split策略

---

#### 四、其他

---

##### 4.1 是否需要关闭自动Major Compaction

---

**Compaction介绍：**

+ Minor Compaction：选取一些小的、相邻的StoreFile将他们合并成一个更大的StoreFile。
+ Major Compaction：所有的StoreFile合并成一个StoreFile。Major Compaction时间会持续比较长，整个过程会消耗大量系统资源，对上层业务有比较大的影响。关闭自动触发Major Compaction功能，改为手动在业务低峰期触发。

**Row Key设计对Compaction的影响:**

+ 周期性活跃的Region：这种现象的Row Key一般由 日期 + ID 组成，Major Compaction的数据量呈现周期性变化。
+ 一直活跃的Region：Row Key散列效果较好，所有Region处于一直活跃的状态，Major Compaction的数据总量一直增大。

**TTL对Compaction的影响：**

&emsp; 数据的TTL直接影响Compaction发生时涉及的最大数据量

&emsp;*思考：*Hbase是否适合做数据的永久保存，hdfs是否是更好的选择

---

*关于Compaction的细节可以单独讲解*

---

##### 4.2 





