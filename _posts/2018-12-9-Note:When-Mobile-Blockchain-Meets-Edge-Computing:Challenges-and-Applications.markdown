---
title: "When Mobile Blockchain Meets Edge Computing:Challenges and Applications"
data: 2018-12-9
tags: "Notes"
---
# When Mobile Blockchain Meets Edge Computing:Challenges and Applications

> Note of When Mobile Blockchain Meets Edge Computing: Challenges and Applications

#### Abstract:

> Blockchain, as the backbone technology of the current popular Bitcoin digital currency, has become a promising decentralized approach for resource and transaction management. Although blockchain has been widely adopted in many applications, e.g., finance, healthcare, and logistics, its application in mobile environments is still limited.

1. Blockchain users need to solve preset proof-of-work puzzles to add new transactions to the blockchain.

2.  Solving the proof-of-work, consumes substantial resources in terms of CPU time and energy, which is not suitable for **resource-limited** mobile devices.

3. Introduce a **novel** concept of edge computing for mobile blockchain.

4. Demonstrative prototype of mobile edge computing enable blockchain systems.

#### Introduction

1. 区块链是一种分散的公开分类账本，可以用来储存用户和企业的交易记录。

2. 集中的方法存在事物处理效率低，故障和攻击点单一的问题，以及集中管理机构的道德风险等问题。

3. 在区块链中，用户事物被记录成块，这些块以链表的形式相互链接，没有中央实体来储存事物数据。

4. 区块链已经被应用与多个分布式系统和多接入网应用场景, e.g., content delivery networks, cognitive radio and smart grid systems.

5. 在挖矿的过程中, 矿工需要解决PoW问题, 但是移动系统资源有限，所以不能广泛地使用, 在以后的IoT中，区块链的部署面临巨大的挑战。

6. Mobile edge computing(MEC) 是一种利用一份环境中可计算能力的体系结构。在边缘计算中，边缘计算服务提供商在“边缘”(基站，无线网的接入点)部署本地数据中心和服务器。

7. 本地计算服务无需连到远程云和服务中心，延迟时间和回城带宽大大减少。

#### Blockchain Overview

1. Each node in the chain is a data block that contains **historical**, **verified transactions**, **information **and **control data**。块链被复制并传播给区块链网络中的所有参与者，这样的块链中包含的数据是全局同步的。

2. 区块链保证了许多用户的认可和考虑，采用加密技术防止恶意中间人更改，篡改或删除记录。consensus is a mechanism to ensure trust in the network. As such, the majority of users can veto" to discard the false transaction.

3. **Byzantine attack **and **Sybil attack**, where an attacker creates mixed information (i.e., fake blockchain) and pseudonymous users in the network. Malicious users need to control over **51%** of all the computing po wer in the network to mislead the network
to accept a false block.

#### Mobile Edge Computing For Blockchain

1. 区块链已经在各种网络和分布式系统中得到了广泛的使用，一个典型的场景就是IoT. 物联网设备能自主地交换信息和资源，其交易过程和回报是formalized 的。

2. Interactions among edge computing service providers and IoT devices or IoT users1 can be modeled as market activities。已经有云服务商提供挖矿业务，但是在边缘计算系统中还没的到很好的研究。

3. 应用场景：Crowdsourcing, Smart Grid.

4. 分布式拒绝服务（DDOS） 很容易在移动物联网中发起，因为他们的保护程度较低。由于移动物联网设备依赖无线传播，干扰攻击可以破坏区块链数据交换。

5. 由于物联网系统中单个个体的计算能力低。只有少数串通或妥协的服务器才能造成51%攻击。

#### DEMONSTRATION SYSTEMS OF MOBILE EDGE COMPUTING ENABLED BLOCKCHAIN
>在本节实现了一个移动边缘计算赋能的区块链系统，并进行实验。

1. 旷工使用andrioid设备通过网络集线器连接到边缘节点，然后从边缘节点请求服务， 然后在以太坊网络挖矿。

2. 通过控制变量法，验证了当边缘计算服务需求增加时，旷工采矿成功的概率增加。

#### MOBILE EDGE COMPUTING RESOURCE MANAGEMENT IN BLOCKCHAIN
>在本节给出了移动区块链的边缘计算系统模型。和普通的挖矿差不多，成本来自边缘计算资源提供商。Present a two-stage Stackelberg game formulation and equilibrium analysis. 主要就是讨论如何使服务商，矿工的利益达到最大化。

1. 供应商和矿工之间的交互可以建模为两阶段的Srackelberg博弈。Leader 在第一阶段确定每一个计算单元的服务价格，the followers, 在知道提供者设定的价格的情况下，决定他们在较低的第二剪- 短执行采矿任务的最佳计算服务需求。
    1. Sub-game: 供应商在第一阶段的定价策略：向矿工收取边缘计算服务减去服务成本，获得的收入。服务成本取决于服务需求。
    2. Solving game Equilibrium: Stackelberg均衡是在追随者采用他们的最佳反应，即在他们的子博弈中的纳什均衡的情况下，leader的收益最大化的一个点。

### 感想

- 区块链是一个去中心化的系统。在许多无信用化场景得到了广泛的应用，如果说在未来的场景中，小规模，低信息容量的区块链记录网络将越来越多地出现在我们的日常生活中。这时候mobile-blockchain将越来越重要——全球有数以亿计的移动设备，这是一个很庞大的计算资源，但是目前他们空闲的资源并不能被充分地利用。

- 服务提供商与旷工都希望自身实现利益的最大化，在本文中，作者利用stackelberg博弈，根据服务商和矿工的策略来选择各自的策略以保证自己的利益最大化，以达到纳什均衡。

- IoT是目前热门的研究领域，在不久的将来，也会有更多的，计算能力更强大的IoT设备的出现，如果移动区块链能与IoT一同成长，有可能会重新定义互联网时代中**trust**。而且在5G技术的带动下，移动设备之间的通信速度更快，单位时间内传播的信息更多，这将会极大促进移动区块链的发展。

- 目前的移动区块链还处于萌芽的阶段，大部分的概念都是从传统区块链上继承而来。但是很多情况下两种区块链网络其实还是有区别的。如果未来移动区块链网络想要有更大的发展，必须想出更好的算法来解决安全，性能等问题。也就是说，移动区块链需要找到适合它自己的模式。

### 改进

- 在服务商和矿工的交易中，本文通过服务商先给计算资源定价，然后与矿工进行Stackelberg博弈来是他们各自觉得自己的利益最大化。但是这其实让交易价格有了一个天花板，这并不能很好地激励矿工的出价。

- 本文中的移动区块链是十分脆弱的，容易受到DDOS攻击和51%攻击等区块链常见的攻击，问题出现在海量的移动设备资源与弱小的计算能力，但是当我们组建起一个相当庞大的移动区块链集团时，这些问题会得到缓解。就是我们可以讲不同作用的链整合起来，如此一来，单个区块链就不会像以前一样脆弱。

- 本文的实验是在eth公链上实现的，可能这是论文发表时间的局限，但是到了现在，乃至将来，eth的链上交易的gas消耗太过庞大。我们如果要复现这个实验，可以使用EOS等消耗更小的公链。

- 本文并没有考虑区块大小对整个移动区块链网络的影响（本文默认为eth的块大小），在区块的容量减小时（矿公的收益同时也会降低），通过比较传统区块链和移动区块链的性能，收益，来比较两种区块链各自的优势。
