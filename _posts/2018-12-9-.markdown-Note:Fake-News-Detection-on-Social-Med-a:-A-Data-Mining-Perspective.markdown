---
title: "Note:Fake News Detection on Social Media: A Data Mining Perspective"
data: 2018-12-9
tags: "Notes"
---
# Fake News Detection on Social Media: A Data Mining Perspective

> 本文综述了在社交媒体上对虚假新闻的检测，包括心理学和社会理论上的假新闻特征，现有的数据挖掘算法，评价指标和又代表熊的数据集。本文还讨论了相关的研究领域，开放的问题，以及社交媒体假新闻检测未来来的研究方向。

#### Introduction

> 与传统新闻媒体相比，社交媒体上的新闻往往更及时，更便宜。更容易与社交媒体上的其他读者分享，评论和讨论新闻。然而，由于网上提供新闻便宜，通过社交媒体传播更快，因此出现了大量的虚假新闻。这些假新闻的目的多种多样，例如财政和政治利益。

1. 假新闻在Facebook上的比权威主流媒体的新闻更受欢迎。虚假新闻往往有意说服消费者接受有偏见或错误的信念。被宣传人员操纵，来传达政治信息或影响。

2. 假新闻改变了人们对真实新闻的解读和反应方式。例如，一些假新闻只是为了引发人们的不信任，使他们感到困惑，从而阻碍他们区分真实和不真实的能力。

3. 定义什么是fake news。对最先进的fake news检测方法提供一个基本的认识。探讨可以提高fake news检测和缓解的研究方向。
Characterization and Detection。
1.讨论虚假新闻的狭义和广义定义。
2.将现有的假新闻检测方法分为不同类别。
3.给出未来社交媒体假新闻检测的发展方向。

#### Fake News Characterization

> A narrow definition of fake news is news articles that are intentionally and verifiably false and could mislead readers. 

1. 真实性和意图。假新闻包括可以核实的虚假消息，和误导消费者的不诚实意图。因此一下概念不是假新闻:
(1)具有适当预警的讽刺新闻。
(2)不是源于新闻事件的谣言。
(3)阴谋论。
(4)无意制造的虚假信息。
(5)仅出于娱乐或欺骗目标的个人的骗局。

2. 假新闻的心理基础，消费者容易收到假新闻的影响：
1.Naive Realism: 消费者倾向于认为他们对显示的看法是唯一准确的，而其他不同意见的人则是不知情不合理或是有偏见的。
2.Confirmation Bias: 消费者更愿意得到正式他们现有观点的信息。

3. 假新闻的社会基础，**Social identity theory** and **normative influence theory**，对社会接受和肯定的偏好对于一个人的身份和自尊十分重要。
从经济博弈论的角度出发，将新闻生成和消费周期描述为一个两人策略博弈。虚假新闻发生在短期效用支配出版商的整体效用，在心理效用支配消费者的整体效用。所以假新闻能蓬勃发展。

4. 社交网络上的假新闻:
恶意账户：social bots，cyborg users，trolls
Echo Chamber Effect: 社交媒体上的用户往往会形成一群直通道合的人，在那里他们会分化自己的观点，从而产生回声效应：
1.**Social credibility**, 如果其他人认为来源可信，在没有足够的信息证明来源的真实性时，人们更有可能认为来源是可信的。
2.**Frequency heuristic**，消费者自然支持他们常常听见的消息，即使是假新闻。

#### Fake News Detection

> 探讨假新闻检测的定义和提出的方法。

1. Definition 2 (Fake News Detection) Given the social
news engagements E among n users for news article a, the
task of fake news detection is to predict whether the news
article a is a fake news piece or not.

2. News Content Features: Source,Headline,Body Text, Image/VIdeo.
Linguistic-based:(1)lexical features,(2)symtactic features.
Visual-based:通过假新闻的视觉特征。

3. Social Context Features:社会交往是新闻传播的过程，它位腿短新闻文章的准确性提供了有用的辅助信息。
    1. User-based: 个人级别的特征，组级用户的特征。虚假新闻和真是新闻的传播者可以形成不同的群体，具有独特的特征，可以听群体层次的特征来描述。
    2. Post-based: post level, group level, temporal level. Topic features can be extracted using topic models,such as **latent Dirichlet allocation**.Group level就是将相同主题的文章集合在一起，分析他们的平均可信度。Temporal level 考虑post level随时间的变化。可以用Unsupervised embedding methods,such as **RNN**,来捕捉post随时间的变化。
    3. Network-based: 通过在发布相关社交媒体的帖子的用户之间国建特定的网络来提取。The stance network, the co-occurrence network, the friendship network, the diffusion network.  Other approaches learn the latent node embedding features by using SVD or network propagation algorithms .

4. News Context Models: 利用新闻内容特征和现有的事实来源来对假新闻进行分类。
    1. Knowledge-based: Fact-checking 已经引起越来越多的关注，并做出了许多的努力，以开发一个可行的自动化事实核查系统。现有的事实核查方法可分为面向专家的，面向总包的和面向计算的。
    2. Style-based: 基于风格的方法试图通过捕捉新闻内容写作风格中的manipulators来检测假新闻。文体王法分为：以欺骗为导向，以客观为导向。
    
5. Social Context Models: 对用户的社会关系进行分析，从不同的角度捕捉辅助信息。
    1. Stance-based: 利用用户在相关帖子内容中的观点推断原始新闻文章的准确性。
    2. Propagation-based: 根据帖子之间的相互关系进行预测。
    
#### Assessing Detection Efficacy

1. Dataset
    - BuzzFeedNews
    -  LIAR
    -  BS Detector
    -  CREDBANK
    (Table 1 是对数据集的比较)
 
2.  Evaluation Metrics: TP,TN,FN,FP. Note that for Precision, Recall, F1, and Accuracy, the higher the value, the better the performance

#### Related Aeras

> 通过对任务目标的简要说明和一些流行的方法，指出了这些领域与假新闻检测的不同之处。

##### Rumor Classification
- 谣言通常被定义为“在传播时真实性尚未被证实的一条流通信息”，假新闻是之与公共新闻事件有关的，可以被证实为假的信息。

##### Truth Discovery
- Truth Discovery 是指从多个相互冲突的来源中发现真实事实的问题。

##### Clickbait Detection
- 诱导点击是指网络媒体用吸引眼球和挑逗的标题，用来增加文章的阅读量。点击标题创造了一个所谓的“好奇心差距”，增加了读者点击目标链接以满足他们好奇心的可能性。

##### Spammer and Bot Detection
- 垃圾信息检测，旨在捕获而已用户，相互协调，发起各种攻击，如传播广告，传播社情制品，传播病毒和网络钓鱼。我们可以两用这些账户来进行假新闻检测。

#### Open Issues And Future Research

> 社交媒体上的假新闻检测是一个新兴的研究领域，因此本文希望从数据挖掘的角度指出一个很有前途的研究方向，如Fig.2所示：面向数据，面向特性，面向模型，面向应用。

##### Data-oriented

- 面向数据的假新闻研究集中在数据集，时态，心理等不同的数据特征上。建立一个全面的，大规模的假新闻数据集。用数据挖掘的方法来进行假新闻的意图检测。

##### Feature-oriented

- 数据源：新闻内容和社会背景。从新闻内容的角度，引入基于语言和视觉的技术来冲文本信息中提取特征。Embedding techniques。

##### Model-oriented

- 监督学习，半监督学习，无监督学习

##### Application-oriented

- 假新闻传播和假新闻干预。假新闻传播是假新闻在社交媒体上传播的路径和模式。通过主动干预的方法来减少假新闻的传播范围火灾假新闻传播后采取反应干预方法试图删除新闻或删除用户，用真实新闻免疫用户。

### 感想

-  社交媒体的假新闻与传统的假新闻相比，更复杂，影响的因素更多，并且假新闻的影响要比传统的要大得多。本文详尽地综述了社交媒体上的假新闻检测的问题。不仅仅对新闻的文本进行检测，而且从假新闻的传播意图，传播个体，传播方式，传播的心理学基础对社交媒体上的假新闻检测进行分析。

- 社交媒体上的假新闻，有可能事件的本身是真实的，但是处于某种意图曲解了这个事情的意义，从而对人们的心理进行影响，来传达政治信息和影响。根据本文提供的方法，我们可以通过对这个新闻的传播方式进行分析（假新闻会通过大量的机器人账号，被标记的恶意分享者转发，以达到广泛传播的目的）来判断这个是否是假新闻。

- 由于技术手段的升级，在社交网络上的假新闻更容易。恶意的传播者能通过自动生成文章的机器人账号和大量的自动转发账号，来达到快速生成假新闻并广泛传播的意图。这时候如果不对这假新闻的传播进行抑制和干预，后果将不堪设想。当然随着技术的发展，检测假新闻的工具也日益强大，我们可以通过深度学习的方法，对假新闻的文本内容，假新闻的传播方式等进行学习。使得我们检测假新闻能力提高。

### 改进

- 在谈到假新闻的社会基础时，本文提出了一个基于出版商和消费者的博弈。来说明假新闻的传播过程中，假新闻能同时满足出版商和消费者的效用。但是在社交网络上是有监管的，在出版商和消费者进行博弈的同时，还有监管部门的存在，就是说如果传播的是假新闻，他们会得到负的效用，这并不符合纳什均衡。

- 在分析假新闻在社交媒体上的传播模型时，可以根据不同平台的传播方式来进行分类，比如微博和微信。微信是一个熟人社区，也就是微信上转发的东西只有自己的熟人能看到。而微博是一个开放的社区，微博上面转发的东西几乎全部人都能立即看到。我们如果进一步研究，可以研究微博的广场效应和微信的熟人效应来建立细分的模型。
