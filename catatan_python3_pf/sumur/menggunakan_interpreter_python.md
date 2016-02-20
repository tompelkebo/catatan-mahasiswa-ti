# Menggunakan Interpreter Python


##  Interpreter Python

Interpreter Python biasanya terinstal di `/usr/local/bin/python3.4`. dengan menempatkan Interactive Python di path `/usr/local/bin` kita dapat memanggil Interpreter secara langsung melalui terminal dengan mengetik:

```
python3.4
```

kita juga dapat menempatkan interpreter Python dimanapun selama sesi instalasi. tapi dianjurkan untuk menggunakan direktori yang sudah umum digunakan oleh Python saat melakukan instalasi (default directory).

Untuk mengakhiri modus interaktif tekan tombol `Control-D` atau `Control-Z` di keyboard. jika cara tersebut tidak bekerja, ketik perintah `quit()` pada shell.

Untuk mendapatkan histori dari perintah yang kita ketik, tekan  `Control-P` ke prompt Python. untuk menghapus perintah, kita bisa menggunakan tombol `backspace` di keyboard.

Kita juga bisa mengeksekusi sebuah pernyataan atau statement langsung di sebuah shell tanpa masuk ke modus interaktif atau tanpa perlu membuat file dan mengeksekusinya. untuk melakukan hal ini, kita bisa menggunakan perintah seperti:

```
python -c perintah [arg] ...,
```

sebagai contoh:


```python
$ python -c "print('Halo Python Indonesia')"
Halo Python Indonesia
$
```

Terkadang setelah kita mengeksekusi file Python, kita ingin masuk ke modus interaktif secara otomatis. Untuk melakukan hal ini kita bisa menggunakan perintah:

```
$ python -i test.py
Halo Python Indonesia
>>>
```

## Pengkodean File Sumber Python

Secara default, file sumber Python dikodekan dalam UTF-8. Dengan pengkodean ini, karakter dari sebagian besar bahasa di dunia dapat digunakan sebagai `string literal`, `identifier` dan `komentar`, meskipun pada nyatanya pustaka standar Python menggunakan karakter `ASCII` untuk `identifier`. Untuk menampilkan karakter-karakter UTF-8, editor yang kita gunakan harus diatur untuk UTF-8 dan ini juga harus menggunakan font-font yang mendukung semua karakter tersebut.

Kita juga bisa menentukan format pengkodean yang berbeda dari sebuah file sumber Python. Untuk dapat melakukannya, tempatkan satu baris komentar diikuti nama pengkodean untuk file sumber, setelah komentar istimewa (`#!`) Perhatikan format berikut ini:

```Python
# -*- coding: encoding -*-
```

Misalnya, jika editor kita tidak mendukung pengkodean `UTF-8` dan kita ingin menggunakan beberapa jenis pengkodean lain (`Windows 1252`), kita dapat menulisnya seperti:
 
```Python
# -*- coding: cp-1252 -*-
```











