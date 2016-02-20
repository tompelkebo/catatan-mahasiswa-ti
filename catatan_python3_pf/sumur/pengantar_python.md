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

**Perhatikan !** : Karena `**` memiliki hak lebih tinggi dari `-`, maka `-3 ** 2` akan ditafsirkan sebagai `-(3 ** 2)` dan dengan demikian hasilnya adalah `-9`. Untuk menghindari hal ini dan mendapatkan nilai `9`, kita dapat menggunakan `(-3) ** 2`.

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

Dalam modus interaktif, hasil dari ekspresi yang ditulis sebelumnya akan ditugaskan ke dalam variabel `underscore` (`_`). hal ini akan mempermudah untuk melanjutkan perhitungan pada perintah selanjutnya.

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


### String

Selain `Number`, Python juga bisa digunakan untuk memanipulasi `string` yang dapat dinyatakan dalam beberapa cara. Cara pertama yaitu dengan menggunakan tanda kutip tunggal atau single-quotes (`'...'`) dan cara kedua yaitu dengan menggunakan tanda kutip ganda atau double-quotes (`"..."`). Tanda `\` digunakan untuk `escape quotes` atau meluluskan karakter khusus ke dalam `string`.

```Python
>>> 'mari kita solat' # penggunaan single-quotes
'mari kita solat'
>>> 'solat jum\'at wajib buat lelaki' # tanda \' untuk meluluskan karakter '"solat jum'at wajib buat lelaki"
>>> "solat jum'at wajib buat lelaki" # menggunakan double-quotes sebagai gantinya
"solat jum'at wajib buat lelaki"
>>> '"Oke", gue setuju !'
'"Oke", gue setuju !'
>>> "\"Oke\", gue setuju !"
'"Oke", gue setuju !'
>>> '"Jum\'at" barokah sob..'
'"Jum\'at" barokah sob..'
```

fungsi `print()` digunakan untuk mencetak data agar lebih mudah dibaca pada layar. Fungsi ini akan menghilangkan tanda kutip dan dapat mencetak karakter escape dalam bentuk sebenarnya serta dapat mencetak karakter khusus (seperti newline `\n`). Perhatikan contoh berikut ini:

```Python
>>> print('"Jum\'at" barokah sob..')
"Jum'at" barokah sob..
>>> s = 'Baris pertama.\nBaris kedua'
>>> # tanpa print
... s
'Baris pertama.\nBaris kedua'
>>> # dengan print
... print(s)
Baris pertama.
Baris kedua
```

Jika kita tidak menginginkan karakter yang di dahului dengan tanda `\` ditafsirkan sebagai karakter khusus, kita dapat menggunakan `raw string` dengan menambahkan `r` sebelum quote pertama:

```Python
>>> print('C:\doc\nina') # tanpa 'r' \n akan menjadi baris baru
C:\doc
ina
>>> print(r'C:\doc\nina') # dengan 'r' \n tidak menjadi baris baru
C:\doc\nina
```
String literal bisa ditulis dengan beberapa baris (multiline). Untuk menggunakannya, kita bisa menggunakan `triple-quotes` (`"""..."""` atau `'''...'''`). Setiap kita menekan `enter` maka akhir baris secara otomatis akan ditambahkan dalam string tersebut. Namun untuk mencegah akhir baris saat kita menekan `enter`, kita bisa menggunakan karakter `\` di akhir baris. Perhatikan contoh berikut:

```Python
>>> print("""\
... Dear, Neng Ijeh....              Jakarte, 25/Januari/2016
...     
...     Abang kangen deh sama eneng. Abang pengen main kerumah
...     tapi apa daya... gojek langganan abang lagi nganter
...     langganannya.
... """)

```
Hasil yang diperoleh:

```
Dear, Neng Ijeh....              Jakarte, 25/Januari/2016
    
    Abang kangen deh sama eneng. Abang pengen main kerumah
    tapi apa daya... gojek langganan abang lagi nganter
    langganannya.
```

String juga dapat digabungkan (direkatkan) dengan operator `+` dan String juga dapat di duplikasi (diulang) dengan operator `*`. Perhatikan contoh berikut:

```Python
>>> # penggabungan string
... "sir gobang go" + " sir sir"
'sir gobang go sir sir'
>>> # perulangan string
... "sir gobang go" + " sir" * 2
'sir gobang go sir sir'

```

Duat atau lebih string literal yang berada di samping satu sama lainnya (sejajar) secara otomatis akan merekat tanpa menggunakan operator `+`.

```Python
>>> "i " "Love " 'You , ' 'Eneng Ijeh'
'i Love You , Eneng Ijeh'
```

Perekatan string literal otomatis, hanya bekerja dengan cara di atas. Perekatan string literal otomatis, tidak bekerja di dalam variabel atau ekspresi. Perhatikan contoh di bawah ini:

```Python
>>> lirik = "sir gobang go "
>>> lirik " sir sir"
  File "<stdin>", line 1
    lirik " sir sir"
                   ^
SyntaxError: invalid syntax
>>> lirik (" sir" * 2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object is not callable
>>> 'sir gobang go ' (" sir" * 2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object is not callable
``` 

Jadi untuk merekatkan string tersebut, kita bisa menggunakan operator `+`. 

```Python
>>> lirik + " sir sir"
'sir gobang go  sir sir'
>>> 'sir gobang go ' + (" sir" * 2)
'sir gobang go  sir sir'
```

Terdapat fitur lain yang sangat berguna ketika kita ingin mematahkan string panjang untuk dicetak ke layar dengan fungsi `print()`. Perhatikan contoh berikut:

```Python
>>> text = ('Masukan beberapa string dalam tanda kurung '
...         'Untuk merekatkan mereka bersama-sama ' 
...         'Menjadi satu kalimat utuh')
>>> text
'Masukan beberapa string dalam tanda kurung Untuk merekatkan mereka bersama-sama Menjadi satu kalimat utuh'
```

String juga dapat diindeks (subscript). Karakter pertama dari string memiliki indeks ke `0`. Tidak ada jenis karakter yang terpisah, karakter hanyalah sebuah string dalam satuan karakter:

```Python
>>> kata = 'Indonesia'
>>> kata[0]
'I'
>>> kata[5]
'e'
```

Indeks string juga bisa menjadi angka negatif. Indeks string dengan angka negatif selalu dimulai dari `-1` dan perhitungannya dimulai dari kanan.


```Python
>>> kata[-1] # karakter terakhir
'a'
>>> kata[-2] # karakter terakhir kedua
'i'
>>> kata[-6]
'o'
>>> 
```

Python juga mendukung pengirisan string. Intinya, pengindeks-an dilakukan untuk mendapatkan karakter individu sedangkan pengirisan memungkinkan kita mendapatkan bagian tertentu dari string (`substring`). 

```Python
>>> kata[:5]
'Indon'
>>> kata[5:]
'esia'
>>> kata[:5] + kata[5:]
'Indonesia'
>>> kata[:6] + kata[6:]
'Indonesia'
```

Untuk memperjelas pemahaman tentang pengirisan string, kita bisa menggunakan bentuk sintak seperti berikut ini:

```Python
kata[x:y]
x -> posisi index bagian pertama
y -> posisi index bagian kedua
```

Jika `x` dalam pengirisan dihilangkan, nilainya menjadi `0` (default) dan diakses hingga ukuran string yang diiris yaitu nilai `y` (misalnya `[:4]`). Jika `y` dalam pengirisan dihilangkan, nilainya menjadi `0` (default) dan dari indeks ke `x` sampai akhir (misalnya `[4:]`).

Salah satu cara untuk memahami bagaimana sebuah irisan bekerja adalah memikirkan indeks sebagai petunjuk antara karakter di dalam string. Tepi kiri pertama bernilai `0`, tepi kiri kanan pertama bernilai `-1` dan string memiliki karakter sebanyak `n` (dalam hal ini 9 karakter). Perhatikan:

```
 +---+---+---+---+---+---+---+---+---+
 | I | n | d | o | n | e | s | i | a |
 +---+---+---+---+---+---+---+---+---+
 0   1   2   3   4   5   6   7   8   9    -> baris pertama
-9  -8  -7  -6  -5  -4  -3  -2  -1        -> baris kedua
```

Baris pertama dari angka yang sejajar memberikan posisi index `0` sampai `9` di dalam string. Baris kedua memberikan indeks negatif yang sesuai. 

Mencoba untuk menggunakan indeks yang melebihi panjang atau jumlah karakter dari string akan mengakibatkan kesalahan:

```Python
>>> kata[56]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
```

Tapi, ketika kita melakukan pengirisan dengan indeks yang nilainya melebihi batas tidak akan terjadi kesalahan.

```Python
>>> kata[:56]
'Indonesia'
>>> kata[56:]
''
```

String di Python tidak bisa diubah (`immutable`). Oleh karena itu, ketika kita mencoba untuk menugaskan nilai lain ke dalam sebuah string dalam posisi tertentu, akan menyebabkan kesalahan:

```Python
>>> kata[0] = 'E'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>> kata[2:] = "On"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment 
```

Jika kita membutuhkan string yang berbeda, kita harus membuat yang baru.

```Python
>>> 'E' + kata[1:]
'Endonesia'
>>> kata[:6] + 'sian'
'Indonesian'
```

Python menyediakan fungsi `len()` di mana fungsi ini mengembalikan nilai integer dari jumlah karakter pada string yang dilewati sebagai parameter untuk fungsi tersebut.

```Python
>>> len("Indonesia")
9
```

###List

Python mengenal sejumlah tipe data majemuk (bertumpuk) yang digunakan untuk mengelompokan nilai-nilai bersama dalam satu kesatuan. Tipe data ini ialah `list` yang berisi item-item yang dipisahkan dengan tanda koma dimana item-item tersebut dibungkus dengan tanda kurung persegi (`[]`). Sebuah list berisi item-item dari berbagai jenis data, tapi biasanya item-item tersebut memiliki tipe yang sama.

```Python
>>> rokaat_solat = [2, 4, 4, 3, 4]
>>> rokaat_solat
[2, 4, 4, 3, 4]
```

list juga bisa diindeks dan diiris layaknya string (karena semua tipe data `sequence` bisa melakukannya). Perhatikan contoh berikut ini:

```Python
>>> rokaat_solat[0] # solat subuh 
2
>>> rokaat_solat[-1] # solat isya
4
>>> rokaat_solat[-3:] # solat ashar sampai isya
[4, 3, 4]
```

Semua operasi pada irisan akan mengembalikan sebuah list baru yang berisi item-item yang diminta. Ini berarti bahwa irisan berikut mengembalikan list yang baru dari list yang ada (copy).

```Python
>>> rokaat_solat[:]
[2, 4, 4, 3, 4]
```

List juga mendukung operasi penggabungan (perekatan - `concatenate`) seperti string dengan operator `+`.

```Python
>>> angka_ganjil = [1, 3, 5, 7]
>>> angka_ganjil + [9, 11, 13, 15, 17, 19, 21]
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21]
```

List bersifat `muttable`, ia tidak seperti string yang sifatnya `immutable`. setiap item pada list yang diakses melalui indeks bisa diubah atau ditugaskan item dari nilai lain ke dalamnya.

```Python
>>> from pprint import pprint
>>> tugas_kampus = [
... 'Pencarian Paper Algoritma RSA',
... 'Perhitungan Dasar RC4',
... 'Konsep K-Mean Dasar'
... ]
>>> p(tugas_kampus)
['Pencarian Paper Algoritma RSA',
 'Perhitungan Dasar RC4',
 'Konsep K-Mean Dasar']
>>> tugas_kampus[1] = 'Perhitungan Dasar RC6 + SHA1' 
>>> pprint(tugas_kampus)
['Pencarian Paper Algoritma RSA',
 'Perhitungan Dasar RC6 + SHA1',
 'Konsep K-Mean Dasar']
```

Kita juga dapat menambahkan item baru pada akhir list, yaitu dengan menggunakan method `append(item)`. 

```Python
>>> # menambahkan tugas 
... tugas_kampus.append("Penulisan Karya Ilmiah")
>>> pprint(tugas_kampus)
['Pencarian Paper Algoritma RSA', 
 'Perhitungan Dasar RC6 + SHA1', 
 'Konsep K-Mean Dasar', 
 'Penulisan Karya Ilmiah']

```

Kita juga bisa menugaskan nilai ke dalam bentuk irisan dalam sebuah list. tapi, ini berpotensi untuk mengubah ukuran list atau bahkan bisa menghapus semua item-item list.

```Python
>>> huruf = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> huruf
['a', 'b', 'c', 'd', 'e', 'f', 'g']
>>> # menimpa beberapa item tertentu
... huruf[2:5] = ['C', 'D', 'E']
>>> huruf
['a', 'b', 'C', 'D', 'E', 'f', 'g']
>>> # menghapus beberapa item tertentu
... huruf[2:5] = []
>>> huruf
['a', 'b', 'f', 'g']
>>> # menghapus semua item
... huruf[:] = []
>>> huruf
[]
```

Fungsi built-in `len()` juga berlaku untuk list.

```Python
>>> huruf = ['a', 'b', 'c', 'd']
>>> len(huruf)
4
```

Kita juga bisa membuat list bersarang, artinya mengisi item-item list dengan nilai list lain. Perhatikan contoh berikut ini:

```Python
>>> list_1 = [12.3, 4.67, 7.65]
>>> list_2 = [4.5, 67.86, 44.21]
>>> list_3 = [list_1, list_2]
>>> list_3
[[12.3, 4.67, 7.65], [4.5, 67.86, 44.21]]
>>> list_3[0]
[12.3, 4.67, 7.65]
>>> list_3[1]
[4.5, 67.86, 44.21]
>>> list_3[0][2]
7.65
```



