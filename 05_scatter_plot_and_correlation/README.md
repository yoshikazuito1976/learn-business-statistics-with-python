# 05 Scatter Plot and Correlation

## この章の目的

この章では、散布図で2つの変数の関係を可視化し、相関係数で関係の強さを数値化する方法を学びます。

## なぜ散布図と相関を見るのか

ビジネスでは、次のような問いがよくあります。

- 広告費を増やすと売上は本当に増えるか
- 接客時間が長いほど満足度は高いか
- 値引き率が高いほど購入率は上がるか

関係の方向と強さを把握することで、打ち手の優先順位をつけやすくなります。

## ビジネス例

広告費と売上の関係を確認します。

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

np.random.seed(1)
ad_cost = np.random.uniform(50, 300, 60)
sales = 200 + 8 * ad_cost + np.random.normal(0, 120, 60)
df = pd.DataFrame({"ad_cost": ad_cost, "sales": sales})

# 散布図
plt.scatter(df["ad_cost"], df["sales"])
plt.xlabel("Ad Cost")
plt.ylabel("Sales")
plt.title("Ad Cost vs Sales")
plt.show()

# 相関係数
corr = df[["ad_cost", "sales"]].corr().loc["ad_cost", "sales"]
print("correlation:", corr)
```

## 観察ポイント

- 右上がりか、右下がりか
- 直線に近いか、曲線的か
- 外れ値が全体の傾向をゆがめていないか

## 注意点

相関があることと、因果関係があることは別です。

例: 季節要因やキャンペーン時期など、第三の要因で同時に動いている場合があります。

## 次の章

次の章では、相関を一歩進めて、回帰分析で予測と説明を行います。
