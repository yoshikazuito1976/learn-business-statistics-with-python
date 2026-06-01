# 07 Population and Sample

## この章の目的

この章では、母集団と標本の違いを理解し、なぜ標本から母集団を推測するのかを学びます。

## なぜ重要か

実務では全件調査が難しいことがほとんどです。

- 全顧客への聞き取りはコストが高い
- 全製品検査は時間がかかる
- すべての広告パターンを同時に試せない

そのため、標本を使って全体を推測します。

## 基本用語

- 母集団: 調べたい対象全体
- 標本: 母集団から取り出した一部
- 標本統計量: 標本平均や標本比率など

## ビジネス例

全顧客 10000 人のうち、300 人を抽出して満足度を調べる場面を考えます。

```python
import numpy as np

np.random.seed(3)
population = np.random.normal(loc=70, scale=10, size=10000)
sample = np.random.choice(population, size=300, replace=False)

print("population mean:", population.mean())
print("sample mean:", sample.mean())
```

## 観察ポイント

- 標本平均は母平均と近いが、必ず一致はしない
- 抽出方法が偏ると推定も偏る

## 実務での使い方

調査設計では「どこから、どう抽出した標本か」を説明できることが重要です。

## 次の章

次の章では、標本抽出とシミュレーションを使って推測の安定性を確認します。
