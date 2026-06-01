# 06 Regression Analysis

## この章の目的

この章では、回帰分析を使って「変数間の関係を式で表す」方法を学びます。

## なぜ回帰分析を使うのか

ビジネスでは、単に関連を見るだけでなく、次の判断が必要です。

- 広告費をどれだけ増やすと売上がどれだけ動きそうか
- 来店数が増えたときの必要人員をどれくらい見込むか

回帰分析は、説明と予測の両方に使える道具です。

## ビジネス例

来店数と売上の関係を単回帰で確認します。

```python
import numpy as np
from scipy import stats

np.random.seed(2)
visitors = np.random.randint(100, 500, 80)
sales = 500 + 120 * visitors + np.random.normal(0, 8000, 80)

slope, intercept, r_value, p_value, std_err = stats.linregress(visitors, sales)

print("slope:", slope)
print("intercept:", intercept)
print("R^2:", r_value ** 2)
print("p-value:", p_value)
```

## 読み方

- 傾き: 説明変数が1増えたとき、目的変数が平均でどれだけ変わるか
- 切片: 説明変数が0のときの理論上の値
- R^2: どれくらい説明できているかの目安
- p値: その関係を偶然とみなせるかの目安

## 注意点

- 外れ値に影響されやすい
- 線形でない関係は単回帰だけでは表しにくい
- 実務では残差確認が重要

## 次の章

次の章では、回帰や検定の前提になる母集団と標本を整理します。
