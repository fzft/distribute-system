## Replication
- 在众多节点中保存一份相同的备份
- 应用场景: 数据库，文件系统，缓存。。。
- 一个节点保存有一份数据的就被叫做replica
- 如果某些replicas故障了或者需要重启等操作，还是能通过其他正常节点来访问数据
- 单节点无法满足多用户的需求，多节点加快高并发下的访问速度
- 对于不太变化的数据处理比较简单, 复制就行
- 重点关注那些经常变化的数据