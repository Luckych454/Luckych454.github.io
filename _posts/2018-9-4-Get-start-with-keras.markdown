---
title:  "Get start with keras"
data:  2018-9-4 14:45:00
tags:  Keras
---
不久前学完了Andrew Ng的machine learning, 现在打算通过对keras的学习加深对神经网络的理解。

![ ](http://images2015.cnblogs.com/blog/1119747/201707/1119747-20170707133635659-888158147.png  "keras的模块结构")

![ ](http://images2015.cnblogs.com/blog/1119747/201707/1119747-20170707133932722-715494711.png  "使用keras搭建一个神经网络")

下面是一个最最基本的keras程序。
```python3
from keras.models import Sequential
from keras.layers import Input,Dense
import numpy as np

model = Sequential()
model.add(Dense(units=32,activation='relu',input_dim=100))
model.add(Dense(units=1,activation='sigmoid'))
model.compile(optimizer='rmsprop',loss='binary_crossentropy',metrics=['accuracy'])

data = np.random.random((1000,100))
labels = np.random.randint(2,size = (1000,1))

model.fit(data,labels,epochs=10,batch_size =32)
score = model.evaluate(data, labels, verbose=0)
print('Test loss:', score[0])
print('Test accuracy:', score[1])
```

接下来就是对keras的各种分析

*待续*
