# 09 Central Limit Theorem

## この章の目的

この章では、中心極限定理の考え方を学びます。

要点は「標本平均の分布は、標本サイズが十分大きいと正規分布に近づく」ということです。

## なぜ重要か

中心極限定理があることで、区間推定や仮説検定の道具を使えるようになります。

つまり、実務での意思決定に使う統計推論の土台になります。

## ビジネス例

もともと歪んだ売上データから標本平均を何度も作り、その分布を見ます。

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(5)
population = np.random.exponential(scale=100, size=50000)

sample_size = 50
n_sim = 2000
means = []

for _ in range(n_sim):
    sample = np.random.choice(population, size=sample_size, replace=True)
    means.append(sample.mean())

plt.hist(means, bins=30, edgecolor="black")
plt.title("Sampling Distribution of Sample Mean")
plt.xlabel("Sample Mean")
plt.ylabel("Frequency")
plt.show()
```

## 観察ポイント

- 元データは右に歪んでいても、標本平均は鐘型に近づく
- 標本サイズが大きいほど、標本平均の分布は細くなる

## 次の章

次の章では、標本から母数の範囲を推定する区間推定と信頼区間を扱います。
