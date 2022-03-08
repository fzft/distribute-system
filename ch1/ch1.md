## 为什么要做一个分布式的系统
- 本质上就是一个分布式的
    - 从你的手机发送一条信息到你朋友的手机，业务逻辑本身就是一个分布式的
- 追求更高的可靠性
    - 即使有一个节点坏了, 整个系统也能正常运行
- 追求更好的性能表现
- 解决更大的问题
    - 很大的数据，单机无法处理

## 分布式系统的弊端
- 通讯可能失败
- 程序可能崩溃

### 容错(Fault tolerance)
- 我们希望整个系统能平稳运行，即使在有时部分节点崩溃的情况下

## 分布式系统和网络
node(i) ----- message(m)-------> node(j)
- latency: 
- bandwidth

## RPC
online shop ------ > payment service

processPayment() stub 
---> marshal args ---m1--> unmarshal args ---> processPayment implementation

 unmarshal result <--- m2-- marshal result <----

 RPC call function look the same as a local function call 

 ### In practice
 1. 如果服务在收到请求时挂掉
 2. 如果message丢了
 3. 如果message延迟
 4. 如果其中有一环出问题，重试是不是可靠

 ### RPC 历史
 1. SOAP/XML-RPC: RPC using XML and HTTP
 2. Thrift(facebook 2007)
 3. gRPC(Google 2015)
 4. REST (often with JSON)
 5. Ajax in web browers

### RPC 企业级应用
 1. SOA
 2. microservices

 把一个大的软件应用拆分成若干个服务(服务部署在不同的节点)并通过RPC来进行通信

 不同服务通过不用语言来实现：
 1. 相互性： 数据类型转换
 2. 接口定义语言 (IDL)