## 详细说明

如果数据不一定是线性分离的，也就是两类的数据点可能交杂在一起。

- 间隔内侧：指的是一些数据点会落在决策边界的“间隔”之内，甚至可能越过决策边界进入另一侧。这种情况下，这些数据点被称为“间隔内侧数据点”
- 硬间隔：适用于线性可分的数据，不允许任何数据点进入间隔内侧或越过决策边界，即要求分类严格无误。
- 软间隔：适用于数据可能非线性可分的情况，允许部分数据点进入间隔内侧甚至越界。这种方法使用松弛变量允许少量错误分类，以便在复杂的数据集上找到更好的决策边界。

以下考虑软间隔

设D为点与决策边界之间的距离；基于学习结果，我们可以将训练数据分为以下3种：

- D > 间隔：间隔外侧的数据。
- D = 间隔：间隔上的数据。
- D < 间隔，或者误分类的数据：间隔内侧的数据。

将D ≤ 间隔的数据称为支持向量，确定了决策边界，间隔外侧的数据则不会影响决策边界。

![image.png](images/1.png)

对于以上例子，对于线性可分的数据，如果强制训练数据不进入间隔内侧，可能会导致学习结果对数据过拟合。

在使用软间隔时，允许间隔内侧进入多少数据由超参数决定。

与其他算法一样，在决定超参数时，需要使用网格搜索（grid search）和随机搜索（random search）等方法反复验证后再做决定。