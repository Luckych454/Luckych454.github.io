---
title: "The  Activation of Keras"
data: 2018-9-7
tags: "Keras"
---
在介绍*layouts*之前，我们先来了解一下*Activations*。Keras里面预定义了10种激活函数。

激活函数可以通过设置单独的激活层实现，也可以在构造层对象时通过传递activation参数实现

```python3
from keras.layers import Activation, Dense
model.add(Dense(64))
model.add(Activation('tanh'))
```
等价于
```python3
model.add(Dense(64, activation='tanh'))
```

# **softmax**

*softmax*函数将每个得出来的数求指数，然后归一化。

![softmax函数](https://pic4.zhimg.com/75938cc54604077d2ed193e97a5302bb_b.jpg "softmax函数")
取指数的第一个原因是要模拟max的行为，所以要让大的更大。第二个原因是需要一个可导的函数。
让大的更大的原因是让错的更错，这样学习效率更高。好比以前考试错了，老师轻轻说了两句，换成softmax两巴掌上去。
```python3
softmax(x, axis=-1)
#x: 张量。
#axis: 整数，代表softmax作用的维度。
```

# **elu**

![elu函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/0169720171010094120.png  "elu函数")

```python3
elu(x, alpha=1.0)
#x：张量。
#alpha：一个标量，表示负数部分的斜率。
```

# **selu**

![selu函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/3192020171010094215.png  "selu函数")
SELU 等同于：scale * elu(x, alpha),其中λ和α是固定数值（分别为 1.0507 和 1.6726）。

# **softplus**

![softplus函数](https://mmbiz.qpic.cn/mmbiz_png/KmXPKA19gW98zItS1d5CbvFj50ujz1AGzV7Rw8v6SLLnZzsxia35oOSWZLgl5ehbh9l0Vicwb5QVvFjibbRibeGMZQ/0?wx_fmt=png "softplus函数")

*softplus*函数是*relu*不错的替代选择,*softplus*能返回任何大于零的值。并且*softplus*的倒数是连续的，非零的，从而防止出现静默神经元。但是*softplus*的倒数常常小于1，可能出现梯度缺失的情况。

# **softsign**

![softsign函数](https://mmbiz.qpic.cn/mmbiz_png/KmXPKA19gW98zItS1d5CbvFj50ujz1AGOCXyAWnnKVsmVF90iakFT9sibwc8Q6TNFu1k6iaqsnhqYLsphS803YYSg/0?wx_fmt=png "softsign函数")

*softsign*函数是*tanh*函数的一种替代选择，它能更高效地学习，同时，导数的计算币tanh更麻烦。

# **relu**

![relu函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/4217520171010093357.png  "relu函数")

修正线性单元（Rectified linear unit，ReLU）是神经网络中最常用的激活函数。它保留了 step 函数的生物学启发（只有输入超出阈值时神经元才激活），不过当输入为正的时候，导数不为零，从而允许基于梯度的学习（尽管在 x=0 的时候，导数是未定义的）。使用这个函数能使计算变得很快，因为无论是函数还是其导数都不包含复杂的数学运算。然而，当输入为负值的时候，ReLU 的学习速度可能会变得很慢，甚至使神经元直接无效，因为此时输入小于零而梯度为零，从而其权重无法得到更新，在剩下的训练过程中会一直保持静默。

# **tanh**

![tanh函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/8940520171010093544.png  "tanh函数")

在分类任务中，双曲正切函数（Tanh）逐渐取代 Sigmoid 函数作为标准的激活函数，其具有很多神经网络所钟爱的特征。它是完全可微分的，反对称，对称中心在原点。为了解决学习缓慢和/或梯度消失问题，可以使用这个函数的更加平缓的变体（log-log、softsign、symmetrical sigmoid 等等）。

# **sigmoid**

![sigmoid函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/5561420171010093434.png  "sigmoid函数")

sigmoid函数经常用于*Logistics Regression*中，从它的图像可看出，当*x>0*时,*S(x)>0.5*,当*x<0*时,*S(x)<0.5*

# **hard_sigmoid**

![hard_sigmoid函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/8435220171010094403.png  "hard_sigmoid函数")

hard_sigmoid的计算速度比 sigmoid 激活函数更快。但是可能导致静默神经元。

# **linear**

![linear函数](https://image.jiqizhixin.com/uploads/wangeditor/5abc32e8-b02e-4b03-b527-c0a149f1bc78/9840820171010093320.png  "linear函数")

通过激活函数 Identity，节点的输入等于输出。它完美适合于潜在行为是线性（与线性回归相似）的任务。当存在非线性，单独使用该激活函数是不够的，但它依然可以在最终输出节点上作为激活函数用于回归任务。

# **高级激活函数**

在```keras.layers.advanced_activations```模块中，可以找到*PReLU*,和*LeakyReLU*

以上就是对keras所提供的激活函数的介绍，在不断的发现问题的同时不断得解决问题，正是学习的关键。

[机器之心-26种神经网络激活函数可视化


](https://www.jiqizhixin.com/articles/2017-10-10-3) 
[图片来源(看得更清晰)](https://dashee87.github.io/data%20science/deep%20learning/visualising-activation-functions-in-neural-networks/) 
