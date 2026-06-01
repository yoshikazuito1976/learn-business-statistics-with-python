# 03 Variance and Standard Deviation
# 分散と標準偏差

## この章の目的

前回は「平均」と「期待値」を学びました。

平均は、複数のデータをひとつの代表値として見るために便利です。

しかし、平均だけではデータの特徴を十分に説明できないことがあります。

この章では、データの「ばらつき」に注目します。

---

## 平均だけでは見えないこと

次の2つのデータを見てみましょう。

```python
data_a = [50, 50, 50, 50, 50]
data_b = [30, 40, 50, 60, 70]
```

どちらも平均は同じです。

```python
data_a = [50, 50, 50, 50, 50]
data_b = [30, 40, 50, 60, 70]

avg_a = sum(data_a) / len(data_a)
avg_b = sum(data_b) / len(data_b)

print(avg_a)
print(avg_b)
```

実行結果

```text
50.0
50.0
```

平均だけを見ると、2つのデータは同じように見えます。

しかし、実際にはかなり違います。

- `data_a` はすべて同じ値
- `data_b` は小さい値から大きい値まで広がっている

この違いを表すために使うのが、**分散**と**標準偏差**です。

---

## ばらつきとは何か

ばらつきとは、データが平均からどれくらい離れているかという考え方です。

平均に近い値ばかりなら、ばらつきは小さいです。

平均から遠い値が多ければ、ばらつきは大きいです。

---

## 平均からの差を見る

まず、それぞれの値が平均からどれくらい離れているかを見ます。

```python
data = [30, 40, 50, 60, 70]

average = sum(data) / len(data)

for x in data:
    difference = x - average
    print(x, difference)
```

実行結果

```text
30 -20.0
40 -10.0
50 0.0
60 10.0
70 20.0
```

平均より小さい値はマイナスになります。

平均より大きい値はプラスになります。

しかし、このまま合計すると問題があります。

```python
data = [30, 40, 50, 60, 70]

average = sum(data) / len(data)

total_difference = 0

for x in data:
    total_difference += x - average

print(total_difference)
```

実行結果

```text
0.0
```

平均との差をそのまま合計すると、プラスとマイナスが打ち消し合ってしまいます。

そこで、平均との差を2乗します。

---

## 分散とは

分散とは、ざっくり言うと、

> 平均からのズレを2乗して、その平均を取ったもの

です。

```python
data = [30, 40, 50, 60, 70]

average = sum(data) / len(data)

squared_differences = []

for x in data:
    difference = x - average
    squared_difference = difference ** 2
    squared_differences.append(squared_difference)

variance = sum(squared_differences) / len(squared_differences)

print(variance)
```

実行結果

```text
200.0
```

分散が大きいほど、データのばらつきは大きいと考えます。

---

## 標準偏差とは

分散は、平均との差を2乗しているため、単位が元のデータとずれます。

たとえば、点数のデータなら、分散は「点数の2乗」のような意味になってしまいます。

そこで、分散の平方根を取ります。

これが**標準偏差**です。

```python
data = [30, 40, 50, 60, 70]

average = sum(data) / len(data)

squared_differences = []

for x in data:
    difference = x - average
    squared_difference = difference ** 2
    squared_differences.append(squared_difference)

variance = sum(squared_differences) / len(squared_differences)
standard_deviation = variance ** 0.5

print(variance)
print(standard_deviation)
```

実行結果

```text
200.0
14.142135623730951
```

標準偏差は、元のデータと同じ単位でばらつきを見るための値です。

---

## Pythonのstatisticsモジュールを使う

Pythonには、平均・分散・標準偏差を計算するための機能があります。

```python
import statistics

data = [30, 40, 50, 60, 70]

print(statistics.mean(data))
print(statistics.pvariance(data))
print(statistics.pstdev(data))
```

実行結果

```text
50
200
14.142135623730951
```

ここでは、全体のデータを対象にするため、`pvariance()` と `pstdev()` を使っています。

- `pvariance()`：母分散
- `pstdev()`：母標準偏差

---

## 平均が同じでも、ばらつきは違う

次の2つのデータを比べます。

```python
import statistics

data_a = [50, 50, 50, 50, 50]
data_b = [30, 40, 50, 60, 70]

print("data_a")
print("average:", statistics.mean(data_a))
print("standard deviation:", statistics.pstdev(data_a))

print("data_b")
print("average:", statistics.mean(data_b))
print("standard deviation:", statistics.pstdev(data_b))
```

実行結果

```text
data_a
average: 50
standard deviation: 0.0
data_b
average: 50
standard deviation: 14.142135623730951
```

どちらも平均は50です。

しかし、標準偏差は違います。

`data_a` はすべて同じ値なので、ばらつきはありません。

`data_b` は平均から離れた値があるため、ばらつきがあります。

---

## ビジネスでの見方

たとえば、2つの店舗の1日の売上が次のようになっていたとします。

```python
store_a = [100, 100, 100, 100, 100]
store_b = [60, 80, 100, 120, 140]
```

どちらも平均売上は100です。

しかし、安定しているのは `store_a` です。

`store_b` は売上が大きい日もありますが、小さい日もあります。

```python
import statistics

store_a = [100, 100, 100, 100, 100]
store_b = [60, 80, 100, 120, 140]

print("store_a")
print("average:", statistics.mean(store_a))
print("standard deviation:", statistics.pstdev(store_a))

print("store_b")
print("average:", statistics.mean(store_b))
print("standard deviation:", statistics.pstdev(store_b))
```

平均だけを見ると同じです。

しかし、標準偏差を見ると、安定性の違いが見えてきます。

---

## 乱数でばらつきを観察する

次に、サイコロを何回も振った結果を使って、ばらつきを見てみます。

```python
import random
import statistics

results = []

for i in range(100):
    dice = random.randint(1, 6)
    results.append(dice)

print(results)
print("average:", statistics.mean(results))
print("standard deviation:", statistics.pstdev(results))
```

サイコロの結果は毎回変わります。

そのため、平均や標準偏差も少しずつ変わります。

ただし、試行回数を増やすと、全体の傾向が見えやすくなります。

---

## 試行回数を増やして比較する

```python
import random
import statistics

for n in [10, 100, 1000, 10000]:
    results = []

    for i in range(n):
        dice = random.randint(1, 6)
        results.append(dice)

    print("trials:", n)
    print("average:", statistics.mean(results))
    print("standard deviation:", statistics.pstdev(results))
    print()
```

試行回数が少ないと、結果は大きくぶれます。

試行回数が多くなると、平均や標準偏差は安定してきます。

ここでも大事なのは、

> 1回の結果ではなく、複数回の結果を集めて全体の傾向を見る

という考え方です。

---

## 確認問題

### 問題1

次の2つのデータについて、平均と標準偏差を計算してください。

```python
class_a = [70, 70, 70, 70, 70]
class_b = [50, 60, 70, 80, 90]
```

平均だけを見た場合と、標準偏差まで見た場合で、どのような違いがあるでしょうか。

---

### 問題2

次の売上データについて、どちらの店舗の売上が安定しているか考えてください。

```python
shop_a = [98, 102, 100, 101, 99]
shop_b = [70, 130, 90, 110, 100]
```

平均と標準偏差を計算して説明してください。

---

## まとめ

この章では、平均だけでは見えない「ばらつき」を扱いました。

重要なポイントは次の通りです。

- 平均はデータの代表値である
- しかし、平均だけではデータの広がりはわからない
- ばらつきは、データが平均からどれくらい離れているかを見る考え方である
- 分散は、平均との差を2乗して平均したもの
- 標準偏差は、分散の平方根である
- 標準偏差を見ると、データの安定性やリスクを考えやすくなる

ビジネスでは、平均だけで判断すると危険なことがあります。

平均とあわせて、ばらつきも見ることで、より正確に状況を判断できます。

---

## キーメッセージ

> 平均は中心を見る。標準偏差は広がりを見る。
