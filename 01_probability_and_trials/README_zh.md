# 01 Probability and Trials

## 中文

本章学习概率与试验。

概率并不是对单次结果的精确预言。
概率是帮助我们在同一条件下反复试验时观察整体趋势的工具。

## 本章目标

- 理解什么是概率
- 理解什么是试验
- 理解单次结果与重复趋势的差异
- 理解概率与实际结果不必完全一致
- 观察试验次数增加后趋势更清晰
- 用 Python 进行概率模拟

## 什么是概率

概率是表示某个事件发生可能性的数值。

例如中奖概率是 10% 的抽奖。
10% 并不表示“抽一次就会中 0.1 次”。
抽一次只有“中”或“不中奖”两种结果。

10% 的含义是：在相同条件下反复进行很多次时，整体中奖比例倾向于接近 10%。

## 什么是试验

试验是指在相同条件下进行的一次操作。

例如：
- 抽奖一次
- 掷骰子一次
- 一个用户浏览一次商品页
- 发送一封邮件
- 展示一次广告

## 例子：中奖率 10% 的抽奖

单次结果只有：
- 中奖
- 未中奖

重复到 100、1000、10000 次时，中奖比例会更接近 10%。

## 抽 10 次至少中 1 次的概率

要区分：
- 抽一次中奖概率是 10%
- 抽10次至少中1次的概率不是 10%

用反事件计算更清楚：

```text
P(至少中1次) = 1 - P(10次全不中)
P(10次全不中) = 0.9^10 = 0.3486784401
P(至少中1次) = 1 - 0.9^10 = 0.6513215599
```

因此可以直观理解为大约 65%。
10% 是“单次中奖倾向”，不是“10次整体事件”的概率。

## Python 表达抽奖

```python
import random

if random.random() < 0.1:
    print("中奖")
else:
    print("未中奖")
```

## 重复 100 次

```python
import random

win_count = 0
trial_count = 100

for i in range(trial_count):
    if random.random() < 0.1:
        win_count += 1

print("试验次数:", trial_count)
print("中奖次数:", win_count)
print("中奖比例:", win_count / trial_count)
```

## 增加试验次数

```python
import random

trial_counts = [10, 100, 1000, 10000]

for trial_count in trial_counts:
    win_count = 0
    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1
    print(trial_count, win_count, win_count / trial_count)
```

## 图形确认

```python
import random
import matplotlib.pyplot as plt

trial_counts = [10, 100, 1000, 10000]
win_rates = []

for trial_count in trial_counts:
    win_count = 0
    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1
    win_rates.append(win_count / trial_count)

plt.bar([str(x) for x in trial_counts], win_rates)
plt.axhline(0.1, linestyle="--")
plt.show()
```

## 与业务的联系

只看一次成败容易误判。
业务统计需要收集多次试验与数据，观察整体趋势再判断。

## 小结

- 概率表示事件发生的可能性
- 单次结果与重复趋势不同
- 试验次数少时波动大
- 试验次数多时趋势更明显
- Python 可以帮助进行概率现象模拟
