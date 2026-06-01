# 10 Interval Estimation

## この章の目的

この章では、点推定だけでなく、区間推定（信頼区間）で不確実性を表現する方法を学びます。

## なぜ信頼区間を見るのか

平均値1つだけでは、推定の不確実性が見えません。

信頼区間を使うと「どの範囲に母平均がありそうか」を幅で示せます。

## ビジネス例

新しい導線のページ滞在時間の平均を標本から推定します。

```python
import numpy as np
from scipy import stats

np.random.seed(6)
sample = np.random.normal(loc=180, scale=40, size=80)

mean = sample.mean()
sem = stats.sem(sample)  # 標準誤差
ci_low, ci_high = stats.t.interval(confidence=0.95, df=len(sample)-1, loc=mean, scale=sem)

print("sample mean:", mean)
print("95% CI:", (ci_low, ci_high))
```

## 読み方

- 区間が狭い: 推定の精度が高い
- 区間が広い: 推定の不確実性が大きい

## 信頼区間の実務的な意味

「真の値がこの区間に95%の確率で入る」というより、
「同じ手順を繰り返すと、95%の区間が真の値を含む」という手続きの信頼性を表します。

## 次の章

次の章では、仮説検定の考え方を整理し、p値・有意水準・棄却の意味を扱います。
