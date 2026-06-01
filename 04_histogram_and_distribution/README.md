# 04 Histogram and Distribution

## この章の目的

この章では、度数分布表とヒストグラムを使って、データの分布を観察する方法を学びます。

平均だけでは見えない「偏り」「ばらつき」「外れ値の気配」をつかむことが目標です。

## なぜ分布を見るのか

ビジネスでは、同じ平均でも現場の意味が変わることがあります。

例:
- 平均購入金額は同じでも、高額顧客が少数いるのか、全体が均一なのか
- 平均対応時間は同じでも、遅い案件が一部に集中していないか

分布を見ることで、改善の優先順位を決めやすくなります。

## ビジネス例

EC サイトの1注文あたり購入金額を観察する場面を考えます。

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

np.random.seed(0)
amount = np.random.gamma(shape=2.0, scale=1500, size=300)
df = pd.DataFrame({"amount": amount})

# 度数分布表
bins = [0, 1000, 2000, 3000, 5000, 10000]
freq = pd.cut(df["amount"], bins=bins).value_counts().sort_index()
print(freq)

# ヒストグラム
plt.hist(df["amount"], bins=20, edgecolor="black")
plt.xlabel("Purchase Amount")
plt.ylabel("Frequency")
plt.title("Histogram of Purchase Amount")
plt.show()
```

## 観察ポイント

- 山が1つか複数か
- 右に長い尾があるか
- 極端に大きい値があるか
- 区間ごとの件数に偏りがあるか

## この章での判断

ヒストグラムは「計算結果」ではなく「現場の状態」を見る道具です。

施策前後で分布がどう変わったかを見ると、平均の変化より実務的な示唆が得られることがあります。

## 次の章

次の章では、2変数の関係を見るために散布図と相関を学びます。
