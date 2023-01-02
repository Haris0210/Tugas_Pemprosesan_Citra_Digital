<h2 align=center><u>Steganography</u></h2>

### Apa itu Steganography?

Steganografi atau Steganography adalah sebuah ilmu, teknik atau seni menyembunyikan sebuah pesan rahasia dengan suatu cara sehingga pesan tersebut hanya akan diketahui oleh si pengirim dan si penerima pesan rahasia tersebut. Steganografi berasal dari Bahasa Yunani yaitu Stegano yang berarti “tersembunyi atau menyembunyikan” dan graphy yang berarti “Tulisan, jadi Steganografi adalah tulisan atau pesan yang disembunyikan. Steganografi kebalikannya kriptografi yang menyamarkan arti dari sebuah pesan rahasia saja, tetapi tidak menyembunyikan bahwa ada sebuah pesan. Kelebihan Steganografi dibandingkan dengan Kriptografi adalah pesan-pesannya akan dibuat tidak menarik perhatian dan tidak menimbulkan kecurigaan, berbeda dengan Kriptografi yang pesannya tidak disembunyikan, walaupun pesannya sulit untuk di pecahkan akan tetapi itu akan menimbulkan kecurigaan pesan tersebut.

Pesan rahasia yang akan disembunyikan akan disisipkan pada suatu media penampung seperti citra, suara, video dan sebagainya yang terlihat tidak mencurigakan untuk menyimpan pesan rahasia. Pesan rahasia akan memerlukan sebuah kunci rahasia yang dinamakan stego-key agar hanyak pihak yang berhak saja yang dapat membuka atau mengekstak pesan rasahia tersebut.

### Membuat Steganography di Citra dengan Octave

Kode program :
```octave
picture = imread("image.jpg");
gray = rgb2gray(picture);
[row,col] = size(picture);

pesan = "Haris Gin Mantap";
ascii = uint8(pesan);
biner = dec2bin(ascii,8);
biner2 = str2num(biner);

pesan2 = transpose(biner2);
pesan3 = pesan2(:);
hasil = transpose(pesan2);
panjang = length(hasil);
counter = 1;
steganography = gray;

for x = 1:row
for y = 1:col
	if (counter <= panjang)
		LSB = bitget(gray(x,y),1);
		biner3 = hasil(counter);
		temp = xor(LSB, biner3);
		steganography(x,y) = gray(x,y) + temp;
		counter = counter + 1;
	else
		break;
	endif
endfor
endfor

subplot(1,2,1); imshow(gray); title("Gambar Asli");
subplot(1,2,2); imshow(steganography, "image2.jpg"); title("Steganography");
```
