# 大模型应用开发面经 （5年经验）
## 时间范围
近半年

## 实际面过的公司
阿里、腾讯、美团、字节、快手、同程、京东、360、keep、滴滴、印象笔记、作业帮、彩云科技、蓝色光标、江城互娱、Aviagames、Hungry Stdios、深言科技、即时科技、RockFlow、格灵深瞳、百融云创、印象笔记、网龙、 HiDream.ai、昆仑万维、数驱互动、Authing

## 先说总结
### 面试内容 & 难度
- 个人觉得，在llm应用的面试题上，没有太多复杂、高深的问题，不像上来让你说一下分布式锁怎么设计然后死扣设计细节或是描述一下MVCC原理这种偏高难度的八股文问题（当然也遇到了一两次），究其原因以下几点，一是大模型应用目前仍没有很成熟且被广泛接纳的方案，都还在探索；二是很多公司今年刚开始all in AI（我司all进去的比较早点），面试官也懂得不多，例如RAG这个东西，大部分的面试题无非是“你觉得RAG中最难的是什么？（文档切割喽）”、“你是怎么解决幻觉问题的？”，“微调和RAG的区别是啥？”等等，如果你做过RAG加上你经常看技术文章结合你的“侃侃而谈”，基本面试官都觉得ok。但这里着重说一下我觉得当前非常重要且极大概率提升面试通过率的的一个技术点，就是**掌握微调原理并且做过动手做过微调工作再加上动手部署过大模型**，这是我面试中最常被问到而又只能说没做过的问题，当然大部分公司都有专门的算法团队去做这件事，自己到没机会参与其中，也是可以理解的。

- 算法题：一半是DP问题，还有一部分难度是easy的问题，总体上都是“老熟人”，**但是，你即使写出来，面试不一定就能过**，有的干脆就不考算法题。

- 八股文：明显比之前少很多，这个和面试的岗位有关系，LLM应用的岗位更偏实践，所有很多一面就是leader面，直接问项目，除非一面也不懂LLM的东西，就会考八股文，**但总的来说，八股少了，但是绝对不可以不准备，好几次挂在这上面，别小瞧它。**

- 岗位内容：
  - 游戏公司：基本上是LLM + AB test for 游戏策划；BI 分析；游戏社区客服助手；
  - toC: Agent 个人助手
  - toB: Agent for 解决方案
  - other: 通用 Agent 平台；公司内部AI助手、平台；Agent for 运维
    
### offer
- 会有很多横向对比，如果你期望薪资比较高，对方说要在等等，基本上凉了。
- 大部分涨幅基本是不到20%的，但我的期望是30%左右，最后还是拿到了（要有一点点耐心，还要有一定的运气）。
- 不要眼高手低，先拿一个低于自己预期的offer，再慢慢谈，前提是公司想要你。
- 规划好时间，集中面试，集中对比，由于我时间线拉的过长，后面安排的很乱。

### 再总结
- 每次面完都要复盘，没答好的问题，一定要重新梳理答案。
- 没把握问题的可以直接说不会，别给个你自己都听不懂的答案。
- 简历一定要让大模型润色，但自己要check一遍，别吹过头了。
- 多看技术文章，扩展技术视野，提高二面面试官对你的印象。
- 表达一定要流畅清晰，不要断断续续的，面试官会觉得你思路不清晰。
- 项目效果评估是个很重要的问题，不管你的技术多炫酷，终究还是要看效果，看落地效果。

## 面试题
> 这里想到多少写多少

### LLM 基础
- 大模型是怎么训练出来的？
- Transform 的架构，Encoder 和 Decoder 是什么？
- Function Call 是怎么训练的？
- 微调的方案有哪些？自己做过没有？
- 大模型分词器是什么？
- Embedding 是什么？你们用的那个模型？

### Lib
- 介绍一下 langchian
- 介绍一下 autogen
- 有没有用过大模型的网关框架（litellm）
- 为什么手搓agent，而不是用框架？
- mcp 是什么？和Function Call 有什么区别？有没有实践过？
- A2A 了解吗？

### Prompt
- ReAct 是啥？怎么实现的？
- CoT 是啥？为啥效果好呢？有啥缺点？
- Prompt Caching 是什么？
- 温度值/top-p/top-k 分别是什么？各个场景下的最佳设置是什么？

### RAG
- 你介绍一下RAG 是什么？最难的地方是哪？
- 文档切割策略有哪些？怎么规避语义被切割掉的问题？
- 多路召回是什么？
- 文档怎么存的？粒度是多大？用的什么数据库？
- 为啥要用到图数据库？
- 向量数据库的对比有没有做过？Qdrant 性能如何？量级是多大？有没有性能瓶颈？
- 怎么规避大模型的幻觉？
- 微调和RAG的优劣势？
- **怎么量化你的回答效果？** 例如检索的效果、回答的效果。

### Workflow
- 怎么做的任务拆分？**为什么要拆分？** 效果如何？怎么提升效果？
- text2sql 怎么做的？怎么提高准确率？
- 如何润色query，目的是什么？
- code-generation 是什么做的？如何确保准确性？
- 现在再让你设计你会怎么做？（replan）
- **效果是怎么量化的？**

### Agent
- 介绍一下你的 Agent 项目
- 长短期记忆是怎么做的？记忆是怎么存的？粒度是多少？怎么用的？
- Function Call 是什么做的？
- 你最大的难题是什么？你是怎么提高效果的？怎么降低延迟的？
- 端到端延迟如何优化的？
- 介绍一下single-agent、multi-agent的设计方案有哪些？
- 反思机制是什么做的？为什么要用反思？
- 如何看待当下的LLM应用的趋势和方向
- 为什么要用Webrtc？它和ws的区别是什么？
- agent服务高可用、稳健性是怎么保证的？
- llm 服务并发太高了怎么办？

### 系统设计题
- 短链系统
- 分布式锁的设计
- 给你一部长篇小说，怎么做文档切割？
- 怎么做到论文翻译，并且格式尽可能和原来的统一
- 游戏社区客服助手设计。如何绑定游戏黑话，如何利用好公司内部的文档
- 结合线上问题快速定位项目工程代码有问题的地方
- 有很多结构化和非结构化数据，怎么分析，再怎么得出我要的结论。

### 八股
- go的内存分配策略、GMP、GC
- python 的内存分配策略、GC
- redis 用过那些？mget 底层什么实现的？、zset怎么实现的？
- mysql 索引怎么设计最好？数据库隔离级别？mvcc是怎么实现的？
- 分布式锁是什么实现的？
- kafka的 reblance 是什么？会产生那些问题？怎么保证数据不丢?
- fastapi 设计原理？
- go 中 net/http 如何处理的tcp粘包问题
- http2 是什么？比http1.1有什么优势？
- Linux 网络性能调优的方式
- 如何定位Linux中的pid、端口号等等

### 个人
- 在每个项目的里的角色是什么？承担那些工作？项目是几个人在做？
- 为什么离职、每次离职的原因是什么？
- 平常怎么学习的？怎么接触到大模型的最新进展的？
- 对大模型将来的应用发展有什么看法？
- 你将来的职业规划是什么？
