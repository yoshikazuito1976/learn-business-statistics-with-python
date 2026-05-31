# 00_environment

## 日本語

この章では、この教材を進めるための学習環境を確認します。

目的は、難しい環境構築をすることではありません。
Python と表計算ツールで、データを扱う準備ができている状態を作ることです。

---

## この章の目的

この章では、次のことを確認します。

- Python を実行できること
- 表計算ツールを使えること
- 簡単な計算結果を表示できること
- 乱数を生成できること
- グラフを表示できること

---

## 使用する道具

この教材では、主に次の道具を使います。

- Python
- Google Colab または Jupyter Notebook
- Excel または Google スプレッドシート
- 必要に応じて matplotlib
- 必要に応じて pandas

すべてを最初から完璧に使いこなす必要はありません。
まずは、動作確認ができることを目標にします。

---

## 最低限の動作確認

### 1. Python の実行確認

```python
print("Hello, Business Statistics")
```

```text
Hello, Business Statistics
```

### 2. 簡単な計算の確認

```python
price = 1000
tax_rate = 0.1

total = price + price * tax_rate

print(total)
```

### 3. 乱数生成の確認

```python
import random

number = random.random()
print(number)
```

`random.random()` は、0以上1未満の値を返します。

### 4. グラフ表示の確認

```python
import matplotlib.pyplot as plt

values = [1, 2, 3, 4, 5]
counts = [2, 4, 6, 8, 10]

plt.bar(values, counts)
plt.show()
```

---

## 表計算ツールの確認

Excel や Google スプレッドシートでも、次の基本操作ができることを確認します。

- 表を作る
- 件数を数える
- グラフを作る

Python と表計算ツールのどちらも、データを観察するための道具です。

---

## まとめ

この章では、ビジネス統計を学ぶための環境を確認しました。

次の章から、確率と試行の内容に入ります。
