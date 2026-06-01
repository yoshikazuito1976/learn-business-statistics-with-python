# 12 t-test

## この章の目的

この章では、平均値の差を比較する t検定を学びます。

## 扱うビジネス場面

- AパターンとBパターンの広告効果の比較
- 研修前後のテスト点数の比較
- 2つのクラスやグループの平均値比較

## 1. A/B広告の平均クリック率比較（対応なし）

```python
import numpy as np
from scipy import stats

np.random.seed(8)
A = np.random.normal(loc=0.095, scale=0.020, size=50)
B = np.random.normal(loc=0.110, scale=0.020, size=50)

t_stat, p_value = stats.ttest_ind(A, B, equal_var=False)
print("t:", t_stat)
print("p:", p_value)
```

## 2. 研修前後の点数比較（対応あり）

```python
import numpy as np
from scipy import stats

np.random.seed(9)
before = np.random.normal(loc=62, scale=8, size=30)
after = before + np.random.normal(loc=4, scale=5, size=30)

t_stat, p_value = stats.ttest_rel(before, after)
print("t:", t_stat)
print("p:", p_value)
```

## 3. 2グループ比較の読み方

- p値が小さい: 差が偶然だけでは説明しにくい
- p値が大きい: 差がないと断定ではなく、証拠不足の可能性

## 実務上の注意

- 平均差の大きさ（効果量）も見る
- サンプルサイズが小さいと見落としやすい
- 前提（正規性や分散）を確認する

## 次の章

次の章では、カテゴリデータ同士の関係を見る χ二乗検定を学びます。
