## 详细说明

### 决策边界因k值而异

改变k值后识别出的决策边界会如何变化？

![image.png](images/3.png)

图中从左到右分别为 k=1、5、30。

k=1时出现了像飞地一样的决策边界，说明发生了过拟合。过少的k值可能会使模型非常敏感于训练数据中的噪声和异常值。

k=5时边界变得平滑，相比于 k=1明显好转。

而k=30时，在橙色区域夹杂了许多蓝色的点，说明边界过于宽松导致 错误的判断。它会更多地依赖于全局模式而非局部数据。这样，模型可能无法捕捉到数据中的细节和复杂性

以上说明k值十分重要，需要调优得到最佳的k值。

### 注意点

数据量较小或维度较小时，KNN效果很好。但是一旦数据量较大或维度较大，KNN需要在大量训练数据进行近邻搜索以找到最近的点。需要大量存储容量来存储数据。因此不适合 KNN。  

对于高维数据，KNN也无法很好学习。KNN起作用的前提是“只要拥有的训练数据多，就能在未知数据的附近发现训练数据”这一假设。这个假设叫作渐近假设，但对于高维数据来说，这个假设不一定成立。