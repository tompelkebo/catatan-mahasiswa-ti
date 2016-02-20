# Pengantar Python

Dalam materi ini, input dan output dibedakan dengan ada atau tidaknya sebuah tanda atau simbol (`>>>` dan `...`). Tanda `>>>` adalah sebuah `prompt` pertama yang muncul di `interactive shell python`. Kita bisa menulis perintah apapun setelah tanda tersebut. Baris output diberi tanda tanpa adanya simbol `>>>` dan `...`. Tanda `...` merupakan `prompt` kedua dimana tanda ini digunakan untuk mengetik perintah dalam banyak baris. 

```Python
>>> if 2 != 1:
...     print("2 tidak sama dengan 1")
... 
2 tidak sama dengan 1
```


## Komentar Di Python

Komentar di Python dimulai dengan karakter hash (`#`). Apapun yang kita ketik setelah tanda ini, dianggap sebagai komentar dan tidak akan dieksekusi oleh Python. 

```Python
>>> # ini adalah komentar pertama
... data = 30 # data bernilai 30
>>> text = "# Ini bukan komentar, karena di dahului oleh \"\""
>>> data, text
(30, '# Ini bukan komentar, karena tidak di dahului oleh ""'
```


## Jenis Data di Python

Saatnya kita belajar tentang jenis-jenis data di Python dengan memanfaatkan `Python Interactive Shell`. Buka terminal dengan menekan tombol `Control-T` secara bersamaan, ketik perintah di bawah ini untuk masuk ke modus interaktif:

```
$ python3
```

### Number

Kita dapat mengetik ekspresi Angka (`Number`) ke dalam interaktif Python. kita juga bisa menggunakan operator aritmatika seperti `+`, `-`, `*` dan `/` serta `%`. Cara kerja dari operator ini pun sama seperti di bahasa lainnya. Tanda kurung (`()`) bisa digunakan untuk mengelompokan operasi mana yang harus didahulukan (`precedence`). Mari kita coba:

```Python
>>> 10 + 7
17
>>> 10 / 2
5.0
>>> 10 * 2
20
>>> 10 - 2
8
>>> 10 % 3
1
>>> a, b = 56, 32
>>> c = a - b
>>> c
24
>>> 2 + 3 * 4
14
>>> (2 + 3) * 4
20
```

Perhatikan pada bagian `pembagian`. Jenis nilai dari hasil operasi pembagian di `Python 3` adalah `float`.  Jika kita ingin membulatkan nilai dari hasil pembagian tersebut ke pembulatan ke bawah dan menghasilkan jenis nilai menjadi `integer`, kita bisa menggunakan operator `//`.

```Python
>>> 10 // 2
5
>>> 11 // 4
2
```

Dengan Python, kita bisa melakukan operasi perpangkatan dengan menggunakan operator `**`. 


```Python
>>> 2 ** 3 # 2 dipangkatkan dengan 3
8
```

Tanda sama dengan (`=`) digunakan untuk menugaskan nilai ke dalam variabel. 

```Python
>>> lebar = 10
>>> tinggi = 20
>>> luas = lebar * tinggi
>>> luas
200
```

Jika kita mengakses variabel yang belum dideklarasikan (belum ditugaskan nilai ke dalamnya) akan terjadi kesalahan. Perhatikan pada contoh berikut ini dimana kita mengakses variabel `nama` yang belum dideklarasikan.

```Python
>>> nama # mengakses variabel 'nama'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'nama' is not defined
```  

Dalam modus interaktif, ekspresi yang ditulis sebelumnya akan ditugaskan ke dalam variabel `underscore` (`_`). hal ini akan mempermudah untuk melanjutkan perhitungan di perintah selanjutnya.

```Python
>>> ppn = 10.5 / 100
>>> harga = 99.9
>>> harga * ppn
10.4895
>>> harga + _
110.3895
>>> print("IDR.",round(_, 2))
IDR. 110.39
```

Selain `int` dan `float`, Python juga mendukung beberapa jenis `Number` lain seperti `Decimal` dan `Fraction`. Python juga mendukung `complex number` dimana jenis ini menggunakan simbol `j` atau `J` sebagai akhiran untuk menunjukan bagian imajiner (misalnya `3 + 5j`).







 