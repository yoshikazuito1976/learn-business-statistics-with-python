# 01 Probability and Trials

## Bahasa Indonesia

Pada bab ini, Anda mempelajari probabilitas dan percobaan.

Probabilitas bukan alat untuk menebak hasil satu kali secara tepat.
Probabilitas adalah alat untuk melihat kecenderungan saat kondisi yang sama diulang berkali-kali.

## Tujuan Bab

- Memahami probabilitas
- Memahami percobaan
- Memahami perbedaan hasil satu kali dan kecenderungan berulang
- Memahami bahwa probabilitas dan hasil nyata tidak selalu sama
- Mengamati bahwa semakin banyak percobaan, pola semakin terlihat
- Menjalankan simulasi probabilitas dengan Python

## Apa itu probabilitas?

Probabilitas adalah angka yang menunjukkan seberapa mungkin suatu kejadian terjadi.

Jika peluang menang undian 10%, itu tidak berarti dalam 1 kali undian pasti menang 0,1 kali.
Hasil 1 kali undian hanya dua: menang atau kalah.

Makna 10% adalah: jika diulang sangat banyak, proporsi menang cenderung mendekati 10%.

## Apa itu percobaan?

Percobaan adalah satu tindakan/eksperimen dengan kondisi yang sama.

Contoh:
- Mengambil undian 1 kali
- Melempar dadu 1 kali
- 1 pengguna melihat halaman produk
- Mengirim 1 email
- Menampilkan 1 iklan

## Contoh undian 10%

Pada 1 kali undian:
- Menang
- Kalah

Dari satu hasil, sulit merasakan arti 10%.
Jika diulang 100, 1000, 10000 kali, proporsi menang cenderung mendekati 10%.

## Peluang menang setidaknya 1 kali dalam 10 undian

Dua hal yang berbeda:
- Peluang menang per undian adalah 10%
- Peluang menang minimal 1 kali dalam 10 undian bukan 10%

Gunakan kejadian kebalikan:

```text
P(minimal 1 menang) = 1 - P(10 kali semuanya kalah)
P(10 kali kalah) = 0.9^10 = 0.3486784401
P(minimal 1 menang) = 1 - 0.9^10 = 0.6513215599
```

Secara intuitif, cukup diingat sekitar 65%.
10% adalah peluang per percobaan, bukan peluang untuk keseluruhan 10 percobaan.

## Representasi undian dengan Python

```python
import random

if random.random() < 0.1:
    print("menang")
else:
    print("kalah")
```

## Ulang 100 kali

```python
import random

win_count = 0
trial_count = 100

for i in range(trial_count):
    if random.random() < 0.1:
        win_count += 1

print("jumlah percobaan:", trial_count)
print("jumlah menang:", win_count)
print("rasio menang:", win_count / trial_count)
```

Hasil bisa berbeda setiap eksekusi.

## Perbesar jumlah percobaan

```python
import random

trial_counts = [10, 100, 1000, 10000]

for trial_count in trial_counts:
    win_count = 0
    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1
    print(trial_count, win_count, win_count / trial_count)
```

Percobaan sedikit lebih mudah berfluktuasi.
Percobaan banyak cenderung mendekati 10%.

## Visualisasi grafik

```python
import random
import matplotlib.pyplot as plt

trial_counts = [10, 100, 1000, 10000]
win_rates = []

for trial_count in trial_counts:
    win_count = 0
    for i in range(trial_count):
        if random.random() < 0.1:
            win_count += 1
    win_rates.append(win_count / trial_count)

plt.bar([str(x) for x in trial_counts], win_rates)
plt.axhline(0.1, linestyle="--")
plt.show()
```

## Kaitan dengan bisnis

Satu hasil tidak cukup untuk menyimpulkan kondisi keseluruhan.
Kita perlu banyak percobaan dan melihat tren data.

## Ringkasan

- Probabilitas menyatakan kemungkinan
- Hasil sekali dan tren berulang berbeda
- Percobaan sedikit mudah berfluktuasi
- Percobaan banyak membuat tren lebih jelas
- Python membantu simulasi fenomena probabilistik
