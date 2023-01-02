 
# Menjelaskan tentang Method dan Grayscalle

<h2 align="center"><b> Grayscale </b></h2></p>

<p align="justify">Grayscale adalah model paling sederhana karena mendefinisikan warna hanya menggunakan satu komponen yaitu lightness. Jumlah kecerahan dijelaskan menggunakan nilai mulai dari 0 (hitam) hingga 255 (putih).</p>

<p align="justify">Di satu sisi, gambar skala abu-abu menyampaikan lebih sedikit informasi daripada RGB. Namun, mereka umum dalam pemrosesan gambar karena menggunakan gambar skala abu-abu membutuhkan lebih sedikit ruang yang tersedia dan lebih cepat, terutama ketika kita berurusan dengan perhitungan yang kompleks.</p>



<h2 align="center"><b> Convert RGB to Grayscale </b></h2></p>

> ## Ligthness Method
Dalam rumus

```matlab
grayscale = (min(R,G,B) - max (R,G,B)) / 2
```

<p align="justify">&nbsp &nbsp &nbsp &nbspMetode yang sangat sederhana adalah dengan mengambil nilai rata-rata yaitu menjumlahkan nilai tertinggi dan terendah. Kita dapat dengan mudah melihat bahwa metode ini menghadirkan kelemahan yang sangat serius karena satu komponen RGB tidak digunakan. Ini jelas merupakan masalah karena jumlah cahaya yang dilihat mata kita bergantung pada ketiga warna dasar. 

> ## Average Method

Dalam rumus

```matlab
grayscale = (R + G + B) / 3
```
  
<p align="justify">&nbsp &nbsp &nbsp &nbspCara lain adalah dengan mengambil nilai rata-rata dari ketiga komponen (merah, hijau, dan biru). Meskipun sekarang kita memperhitungkan semua komponen, metode rata-rata juga bermasalah karena memberikan bobot yang sama untuk setiap komponen. Berdasarkan penelitian tentang penglihatan manusia, kita tahu bahwa mata kita bereaksi terhadap setiap warna dengan cara yang berbeda. Secara khusus, mata kita lebih sensitif terhadap hijau, lalu merah, dan akhirnya biru. Oleh karena itu, bobot dalam persamaan di atas harus berubah.

> ## Luminosity Method

Dalam rumus

```matlab
grayscale = (0.3 * R) + (0.59 * G) + (0.11 * B) 
```

<p align="justify">&nbsp &nbsp &nbsp &nbspMetode terbaik adalah metode luminositas yang berhasil memecahkan masalah metode sebelumnya. Berdasarkan pengamatan di atas, kita harus mengambil rata-rata tertimbang dari komponen. Kontribusi warna biru pada nilai akhir harus berkurang, dan kontribusi warna hijau harus meningkat. Metode lightness cenderung mengurangi kontras. Metode luminositas bekerja paling baik secara keseluruhan dan merupakan metode default yang digunakan jika Anda meminta untuk mengubah gambar dari RGB ke skala abu-abu.
