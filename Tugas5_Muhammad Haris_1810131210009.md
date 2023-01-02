# Membuat Pseudo Code dari pola Patterning, Ditthering, Bit Plane Slacing, dan Histogram Equalization
## **Pseudo Code Pathering**
Untuk Pathering, Berdasarkan analisis yang saya lakukan, didapatkan lah algoritmanya seperti berikut
### *Citra Digital Grayscale*

Disini saya menggunakan pseudo code untuk program PYTHON

```python
print("""Disini saya menggunakan citra yang berukuran 3 x 3, sehingga untuk banyaknya level/banyak pola 
adalah 10 pola yang didapatkan dari 3 x 3 + 1 = 10, adapun algoritmanya seperti berikut""")

print("""Dari 256 level warna, akan dibagi untuk menjadi 10 pola, sehingga 256/10 = 25,6 yang
dibulatkan menjadi 26 dan didapatkanlah pada masing-masing pola terdapat 26 panjang rentangan.""")

print("Pola ke-1 didapat dari rentang 0-25")
pola_1 = [[0,0,0], [0,0,0], [0,0,0]]

print("Pola 2 didapat dari rentang 26-51")
pola_2 = [[0,0,0], [0,0,0], [0,0,1]]

print("Pola ke-3 didapat dari rentang 52-77")
pola_3 = [[1,0,0], [0,0,0], [0,0,1]]

print("Pola ke-4 didapat dari rentang 78-103")
pola_4 = [[1,0,1], [0,0,0], [0,0,1]]

print("Pola ke-5 didapat dari rentang 104-129")
pola_5 = [[1,0,1], [0,0,0], [1,0,1]]

print("Pola ke-6 didapat dari rentang 130-155")
pola_6 = [[1,0,1], [0,0,0], [1,1,1]]

print("Pola ke-7 didapat dari rentang 156-181")
pola_7 = [[1,0,1], [1,0,0], [1,1,1]]

print("Pola ke-8 didapat dari rentang 182-207")
pola_8 = [[1,0,1], [1,0,1], [1,1,1]]

print("Pola ke-9 didapat dari rentang 208-233")
pola_9 = [[1,1,1], [1,0,1], [1,1,1]]

print("Pola ke-10 didapat dari rentang 234-259")
pola_10 = [[1,1,1], [1,1,1], [1,1,1]]

gambar = []

for(x = 1; x < gambar.length; x++):
    for(y = 1; y < gambar.length; y++):
        if(gambar[x,y] >=0 and gambar[x,y] <= 25):
            gambar[x,y] = pola_1
        elif(gambar[x,y] >=26 and gambar[x,y] <= 51):
            gambar[x,y] = pola_2
        elif(gambar[x,y] >=52 and gambar[x,y] <= 77):
            gambar[x,y] = pola_3
        elif(gambar[x,y] >=78 and gambar[x,y] <= 103):
            gambar[x,y] = pola_4
        elif(gambar[x,y] >=104 and gambar[x,y] <= 129):
            gambar[x,y] = pola_5
        elif(gambar[x,y] >=130 and gambar[x,y] <= 155):
            gambar[x,y] = pola_6
        elif(gambar[x,y] >=156 and gambar[x,y] <= 181):
            gambar[x,y] = pola_7
        elif(gambar[x,y] >=182 and gambar[x,y] <= 207):
            gambar[x,y] = pola_8
        elif(gambar[x,y] >=208 and gambar[x,y] <= 233):
            gambar[x,y] = pola_9
        elif(gambar[x,y] >=234 and gambar[x,y] <= 259):
            gambar[x,y] = pola_10
        else:
            print('level warna tidak ada')
            
print(gambar)
```


### **Pseudo Code Dithering**
Untuk Dithering, Berdasarkan analisis yang saya lakukan, didapatkan lah algooritmanya seperti berikut

```javascript
    Trashold = [100 150 ; 200 50]

    for(x = 1; x < gambar.length; i++){
        if(x%2 == 1){
            for(y = 1; y < gambar.length; y++){
                if(y%2 == 1){
                    if(gambar[x,y] >= Trashold[1,1]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
                else{
                    if(gambar[x,y] >= Trashold[1,2]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
            }
        }
        else{
            for(y = 1; y < gambar.length; y++){
                if(y%2 == 1){
                    if(gambar[x,y] >= Trashold[2,1]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
                else{
                    if(gambar[x,y] >= Trashold[2,2]){
                        gambar[x,y] = 1;
                    }
                    else{
                        gambar[x,y] = 0;
                    }
                }
            }
        }
    }
```

### **Bit Plane Slacing**

Untuk Bit Plane Slacing, Berdasarkan analisis yang saya lakukan, didapatkan lah algoritmanya seperti berikut

```Java
for (int i = 0; i < x.length ; i++){
    if(x[i] >= 128){
        int biner = x[i] - 128;
        if(biner >= 64){
            biner -= 64;
            if(biner >= 32){
                biner -= 32;
                if(biner >= 16){
                    biner -= 16;
                    if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11111111;
                                }else{
                                    x[i] = 11111110;
                                }
                            }else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11111101;
                            }
                            }else{
                            x[i] = 11111100;
                                    }
                                }
                                else if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11111011;
                                    }
                                    else{
                                        x[i] = 11111010;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11111001;
                                }
                                else{
                                    x[i] = 11111000;
                                }
                            }
                            else if(biner >= 4){
                                    biner -= 4;
                                    if(biner >= 2){
                                        biner -= 2;
                                        if(biner >= 1){
                                            biner -= 1;
                                            x[i] = 11110111;
                                        }
                                        else{
                                            x[i] = 11110110;
                                        }
                                    }
                                    else if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11110101;
                                    }
                                    else{
                                        x[i] = 11110100;
                                    }
                                }
                            else if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11110011;
                                }
                                else{
                                    x[i] = 11110010;
                                }
                                }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11110001;
                            }
                            else{
                                x[i] = 11110000;
                            }
                        }
                        else if(biner >= 8){
                            biner -= 8;
                            if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11101111;
                                    }
                                    else{
                                        x[i] = 11101110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11101101;
                                }
                                else{
                                    x[i] = 11101100;
                                }
                            }
                            else if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11101011;
                                }
                                else{
                                    x[i] = 11101010;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11101001;
                            }
                            else{
                                x[i] = 11101000;
                            }
                        }
                        else if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11100111;
                                    }
                                    else{
                                        x[i] = 11100110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11100101;
                                }
                                else{
                                    x[i] = 11100100;
                                }
                            }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 11100011;
                            }
                            else{
                                x[i] = 11100010;
                            }
                            }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 11100001;
                        }
                        else{
                            x[i] = 11100000;
                        }
                    }
                    else if(biner >= 16){
                        biner -= 16;
                        if(biner >= 8){
                            biner -= 8;
                            if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11011111;
                                    }
                                    else{
                                        x[i] = 11011110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11011101;
                                }
                                else{
                                    x[i] = 11011100;
                                }
                            }
                            else if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11011011;
                                }
                                else{
                                    x[i] = 11011010;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11011001;
                            }
                            else{
                                x[i] = 11011000;
                            }
                        }
                        else if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 11010111;
                                    }
                                    else{
                                        x[i] = 11010110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11010101;
                                }
                                else{
                                    x[i] = 11010100;
                                }
                            }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 11010011;
                            }
                            else{
                                x[i] = 11010010;
                            }
                            }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 11010001;
                        }
                        else{
                            x[i] = 11010000;
                        }
                    }
                    else if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11001111;
                                }
                                else{
                                    x[i] = 11001110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11001101;
                            }
                            else{
                                x[i] = 11001100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 11001011;
                            }
                            else{
                                x[i] = 11001010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 11001001;
                        }
                        else{
                            x[i] = 11001000;
                        }
                    }
                    else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 11000111;
                                }
                                else{
                                    x[i] = 11000110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 11000101;
                            }
                            else{
                                x[i] = 11000100;
                            }
                        }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 11000011;
                        }
                        else{
                            x[i] = 11000010;
                        }
                        }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 11000001;
                    }
                    else{
                        x[i] = 11000000;
                    }	
                }
                else if(biner >= 32){
                    biner -= 32;
                    if(biner >= 16){
                        biner -= 16;
                        if(biner >= 8){
                            biner -= 8;
                            if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 10111111;
                                    }
                                    else{
                                        x[i] = 10111110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10111101;
                                }
                                else{
                                    x[i] = 10111100;
                                }
                            }
                            else if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10111011;
                                }
                                else{
                                    x[i] = 10111010;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 10111001;
                            }
                            else{
                                x[i] = 10111000;
                            }
                        }
                        else if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 10110111;
                                    }
                                    else{
                                        x[i] = 10110110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10110101;
                                }
                                else{
                                    x[i] = 10110100;
                                }
                            }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 10110011;
                            }
                            else{
                                x[i] = 10110010;
                            }
                            }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 10110001;
                        }
                        else{
                            x[i] = 10110000;
                        }
                    }
                    else if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10101111;
                                }
                                else{
                                    x[i] = 10101110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 10101101;
                            }
                            else{
                                x[i] = 10101100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 10101011;
                            }
                            else{
                                x[i] = 10101010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 10101001;
                        }
                        else{
                            x[i] = 10101000;
                        }
                    }
                    else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10100111;
                                }
                                else{
                                    x[i] = 10100110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 10100101;
                            }
                            else{
                                x[i] = 10100100;
                            }
                        }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 10100011;
                        }
                        else{
                            x[i] = 10100010;
                        }
                        }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 10110001;
                    }
                    else{
                        x[i] = 10110000;
                    }
                }
                else if(biner >= 16){
                    biner -= 16;
                    if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10011111;
                                }
                                else{
                                    x[i] = 10011110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 10011101;
                            }
                            else{
                                x[i] = 10011100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 10011011;
                            }
                            else{
                                x[i] = 10011010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 10011001;
                        }
                        else{
                            x[i] = 10011000;
                        }
                    }
                    else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 10010111;
                                }
                                else{
                                    x[i] = 10010110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 10010101;
                            }
                            else{
                                x[i] = 10010100;
                            }
                        }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 10010011;
                        }
                        else{
                            x[i] = 10010010;
                        }
                        }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 10010001;
                    }
                    else{
                        x[i] = 10010000;
                    }
                }
                else if(biner >= 8){
                    biner -= 8;
                    if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 10001111;
                            }
                            else{
                                x[i] = 10001110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 10001101;
                        }
                        else{
                            x[i] = 10001100;
                        }
                    }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 10001011;
                        }
                        else{
                            x[i] = 10001010;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 10001001;
                    }
                    else{
                        x[i] = 10001000;
                    }
                }
                else if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 10000111;
                            }
                            else{
                                x[i] = 10000110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 10000101;
                        }
                        else{
                            x[i] = 10000100;
                        }
                    }
                else if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 10000011;
                    }
                    else{
                        x[i] = 10000010;
                    }
                    }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 10000001;
                }
                else{
                    x[i] = 10000000;
                }	
            }
            else if(x[i] >= 64){
                int biner = x[i] - 64;
                if(biner >= 32){
                    biner -= 32;
                    if(biner >= 16){
                        biner -= 16;
                        if(biner >= 8){
                            biner -= 8;
                            if(biner >= 4){
                                biner -= 4;
                                if(biner >= 2){
                                    biner -= 2;
                                    if(biner >= 1){
                                        biner -= 1;
                                        x[i] = 01111111;
                                    }
                                    else{
                                        x[i] = 01111110;
                                    }
                                }
                                else if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01111101;
                                }
                                else{
                                    x[i] = 01111100;
                                }
                            }
                            else if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01111011;
                                }
                                else{
                                    x[i] = 01111010;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 01111001;
                            }
                            else{
                                x[i] = 01111000;
                            }
                        }
                        else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01110111;
                                }
                                else{
                                    x[i] = 01110110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 01110101;
                            }
                            else{
                                x[i] = 01110100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01110011;
                            }
                            else{
                                x[i] = 01110010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01110001;
                        }
                        else{
                            x[i] = 01110000;
                        }
                    }
                    else if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01101111;
                                }
                                else{
                                    x[i] = 01101110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 01101101;
                            }
                            else{
                                x[i] = 01101100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01101011;
                            }
                            else{
                                x[i] = 01101010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01101001;
                        }
                        else{
                            x[i] = 01101000;
                        }
                    }
                    else if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01100111;
                            }
                            else{
                                x[i] = 01100110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01100101;
                        }
                        else{
                            x[i] = 01100100;
                        }
                    }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 01100011;
                        }
                        else{
                            x[i] = 01100010;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 01110001;
                    }
                    else{
                        x[i] = 01110000;
                    }
                }
                else if(biner >= 16){
                    biner -= 16;
                    if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01011111;
                                }
                                else{
                                    x[i] = 01011110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 01011101;
                            }
                            else{
                                x[i] = 01011100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01011011;
                            }
                            else{
                                x[i] = 01011010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01011001;
                        }
                        else{
                            x[i] = 01011000;
                        }
                    }
                    else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 01010111;
                                }
                                else{
                                    x[i] = 01010110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 01010101;
                            }
                            else{
                                x[i] = 01010100;
                            }
                        }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 01010011;
                        }
                        else{
                            x[i] = 01010010;
                        }
                        }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 01010001;
                    }
                    else{
                        x[i] = 01010000;
                    }
                }
                else if(biner >= 8){
                    biner -= 8;
                    if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01001111;
                            }
                            else{
                                x[i] = 01001110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01001101;
                        }
                        else{
                            x[i] = 01001100;
                        }
                    }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 01001011;
                        }
                        else{
                            x[i] = 01001010;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 01001001;
                    }
                    else{
                        x[i] = 01001000;
                    }
                }
                else if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 01000111;
                            }
                            else{
                                x[i] = 01000110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 01000101;
                        }
                        else{
                            x[i] = 01000100;
                        }
                    }
                else if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 01000011;
                    }
                    else{
                        x[i] = 01000010;
                    }
                    }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 01000001;
                }
                else{
                    x[i] = 01000000;
                }	
            }
            else if(x[i] >= 32){
                int biner = x[i] - 32;
                if(biner >= 16){
                    biner -= 16;
                    if(biner >= 8){
                        biner -= 8;
                        if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 00111111;
                                }
                                else{
                                    x[i] = 00111110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 00111101;
                            }
                            else{
                                x[i] = 00111100;
                            }
                        }
                        else if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 00111011;
                            }
                            else{
                                x[i] = 00111010;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 00111001;
                        }
                        else{
                            x[i] = 00111000;
                        }
                    }
                    else if(biner >= 4){
                            biner -= 4;
                            if(biner >= 2){
                                biner -= 2;
                                if(biner >= 1){
                                    biner -= 1;
                                    x[i] = 00110111;
                                }
                                else{
                                    x[i] = 00110110;
                                }
                            }
                            else if(biner >= 1){
                                biner -= 1;
                                x[i] = 00110101;
                            }
                            else{
                                x[i] = 00110100;
                            }
                        }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 00110011;
                        }
                        else{
                            x[i] = 00110010;
                        }
                        }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 00110001;
                    }
                    else{
                        x[i] = 00110000;
                    }
                }
                else if(biner >= 8){
                    biner -= 8;
                    if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 00101111;
                            }
                            else{
                                x[i] = 00101110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 00101101;
                        }
                        else{
                            x[i] = 00101100;
                        }
                    }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 00101011;
                        }
                        else{
                            x[i] = 00101010;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 00101001;
                    }
                    else{
                        x[i] = 00101000;
                    }
                }
                else if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 00100111;
                            }
                            else{
                                x[i] = 00100110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 00100101;
                        }
                        else{
                            x[i] = 00100100;
                        }
                    }
                else if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 00100011;
                    }
                    else{
                        x[i] = 00100010;
                    }
                    }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 00110001;
                }
                else{
                    x[i] = 00110000;
                }
            }
            else if(x[i] >= 16){
                int biner = x[i] - 16;
                if(biner >= 8){
                    biner -= 8;
                    if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 00011111;
                            }
                            else{
                                x[i] = 00011110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 00011101;
                        }
                        else{
                            x[i] = 00011100;
                        }
                    }
                    else if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 00011011;
                        }
                        else{
                            x[i] = 00011010;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 00011001;
                    }
                    else{
                        x[i] = 00011000;
                    }
                }
                else if(biner >= 4){
                        biner -= 4;
                        if(biner >= 2){
                            biner -= 2;
                            if(biner >= 1){
                                biner -= 1;
                                x[i] = 00010111;
                            }
                            else{
                                x[i] = 00010110;
                            }
                        }
                        else if(biner >= 1){
                            biner -= 1;
                            x[i] = 00010101;
                        }
                        else{
                            x[i] = 00010100;
                        }
                    }
                else if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 00010011;
                    }
                    else{
                        x[i] = 00010010;
                    }
                    }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 00010001;
                }
                else{
                    x[i] = 00010000;
                }
            }
            else if(x[i] >= 8){
                int biner = x[i] - 8;
                if(biner >= 4){
                    biner -= 4;
                    if(biner >= 2){
                        biner -= 2;
                        if(biner >= 1){
                            biner -= 1;
                            x[i] = 00001111;
                        }
                        else{
                            x[i] = 00001110;
                        }
                    }
                    else if(biner >= 1){
                        biner -= 1;
                        x[i] = 00001101;
                    }
                    else{
                        x[i] = 00001100;
                    }
                }
                else if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 00001011;
                    }
                    else{
                        x[i] = 00001010;
                    }
                }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 00001001;
                }
                else{
                    x[i] = 00001000;
                }
            }
            else if(x[i] >= 4){
                int biner = x[i] - 4;
                if(biner >= 2){
                    biner -= 2;
                    if(biner >= 1){
                        biner -= 1;
                        x[i] = 00000111;
                    }
                    else{
                        x[i] = 00000110;
                    }
                }
                else if(biner >= 1){
                    biner -= 1;
                    x[i] = 00000101;
                }
                else{
                    x[i] = 00000100;
                }
            }
            else if(x[i] >= 2){
                int biner = x[i] - 2;
                if(biner >= 1){
                    biner -= 1;
                    x[i] = 00000011;
                }
                else{
                    x[i] = 00000010;
                }
            }
            else if(x[i] >= 1){
                int biner = x[i] - 1;
                x[i] = 00000001;
            }
            else{
                x[i] = 00000000;
            }
        }
```


### Algoritma Patterning

Langkah-langkah
1. Siapkan matriks yang berisi angka, baik itu matriks 2 x 2, 3 x 3 atau yang lainnya. Tujuannya adalah untuk menentukan pola yang akan digunakan dari angka yang dikandungnya.
2. Tentukan matriks yang diperbesarnya, misal 3 x 3, berarti akan ada 10 jenis pola. Hal itu didapat dari 3 x 3 = 9 ditambah 1. Kemudian, untuk menentukan interval tiap-tiap pola, adalah dengan 10/255 = 26.

~ jadi, tiap satu pola memuat angka yang panjangnya 26 (Dimulai dari angka 0 sampai dengan 255)

~ untuk 4 x 4 yaitu -> 4 x 4 = 16 + 1 = 17. Tinggal menentukan interval untuk 17 pola, begitu juga 5 x 5 dan seterusnya.
3. Membuat pola yang pengambilan polanya ditentukan oleh matriks yang telah disiapkan di awal.

Kesimpulannya, matriks sebagai patokan, memasang pola dengan panjang interval sesuai dengan matriks yang diperbesarnya, lalu membuat pola dengan menyesuaikan angka dalam matriks dengan pola yang berisi interval.

### Algoritma Dithering

Langkah-langkah
1.Siapkan matriks satu yang berisi angka
2. Siapkan matriks dua yang akan menjadi bahan perbandingan dengan matriks sebelumnya
3. Apabila perbandingan tiap ordo yang selaras, matriks dua lebih kecil dari matriks satu, maka kotaknya akan berwarna hitam. Sebaliknya, apabila matriks dua lebih besar daripada matriks satu, maka kotaknya akan berwarna putih.

Kesimpulannya, harus ada matriks satu dan matriks dua yang akan dibandingkan. Matriks dua yang menjadi penentu warna hitam atau putih.

###  Penyetaraan Histogram Algoritma

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