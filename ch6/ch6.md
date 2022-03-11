## 一致性

#### 如果主节点崩了这么办
1. Manual failover: 人工的去选择一个新的leader节点，配置每一个子节点使用新的leader节点

#### 一致性算法 解决的是Fail stop 模型问题
1. Paxos: 
2. Raft

#### leader elecetion
Paxos, raft 通过主节点对信息进行排序
1. 通过 failure detector 来确认主节点是否down掉
2. 当检测到主节点当掉后，选举一个新的主节点
3. 防止同时存在两个主节点(脑裂- split-brain)
4. 定义一个term(届)每次选举，term + 1
5. 每个节点在每个term中只能投一次票
6. 需要一个quorum来进行选举

#### RAFT 算法
演示 http://thesecretlivesofdata.com/raft/

#### Paxos 