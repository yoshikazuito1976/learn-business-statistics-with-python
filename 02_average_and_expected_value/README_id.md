# 02 Average and Expected Value

## Bahasa Indonesia

Pada bab ini, Anda mempelajari rata-rata dan nilai harapan.

## Tujuan Bab

- Memahami rata-rata
- Memahami nilai harapan
- Memahami bahwa nilai harapan bukan hasil pasti
- Memakai probabilitas x jumlah percobaan untuk memperkirakan hasil rata-rata
- Memverifikasi dengan simulasi Python
- Menghubungkan konsep ini ke keputusan bisnis

## Apa itu rata-rata?

Rata-rata adalah nilai perwakilan dari beberapa angka.

```text
2, 4, 6, 8, 10
(2 + 4 + 6 + 8 + 10) / 5 = 6
```

Rata-rata berguna, tetapi tidak selalu cukup untuk memahami data.

## Apa itu nilai harapan?

Nilai harapan adalah hasil rata-rata jika kejadian acak diulang banyak kali.

Jika peluang menang 10% dan diulang 10 kali:

```text
10 x 0.1 = 1
```

Nilai harapan menang adalah 1 kali.
Namun, ini bukan jaminan hasil pada satu percobaan.

## Contoh konkret nilai harapan

1. Klik iklan: 100 x 0.05 = 5
2. Konversi sales: 30 x 0.1 = 3
3. Waktu respons: 20 x 12 = 240 menit
4. Proyeksi omzet: 100 x 3000 = 300000
5. Gacha 2%: 100 x 0.02 = 2
6. Prediksi absen: 40 x 0.05 = 2
7. Produk cacat: 1000 x 0.01 = 10

Semua nilai di atas adalah perkiraan rata-rata, bukan hasil pasti.

## Simulasi Python

```python
import random

p = 0.1
trials_per_set = 10
set_count = 1000
results = []

for _ in range(set_count):
    win_count = 0
    for i in range(trials_per_set):
        if random.random() < p:
            win_count += 1
    results.append(win_count)

print(sum(results) / len(results))
```

## Kaitan dengan bisnis

Rata-rata dan nilai harapan dipakai untuk perencanaan:
- estimasi klik
- estimasi konversi
- estimasi waktu kerja
- estimasi pendapatan

Tetapi keputusan tidak boleh hanya berdasar rata-rata.
Variasi data juga harus dipertimbangkan.

## Ringkasan

- Rata-rata adalah nilai pusat
- Nilai harapan adalah perkiraan rata-rata untuk kejadian acak
- Nilai harapan bukan jaminan hasil satu kali
- Rata-rata yang sama bisa punya pola data yang berbeda
