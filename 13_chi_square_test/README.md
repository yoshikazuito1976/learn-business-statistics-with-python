# 13 Chi-square Test

## この章の目的

この章では、カテゴリデータ同士の関係を確認する χ二乗検定を学びます。

## 扱うビジネス場面

- 性別や年代と購入有無の関係
- 広告パターンとクリック有無の関係
- アンケート回答と属性の関係

## 例: 広告パターンとクリック有無

```python
import pandas as pd
from scipy.stats import chi2_contingency

# 行: 広告パターン, 列: クリック有無
table = pd.DataFrame(
    [[120, 880], [160, 840]],
    index=["Pattern_A", "Pattern_B"],
    columns=["Click", "No_Click"]
)

chi2, p_value, dof, expected = chi2_contingency(table)
print("chi2:", chi2)
print("p:", p_value)
print("dof:", dof)
print("expected:\n", expected)
```

## 読み方

- 帰無仮説: 行と列は独立（関係なし）
- p値が小さい: 独立とみなすには無理がある
- p値が大きい: 関係があると言い切る証拠が不足

## 実務でのポイント

- 件数が極端に少ないセルが多いときは注意
- 比率差の大きさも合わせて確認する
- セグメント施策の優先順位づけに使える

## 次の章

次の章では、代表的な検定手法を一覧で整理します。
