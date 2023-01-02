<h2 align=center><u>Implementasi Bit Plane Slicing Pada Octave</u></h2>

### Apa itu Bit Plane Slicing?

Secara digital, sebuah gambar direpresentasikan dalam bentuk piksel. Piksel ini dapat diekspresikan lebih lanjut dalam bentuk bit. Perhatikan gambar di bawah ini :


Format biner untuk nilai tersebut adalah (representasi 8-bit).


Format biner untuk nilai piksel 167 adalah 10100111 Demikian pula, untuk 144 adalah 10010000. Gambar 8-bit ini terdiri dari delapan bidang 1-bit. Plane 1 berisi bit urutan terendah dari semua piksel dalam gambar.


Dan plane 8 berisi bit urutan tertinggi dari semua piksel dalam gambar.


Mari kita lihat bagaimana kita bisa melakukannya dengan menggunakan MATLAB

```oktave

A = [ 167 133 111
      144 140 135
      159 154 148 ]

B = bitget(A,1); %Bit urutan terendah dari semua piksel
'bitget' adalah fungsi MATLAB yang digunakan untuk mengambil bit 
dari posisi yang ditentukan dari semua piksel.

B = [ 1 1 1
      0 0 1
      1 0 0 ]

B = bitget(A,8); %Bit urutan tertinggi dari semua piksel

B = [ 1 1 0
      1 1 1 
      1 1 1 ]
      
```

<h2 align=center><u>Steganography</u></h2>

### Apa itu Steganography?

Steganografi atau Steganography adalah sebuah ilmu, teknik atau seni menyembunyikan sebuah pesan rahasia dengan suatu cara sehingga pesan tersebut hanya akan diketahui oleh si pengirim dan si penerima pesan rahasia tersebut. Steganografi berasal dari Bahasa Yunani yaitu Stegano yang berarti “tersembunyi atau menyembunyikan” dan graphy yang berarti “Tulisan, jadi Steganografi adalah tulisan atau pesan yang disembunyikan. Steganografi kebalikannya kriptografi yang menyamarkan arti dari sebuah pesan rahasia saja, tetapi tidak menyembunyikan bahwa ada sebuah pesan. Kelebihan Steganografi dibandingkan dengan Kriptografi adalah pesan-pesannya akan dibuat tidak menarik perhatian dan tidak menimbulkan kecurigaan, berbeda dengan Kriptografi yang pesannya tidak disembunyikan, walaupun pesannya sulit untuk di pecahkan akan tetapi itu akan menimbulkan kecurigaan pesan tersebut.

Pesan rahasia yang akan disembunyikan akan disisipkan pada suatu media penampung seperti citra, suara, video dan sebagainya yang terlihat tidak mencurigakan untuk menyimpan pesan rahasia. Pesan rahasia akan memerlukan sebuah kunci rahasia yang dinamakan stego-key agar hanyak pihak yang berhak saja yang dapat membuka atau mengekstak pesan rasahia tersebut.
