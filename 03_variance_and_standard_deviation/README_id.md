# 03 Variance and Standard Deviation

## Bahasa Indonesia

Bab ini membahas sebaran data (variasi) yang tidak bisa dipahami hanya dari rata-rata.

Contoh:

```text
A: 48, 49, 50, 51, 52
B: 10, 30, 50, 70, 90
```

Rata-ratanya sama (50), tetapi penyebarannya sangat berbeda.

## Mengapa rata-rata tidak cukup

Dalam bisnis, stabilitas juga penting:
- Apakah penjualan harian stabil?
- Apakah jumlah pengunjung terlalu berfluktuasi?
- Apakah waktu proses konsisten?

Rata-rata hanya menunjukkan pusat, bukan sebaran.

## Langkah awal: deviasi

Deviasi adalah selisih nilai terhadap rata-rata.

```text
deviasi = nilai - rata-rata
```

Jika deviasi dijumlahkan, nilai positif dan negatif saling meniadakan.

## Varians

Agar tidak saling meniadakan, deviasi dikuadratkan lalu dirata-ratakan.
Itulah varians.

## Simpangan baku

Varians memakai satuan kuadrat, sehingga kurang intuitif.
Akar kuadrat varians disebut simpangan baku (standard deviation).

## Contoh Python

```python
data = [40, 50, 60]

mean = sum(data) / len(data)
deviations = [x - mean for x in data]
squared = [d ** 2 for d in deviations]
variance = sum(squared) / len(data)
std = variance ** 0.5

print(mean, deviations, variance, std)
```

## Contoh NumPy

```python
import numpy as np

data = [40, 50, 60]
print(np.mean(data))
print(np.var(data))
print(np.std(data))
```

## Makna bisnis

Dua toko bisa punya rata-rata penjualan yang sama,
tetapi satu toko bisa jauh lebih tidak stabil.

Simpangan baku membantu menilai stabilitas dan risiko.

## Ringkasan

- Rata-rata menunjukkan pusat data
- Varians dan simpangan baku menunjukkan sebaran
- Rata-rata sama belum tentu kondisi data sama
- Keputusan bisnis perlu melihat pusat dan variasi sekaligus
