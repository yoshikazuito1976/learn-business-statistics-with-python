# 08 Sampling and Simulation

## この章の目的

この章では、標本抽出とシミュレーションを使って、推定値のぶれ方を体験的に理解します。

## なぜシミュレーションするのか

理論だけでは「どれくらいぶれるか」の感覚がつかみにくいからです。

同じ条件でも標本が変われば結果は変わります。
このぶれを見ておくことで、1回の結果を過信しにくくなります。

## ビジネス例

顧客満足度の平均を標本で推定する状況を1000回シミュレーションします。

```python
import numpy as np

np.random.seed(4)
population = np.random.normal(loc=75, scale=12, size=50000)

sample_size = 200
n_sim = 1000
sample_means = []

for _ in range(n_sim):
    s = np.random.choice(population, size=sample_size, replace=False)
    sample_means.append(s.mean())

print("population mean:", population.mean())
print("mean of sample means:", np.mean(sample_means))
print("std of sample means:", np.std(sample_means))
```

## 観察ポイント

- 標本平均は毎回違う
- ただし全体としては母平均の近くに集まる
- 標本サイズを増やすとぶれは小さくなる

## 次の章

次の章では、この現象を理論的に支える中心極限定理を学びます。
