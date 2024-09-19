# Prediksi Pendapatan Terbesar pada Penjualan Produk Cat dengan Menggunakan Metode Monte Carlo

## Deskripsi Proyek
Proyek ini bertujuan untuk memprediksi pendapatan penjualan produk cat menggunakan Metode Monte Carlo. Metode ini digunakan untuk membantu toko bangunan dalam memprediksi penjualan produk cat yang diminati konsumen, sehingga stok cat dapat dikelola dengan lebih efektif. Dengan memanfaatkan metode Monte Carlo, kita dapat memodelkan berbagai skenario penjualan dan memperoleh prediksi yang lebih akurat untuk membantu meningkatkan pendapatan penjualan.

## Latar Belakang
Pemenuhan permintaan konsumen terhadap produk cat adalah tantangan yang harus dikelola dengan baik. Ketersediaan stok yang sesuai dengan permintaan memengaruhi pendapatan toko secara signifikan. Oleh karena itu, toko bangunan UD memerlukan sebuah sistem yang dapat memprediksi pendapatan penjualan untuk mengoptimalkan ketersediaan produk cat yang paling diminati.

## Metode yang Digunakan
Penelitian ini menggunakan **Metode Monte Carlo**, yang merupakan metode simulasi numerik dengan memanfaatkan bilangan acak. Metode ini digunakan untuk mengevaluasi model deterministik dan memprediksi nilai ekspektasi dari variabel acak. Beberapa kelebihan dari metode ini adalah:
- Dapat mengevaluasi pengaruh risiko.
- Mampu mengakomodasi berbagai jenis distribusi dalam variabel input.
- Pemodelan relatif sederhana dan mudah dikembangkan.
- Menyediakan pengukuran keakuratan hasil.

## Library yang Digunakan
- **NumPy**: Untuk perhitungan saintifik seperti statistik dan aljabar linier.
- **Pandas**: Untuk manipulasi dan analisis data.
- **Matplotlib**: Untuk visualisasi data dalam bentuk grafik 2D/3D.
- **SciPy.stats**: Untuk pemrosesan statistik, seperti distribusi probabilitas dan uji normalitas.
- **Random**: Untuk menghasilkan bilangan acak.

## Instalasi
1. Clone repository ini ke lokal:
   ```bash
   git clone https://github.com/RusdyZain/MonteCarlo.git
   ```
## Dataset
Data yang digunakan dalam proyek ini diambil dari file Excel `DataSet.xlsx`, yang berisi data penjualan produk cat dalam dua grup. Grup pertama berisi jumlah permintaan produk, dan grup kedua berisi jumlah stok yang tersedia. Dataset ini akan diakses dan diolah menggunakan Pandas.

### Cara Mengakses Dataset
```python
import pandas as pd
data = pd.read_excel('DataSet.xlsx', engine='openpyxl', header=None, usecols="A:B", skiprows=1)
group1 = np.array(data.iloc[:, 0], dtype=int)
group2 = np.array(data.iloc[:, 1], dtype=int)
```

## Langkah-Langkah Implementasi

### 1. Uji Normalisasi
Uji ini dilakukan untuk menentukan apakah data mengikuti distribusi normal. Jika data normal, kita dapat melanjutkan ke analisis selanjutnya.

```python
# Contoh kode uji normalisasi
from scipy.stats import norm
import pandas as pd

Norm = pd.DataFrame({"Data": demand_probability})
Norm["Rank"] = Norm["Data"].rank(method="min", ascending=True).astype(int)
Norm["Indeks"] = (Norm["Rank"] - 3 / 8) / (len(Norm) + 1 / 4)
Norm["Formula Z-Score"] = stats.norm.ppf(Norm["Indeks"], 0, 1)
Norm["PDF"] = stats.norm.pdf(Norm["Formula Z-Score"], loc=0, scale=1)
```

### 2. Uji Homogenitas
Uji ini dilakukan untuk melihat apakah variabilitas antara dua kelompok data homogen atau tidak.

```python
# Contoh kode uji homogenitas
def levene_test(group1, group2):
    ...
statistic, pvalue = levene_test(group1, group2)
```

### 3. Simulasi Monte Carlo
Simulasi ini digunakan untuk memprediksi pendapatan penjualan dengan metode Monte Carlo berdasarkan data permintaan dan stok cat.

```python
# Contoh kode simulasi Monte Carlo akan ditambahkan di bagian ini
```

## Hasil
Setelah menjalankan simulasi dan uji, hasil yang diperoleh adalah sebagai berikut:
- **Uji Normalisasi** menunjukkan bahwa data mengikuti distribusi normal.
- **Uji Homogenitas** menunjukkan bahwa data dari kedua grup bersifat homogen.
- Simulasi Monte Carlo memberikan prediksi yang dapat diandalkan untuk memperkirakan pendapatan penjualan produk cat.

## Visualisasi
Visualisasi data dilakukan menggunakan Matplotlib untuk membantu mempresentasikan hasil simulasi.

```python
import matplotlib.pyplot as plt
plt.scatter(Norm["Formula Z-Score"], Norm["PDF"])
plt.show()
```

## Kesimpulan
Dengan menggunakan metode Monte Carlo, kita dapat memprediksi pendapatan penjualan produk cat dengan lebih akurat. Ini memungkinkan toko untuk merencanakan persediaan produk cat yang sesuai dengan permintaan konsumen, sehingga meningkatkan pendapatan.
