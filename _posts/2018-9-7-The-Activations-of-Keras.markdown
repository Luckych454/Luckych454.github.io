---
title: "The  Activations of Keras"
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
直接放链接吧。

[机器之心-26种神经网络激活函数可视化](https://www.jiqizhixin.com/articles/2017-10-10-3) 

[图片来源(看得更清晰)](https://dashee87.github.io/data%20science/deep%20learning/visualising-activation-functions-in-neural-networks/) 
