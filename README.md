**消息中间件在后台系统中是必不可少的一个组件，一般我们会在以下场景中使用消息中间件：**

**异步处理：异步处理是使用消息中间件的一个主要原因，在工作中最常见的异步场景有用户注册成功后需要发送注册成功邮件、缓存过期时先返回老的数据，然后异步更新缓存、异步写日志等等；通过异步处理，可以减少主流程的等待响应时间，让非主流程或者非重要业务通过消息中间件做集中的异步处理。**

**系统解耦：比如在电商系统中，当用户成功支付完成订单后，需要将支付结果给通知ERP系统、发票系统、WMS、推荐系统、搜索系统、风控系统等进行业务处理；这些业务处理不需要实时处理、不需要强一致，只需要最终一致性即可，因此可以通过消息中间件进行系统解耦。通过这种系统解耦还可以应对未来不明确的系统需求。**

**削峰填谷：当系统遇到大流量时，监控图上会看到一个一个的山峰样的流量图，通过使用消息中间件将大流量的请求放入队列，通过消费者程序将队列中的处理请求慢慢消化，达到消峰填谷的效果。最典型的场景是秒杀系统，在电商的秒杀系统中下单服务往往会是系统的瓶颈，因为下单需要对库存等做数据库操作，需要保证强一致性，此时使用消息中间件进行下单排队和流控，让下单服务慢慢把队列中的单处理完，保护下单服务，以达到削峰填谷的作用。**

<a href="https://ibb.co/GWFxZQH"><img src="https://i.ibb.co/jyH6CkJ/image.webp" alt="image" border="0"></a>


# [Message-Server-System 面试](https://github.com/stevenli91748/Message-Server-System/blob/master/Interview/README.md)


# 目录
[消息队列对比参照表](https://www.kancloud.cn/zlt2000/microservices-platform/1023348)|[MQ 消息丢失、重复、积压问题，如何解决](https://mp.weixin.qq.com/s/vjlirhG7o2olGS4r6cn2ZQ)|
---|---|

[什么是消息队列？](https://juejin.im/post/6844903817348136968)|[云原生时代消息中间件的演进路线](https://www.kubernetes.org.cn/8305.html)|[MQ 主流的MQ的对比与业务选型](https://www.jianshu.com/p/0b1d1fe84e70)|
---|---|---|

[ELK-实践（架构选择&部署说明）](https://www.jianshu.com/p/2193d3cf7e2b)|[对 Kafka 和 Pulsar 进行性能测试后，拉卡拉将消息平台统一换成了 Pulsar](https://www.jianshu.com/p/5cd80bb3d401)|
---|---|

[ Pulsar出现,再见RocketMQ！全新一代消息中间件，带可视化管理，文档贼全](https://www.jianshu.com/p/6d6fcfff43f0)|
---|

# 目录

* [ActiveMQ](https://github.com/stevenli91748/Message-Server-System/blob/master/ActiveMQ/README.md)
* [RabbitMQ](https://github.com/stevenli91748/Message-Server-System/blob/master/RabbitMQ/README.md)
* [ZeroMQ](https://github.com/stevenli91748/Message-Server-System/blob/master/ZeroMQ/README.md)
* [MetaMQ](https://github.com/stevenli91748/Message-Server-System/blob/master/MetaMQ/README.md)
* [RocketMQ](https://github.com/stevenli91748/Message-Server-System/blob/master/RocketMQ/README.md)
* [Kafka](https://github.com/stevenli91748/Message-Server-System/blob/master/Kafka/README.md)
* [Pulsar---用于服务端到服务端的消息中间件]()

# MQ视频

 * [MQ落地化设计之12306购票业务细节分析与实战](https://www.bilibili.com/video/av58897341)
 * [MQ落地化设计之美团App购票业务细节分析与实战](https://www.bilibili.com/video/av60261628)
 * [70万年薪高并发架构技术RabbitMq美团App购票实战精讲版](https://www.bilibili.com/video/av60861746)

# 有用的参考
* [别在简历写秒杀系统了！我告诉你消息管理平台实现原理吧](https://zhuanlan.zhihu.com/p/258732579)
* [消息中间件这么多，到底应该如何选型？](https://www.360kuai.com/pc/detail?url=http%3A%2F%2Fzm.news.so.com%2F4803fc734844e96d0f7b4f5ae061ec20&check=f7af8422c57e78b6&sign=360_8910f42c&uid=g1573983271791375009)

* [消息队列常见的几种使用场景介绍](https://mp.weixin.qq.com/s/JTFiiCk0yd6XCSawz0WXBw)
* [消息中间件如何选型？](https://mp.weixin.qq.com/s/mM0jSKv-dQpGzzEC0b9l4w)
* [RabbitMQ 和 Kafka 到底怎么选？](https://mp.weixin.qq.com/s/mM0jSKv-dQpGzzEC0b9l4w)
* [MQ消息可达性+幂等性+延时性架构设计](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651960382&idx=1&sn=72dae005c6662a936ea8fa80a4ed6001&chksm=bd2d01e28a5a88f400451195d2521ca668161364e3e62a9a42992299ce6baa5cbafa353d23d3&scene=21#wechat_redirect)
* [高并发场景下，如何保证生产者投递到消息中间件的消息不丢失？](https://mp.weixin.qq.com/s/r2_o5wa6Gn94NY4ViRnjpA)
* [面试大杀器：消息中间件如何实现消费吞吐量的百倍优化？](https://mp.weixin.qq.com/s/vZ4KVC2eGmssnQUyIKgzfw)

* [Java进阶面试系列之一：哥们，你们的系统架构中为什么要引入消息中间件](https://juejin.im/post/5c0fbaf8f265da616f6fd0c3)
* [哥们，那你说说系统架构引入消息中间件有什么缺点](https://juejin.im/post/5c1214a66fb9a049bb7c3410)
* [哥们，消息中间件在你们项目里是如何落地的](https://juejin.im/post/5c17a521f265da611f079bb6)
* [消息中间件集群崩溃，如何保证百万生产数据不丢失](https://juejin.im/post/5c1e51fd6fb9a049a81f4f35)
* [消息中间件如何实现消费吞吐量的百倍优化？](https://juejin.im/post/5c3b392e518825255d296f78)
* [高并发场景下，如何保证生产者投递到消息中间件的消息不丢失](https://juejin.im/post/5c3c9fb3f265da61461e625b)
* [如何保证消息中间件全链路数据100%不丢失（1）](https://juejin.im/post/5c3604abe51d45522a41f4b0)
* [如何保证消息中间件全链路数据100%不丢失（2）](https://juejin.im/post/5c3759fe51882525616dbaf6)
* [从团队自研的百万并发中间件系统的内核设计看Java并发性能优化](https://juejin.im/post/5c3f708151882524b333b67f)
* [MQ消息可达性+幂等性+延时性架构设计](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651960382&idx=1&sn=72dae005c6662a936ea8fa80a4ed6001&chksm=bd2d01e28a5a88f400451195d2521ca668161364e3e62a9a42992299ce6baa5cbafa353d23d3&scene=21#wechat_redirect)
* [如何保证消息不被重复消费？（如何保证消息消费时的幂等性）](https://www.javazhiyin.com/22910.html)
* [如何保证消息的可靠性传输？（如何处理消息丢失的问题）](https://www.javazhiyin.com/22914.html)

