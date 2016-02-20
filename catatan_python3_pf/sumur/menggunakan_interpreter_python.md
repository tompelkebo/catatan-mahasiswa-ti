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

## Encoding File Python















