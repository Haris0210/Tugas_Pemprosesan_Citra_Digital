## Algoritma Halftoning


## Histogram Equalization Algoritma

Kata Kunci
Pembuatan Histogram berhubungan dengan hasil perhitungan dari Grayscale Enhancement. Jadi, sebelum mencapai pembuatan histogram, kita harus menghitungnya terlebih dahulu.

Langkah-langkah
1. Menentukan gambar dan membagi total pixel. Misal, ada gambar 3 bit, maka gray levelnya adalah 8. Dan sebanyak 8 buah macam pula pixel-pixel yang dibuat atau keluar. Biasanya dua macam ini berasal dari pembuatan soal atau permasalahan awal, jadi kita hanya perlu melanjutkan ke langkah selanjutnya.
2. Yang kedua adalah menjumlah semua piksel dari awal hingga akhir.
3. Hasil akhir dari penjumlahan keseluruhan tersebut adalah penentu yang menjadi pembagi piksel masing-masing.
4. Kemudian mengalikan pixel yang dibagi berdasarkan jumlah keseluruhan pixel dengan banyaknya gray level satu demi satu, misal gray level ada 7, maka : (pixel / sumpixel)*gray level
5. Hasil dari perhitungan tersebut dibulatkan
6. Menghitung kembali hasil dari rumus di atas dengan memperhatikan tingkat keabuan dan jumlah piksel yang disediakan pada langkah pertama tadi. Jadi, ada tiga hal yang akan kita perhatikan, yaitu hasil akhir, tingkat keabuan dan no pixel --yang kemudian akan menghasilkan no pixel yang baru untuk pembuatan histogram.

Jika langkah-langkah di atas sudah selesai, kita tinggal memperhatikan pembuatan histogram. Hal yang harus diperhatikan adalah gray level dan no pixel, dan khusus no pixel ini diambil dari hasil perhitungan sebelumnya. Arah panah x mendatar adalah angka untuk gray level, sedangkan aray panah y tegak lurus merupakan angka no of pixel. Jadi, tinggi rendahnya titik histogram dapat ditentukan setelah kita menyelesaikan tugas di atas.

Kesimpulannya, pembuatan histogram harus menyelesaikan perhitungan peningkatan grayscale terlebih dahulu, lalu hasil akhir perhitungan tersebut yang menentukan tinggi atau banyaknya piksel pada tiap-tiap level.

##  Algoritma Bit Place Slicing

Algoritma ini berhubungan dengan biner, yang tujuannya adalah memotong bit / area warna grayscale pada sebuah gambar. Hal pertama yang harus kita ketahui adalah pemotongan daerah secara umum terlebih dahulu, yaitu :

~ 0 untuk angka yang tidak digunakan
~ 1 untuk angka yang digunakan

Dalam biner, ada 8 buah angka desimal, di antaranya :

128 | 64 | 32 | 16 | 8 | 4 | 2 | 1

Langkah-langkah
1. Pelajari cara merubah angka desimal menjadi angka biner
2.Siapkan matriks yang berisi angka
3. Lihat angkanya lalu ubah ke dalam bentuk biner

Contoh

| 64 59 |

| 77 123 |

<br>

Mengiris Tempat Bit

| 01000000 00111011 |

| 01001101 01111011 |

Kesimpulannya, algoritma ini merupakan metode kontribusi atau pengaruh tiap bit penyusun citra, tujuannya adalah merubah angka desimal menjadi angka biner.
