# 04 Histogram and Distribution

## Tujuan Bab

Pada bab ini, Anda mempelajari cara melihat distribusi data.

Rata-rata dan simpangan baku memang berguna, tetapi rata-rata saja tidak cukup untuk melihat bentuk sebaran data.
Dengan rata-rata yang sama pun, pola datanya bisa sangat berbeda.

- Banyak data berkumpul di sekitar rata-rata
- Data terpisah menjadi kelompok nilai tinggi dan rendah
- Nilai ekstrem menarik rata-rata ke atas

Alur observasi pada bab ini:

```text
Data mentah
->
Tabel distribusi frekuensi
->
Histogram
->
Interpretasi distribusi
```

## Apa itu Tabel Distribusi Frekuensi?

Tabel distribusi frekuensi membagi data ke dalam beberapa rentang, lalu menghitung banyak data di tiap rentang.

```python
scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]
```

## Frekuensi, Kelas, dan Lebar Kelas

- Frekuensi: jumlah data dalam suatu rentang
- Kelas: rentang pembagian data
- Lebar kelas: ukuran rentang kelas

Jika kelas terlalu lebar, detail kecil sulit terlihat.
Jika terlalu sempit, tren umum bisa sulit dibaca.

## Membuat Tabel Frekuensi dengan Python

```python
import pandas as pd

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

bins = [40, 50, 60, 70, 80, 90, 100]
labels = [
    "40-<50",
    "50-<60",
    "60-<70",
    "70-<80",
    "80-<90",
    "90-100"
]

groups = pd.cut(scores, bins=bins, labels=labels, right=False)
frequency_table = groups.value_counts().sort_index()
print(frequency_table)
```

## Apa itu Histogram?

Histogram adalah bentuk grafik dari tabel distribusi frekuensi.

- Tabel: mudah untuk angka presisi
- Histogram: mudah untuk melihat bentuk distribusi

## Membuat Histogram dengan Python

```python
import matplotlib.pyplot as plt

scores = [45, 52, 58, 61, 63, 67, 70, 72, 75, 78, 80, 82, 85, 88, 92]

plt.hist(scores, bins=[40, 50, 60, 70, 80, 90, 100], edgecolor="black")
plt.title("Histogram of Test Scores")
plt.xlabel("Score")
plt.ylabel("Frequency")
plt.show()
```

## Cara Membaca Histogram

1. Di rentang mana data paling banyak
2. Seberapa lebar sebaran data
3. Apakah ada nilai ekstrem
4. Apakah puncaknya satu atau lebih

## Contoh Pemakaian di Bisnis

- Distribusi nilai belanja pelanggan
- Distribusi waktu penanganan tiket
- Distribusi nilai ujian/pelatihan

## Hal yang Tidak Terlihat dari Rata-rata Saja

Dua kelompok bisa punya rata-rata sama, tetapi struktur datanya berbeda.
Karena itu, analisis harus melihat distribusi, bukan hanya rata-rata.

## Ringkasan

- Tabel frekuensi menghitung data per rentang
- Histogram memvisualisasikan tabel frekuensi
- Frekuensi adalah jumlah data pada suatu kelas
- Lebar kelas memengaruhi keterbacaan tren
- Histogram membantu melihat konsentrasi dan sebaran
- Dalam bisnis, berguna untuk analisis penjualan, perilaku pelanggan, dan waktu proses

Bab berikutnya: scatter plot dan korelasi.
