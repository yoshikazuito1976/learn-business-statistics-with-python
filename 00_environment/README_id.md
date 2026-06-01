# 00_environment

## Bahasa Indonesia

Pada bab ini, Anda memeriksa lingkungan belajar yang diperlukan untuk materi ini.

Tujuannya bukan melakukan konfigurasi yang rumit.
Tujuannya adalah memastikan Anda siap mengolah data dengan Python dan spreadsheet.

---

## Tujuan Bab

Pada bab ini, Anda memastikan bahwa:

- Python bisa dijalankan
- Alat spreadsheet bisa digunakan
- Hasil perhitungan sederhana bisa ditampilkan
- Bilangan acak bisa dibuat
- Grafik bisa ditampilkan

---

## Alat yang Digunakan

Materi ini terutama menggunakan:

- Python
- Google Colab atau Jupyter Notebook
- Excel atau Google Sheets
- matplotlib (jika diperlukan)
- pandas (jika diperlukan)

Anda tidak perlu langsung menguasai semuanya.
Fokus awalnya adalah memastikan semuanya berjalan.

---

## Pemeriksaan minimum

### 1. Cek eksekusi Python

```python
print("Hello, Business Statistics")
```

```text
Hello, Business Statistics
```

### 2. Cek perhitungan sederhana

```python
price = 1000
tax_rate = 0.1

total = price + price * tax_rate

print(total)
```

### 3. Cek bilangan acak

```python
import random

number = random.random()
print(number)
```

`random.random()` mengembalikan nilai 0 atau lebih, tetapi kurang dari 1.

### 4. Cek tampilan grafik

```python
import matplotlib.pyplot as plt

values = [1, 2, 3, 4, 5]
counts = [2, 4, 6, 8, 10]

plt.bar(values, counts)
plt.show()
```

---

## Pemeriksaan spreadsheet

Di Excel atau Google Sheets, pastikan operasi dasar berikut bisa dilakukan:

- Membuat tabel
- Menghitung jumlah data
- Membuat grafik

Python dan spreadsheet sama-sama alat untuk mengamati data.

---

## Pemeriksaan lingkungan di AlmaLinux

Jika menggunakan AlmaLinux, jalankan perintah berikut:

```bash
python3 -V
sudo dnf install python3-pip
python3 -m pip --version
python3 -m pip install --user ipykernel
python3 -m ipykernel install --user --name python3 --display-name "Python 3"
```

- `python3 -V`: memeriksa versi Python
- `python3 -m pip --version`: memastikan pip tersedia
- Instal `ipykernel` agar kernel `Python 3` dapat dipakai di Jupyter

---

## Ringkasan

Pada bab ini, Anda memeriksa lingkungan belajar statistik bisnis.

Pada bab berikutnya, Anda mulai mempelajari probabilitas dan percobaan.
