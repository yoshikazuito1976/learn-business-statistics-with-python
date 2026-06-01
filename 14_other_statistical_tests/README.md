# 14 Other Statistical Tests

## この章の目的

この章では、代表的な検定手法を「どんな場面で使うか」を中心に整理します。

## 検定手法の使い分け（概要）

- z検定: 母分散既知など条件が強い平均比較
- 対応のないt検定: 独立2群の平均比較
- 対応のあるt検定: 同一対象の前後比較
- 分散分析 (ANOVA): 3群以上の平均比較
- Mann-Whitney U検定: 順位ベースで2群比較（非正規に強い）
- Wilcoxon符号付順位検定: 対応ありの非パラメトリック比較
- Fisherの正確確率検定: 小標本の2x2分割表
- 相関係数の検定: 相関が0とみなせるか

## ビジネスでの選び方

1. 連続値かカテゴリか
2. 2群比較か3群以上か
3. 対応ありか対応なしか
4. 前提（正規性・等分散）が厳しいか

## 最小コード例（ANOVA）

```python
import numpy as np
from scipy import stats

np.random.seed(10)
g1 = np.random.normal(70, 8, 30)
g2 = np.random.normal(73, 8, 30)
g3 = np.random.normal(78, 8, 30)

f_stat, p_value = stats.f_oneway(g1, g2, g3)
print("F:", f_stat)
print("p:", p_value)
```

## 注意点

検定は万能ではありません。

- 前提が崩れると結論が不安定
- p値だけで意思決定しない
- 実務では効果量・コスト・実装難易度と合わせて判断する

## 次の章

次の章では、学んだ内容をビジネス意思決定に接続します。
