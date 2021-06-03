---
Dip: 1
Title: Consensus mechanism
Author: Tailor <tailor@ddn.net>
Type: Core
Status: Draft
Created: 2021-05-11

---

# 概述
本文讨论了共识机制算法的核心矛盾--收益分配，并通过一个公式描述，以及各类算法解决这一矛盾的共同点，并提供一个具体解决方案。

# 摘要
共识机制主要解决的几个问题是
1. 收益分配
2. 分布式
3. 网络容错

本文重点是收益分配讨论

# 共识算法
共识机制的核心点是铸块（收益）权的分配，可以通过一个公式来描述这种分配方式：*R = NPf(x)*。这里*R*节点获得铸块权的调整概率，*N*是节点数，*P*是为调节分配定义的权重，*f(x)*是一个函数，该函数通过某种算法计算出来的一个随机数。*R*的值最接近某个节点编号，则该节点获得铸块权。

1. POW机制
POW机制中，*f(x)*是个数学难题，*P*是算力，由于*f(x)*的结果总是相同，P越大获得铸块权的机会越大。当两个节点概率相等（或接近）时，就会导致分叉。因而POW机制按算力分配收益。
2. POS机制，POS与POW的主要不同是，POS中*P*是币龄，及持有币的多少和时间，因而POS机制按股本分配收益。

3. DPOS机制，DPOS与POS一样，只是参与分配的节点被限制在受托人范围内。

这三种机制都有其优势和缺点，但都与分布式、普惠的经济理念有违背，普通用户的权益被剥脱或削弱了，因而降低了普通用户参与的意愿。

最理想的共识分配算法应当是公平的，*P* = 1。*f(x)*每次计算的结果是随机的，活跃节点都能获得收益权。

要想f(x)的结果足够公平，我们应该回归的问题本身上来，即获取一个完美的随机函数，其每次的计算结果不受可控条件影响。
以下提供几个思路。

## 仲裁和轮询
铸块权的竞争，与程序中的多线程问题极为相似。我们可以想象，每个节点相当于一个线程。每个线程共用一份内存数据。平时他们都无法修改这个内存，在使用时只是读取线程内的备份。在铸块时所有线程竞争这块内存的使用权。由于所有线程的优先级都相同，可以设计一个仲裁程序，由其决定哪个节点获得铸块权。这可能是简单的轮询或者其他复杂算法。这个仲裁程序就是共识机制，算法就是*f(x)*函数。为获得这个随机函数，我们可以在数学和现实世界中类比，寻找可能的算法。

## 元宇宙
近期元宇宙的概念获得比较大的关注，沙盒游戏获得一定成功。

元宇宙指与现实时间对应的数字世界。借助元宇宙的概念，我可以做一些很有意思的思考。假设有个虚拟世界与现实世界类似，区块链节点是虚拟空间中的有限个初始坐标点。每打包一个区块，相当于在虚拟世界创造一个实物，我们可以想象，这个被创造的物体出现的位置，与哪个节点的坐标点距离最近，则收益权归宿哪个节点。区块在元宇宙中出现的位置是随机的，那么所有节点获取收益的机会在概率上均等。
假设存在这样一个随机函数，我们可以在之上施加影响，使其结果偏向我们希望的结果。比如POW机制，我可以假设每个节点具有质量，质量越大，引力越大，越能容易的捕获到收益权，每个节点的质量就相当于前面公式中提到的*P*。在POS机制中，每个节点的质量是币龄等等。

实际上随机函数*f(x)* 可以包含很多的维度参数，只要该函数在至少其中一个维度上是完全随机的，就能满足要求。
再次假设这些节点在空间中分布在一个圆上，每打包一个块其收益是*k*，*r*是半径，*x*是新块在该圆的弧度，这个函数可以表示成*f(kx)*，*k*指两个相邻区块的距离。如果像比特币那样是等比序列，且比例系数小于1，那么新的块总是向圆心逼近，如果，*k*的等比系数大于1，新块在概率上总是远离圆心，通胀还是通缩在空间上得到很具体的描述。

## 结论
在收益分配算法上，最重要是一个随机函数。比特币、以太坊这些典型实现，都是通过上一个块的hash值作为这个随机函数的基础。目前这一手段基本是最佳实践。在此基础上进行调整、修正，就可以对结果施加影响。

# 拜占庭容错

# 分叉
...
# 双花
...
# 参考实现
简单实现 

```
const id = lastBlock.id
const pos = getPos(id)

function getPos(hash) {
  let N = 1

  .... // 上一个节点的hash值，转换成数字，对节点数取模

  return N
}


```

# 参考

- [比特币白皮书](https://github.com/)
- [以太坊白皮书](https://github.com/ethereum)