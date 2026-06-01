# 03 Variance and Standard Deviation

## 中文

本章学习平均值以外的重要信息：数据的离散程度。

例如：

```text
A: 48, 49, 50, 51, 52
B: 10, 30, 50, 70, 90
```

两组数据平均值都为 50，但分散程度明显不同。

## 为什么平均值不够

在业务中不仅要看水平，还要看稳定性：
- 每日销售是否稳定
- 客流是否波动过大
- 处理时间是否一致

平均值只告诉你中心，不告诉你分散。

## 偏差

偏差是每个数据点与平均值的差：

```text
偏差 = 数据值 - 平均值
```

偏差直接相加会正负抵消，因此不能直接衡量离散。

## 方差

把偏差平方后再取平均，得到方差。

## 标准差

方差的单位是平方单位，不够直观。
对方差开平方，得到标准差，单位回到原单位。

## Python 示例

```python
data = [40, 50, 60]

mean = sum(data) / len(data)
deviations = [x - mean for x in data]
squared = [d ** 2 for d in deviations]
variance = sum(squared) / len(data)
std = variance ** 0.5

print(mean, deviations, variance, std)
```

## NumPy 示例

```python
import numpy as np

data = [40, 50, 60]
print(np.mean(data))
print(np.var(data))
print(np.std(data))
```

## 业务意义

两家门店平均销售额可以相同，但波动风险可能完全不同。
标准差有助于评估稳定性和风险。

## 小结

- 平均值表示中心
- 方差与标准差表示离散
- 平均值相同不代表数据状态相同
- 业务判断应同时关注水平与波动
