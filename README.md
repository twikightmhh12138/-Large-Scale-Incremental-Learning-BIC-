# -Large-Scale-Incremental-Learning-BIC-
实现了BIC方法，并在cifar-100数据集上进行了测试，最终得到的结果与论文的数据相差很小，验证了BIC方法的准确性和有效性
# BIC
# 数据集
从 https://www.cs.toronto.edu/~kriz/cifar-100-python.tar.gz 上下载CIFAR-100数据集

Put meta, train, test into ./cifar100

# 训练
```
python main.py
```

# Result

|    |  20  |  40  |  60  |  80  |  100  |
| ---- | ---- | ---- | ---- | ---- | ---- |
|  Paper  | 85.20 | 74.59 | 66.76 | 60.14 | 55.55 |
|  Implementation  | 82.25| 67.425| 62.10| 56.99｜ 52.94 |



# Alpha & Beta

### Adam (Bias correction layer)
|     |  20  |  40  |  60  |  80  |  100  |
| --- | ---- | ---- | ---- | ---- | ---- |
| Alpha | 1.0 | 0.822 | 0.734 | 0.723 | 0.705 |
| Beta | 0.0 | -0.287 | -0.302 | -0.312 | -0.319 |

### SGD (Bias correction layer)
|     |  20  |  40  |  60  |  80  |  100  |
| --- | ---- | ---- | ---- | ---- | ---- |
| Alpha | 1.0 | 1.006 | 1.017 | 0.976 | 0.983 |
| Beta | 0.0 | -2.809 | -3.496 | -3.447 | -3.683 |

不同的优化器得到的不同的ALpha和Beta值
