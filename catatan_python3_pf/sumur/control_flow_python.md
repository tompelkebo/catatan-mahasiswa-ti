# Control Flow Python

Dalam materi ini kita akan belajar tentang aliran control atau control flow dengan tikungan atau indentasi. Control flow juga dikenal di bahasa lain sebagai core dari sebuah bahasa seperti penyataan `if..else`, `for`, `while` dan lain sebagainya.


## Penyeleksian Kondisi Dengan Pernyataan If

Mungkin dimana-mana jenis pernyataan untuk control flow yang sering dikenal adalah pernyataan `if`. Perhatikan contoh di bawah ini:

```Python
>>> ipk = float(input("Masukan ipk anda: "))
Masukan ipk anda: 3.5
>>> if ipk < 2.0:
...     ipk = 2
...     print("anda pasti kepikiran cewek saat kuliah")
... elif ipk == 2.0:
...     print("anda pasti kepikiran pulang saat kuliah")
... elif ipk < 3.0:
...     print("anda fokus")
... elif ipk > 3.0 and ipk <= 4.0:
...     print("anda ambisius")
... else:
...     print("mahasiswa macam apa anda ?")
... 
anda ambisius
```

Kita dapat menyertakan nol atau lebih bagian `elif`. bagian `else` opsional. kata kunci `elif` kependekan dari `else if` dan sangat berguna untuk menghindari lekukan yang berlebihan. Pernyataan `if...elif...else` merupakan pengganti dari penggunaan pernyataan `switch` atau `case` yang ada di bahasa pemrograman lainnya selain Python.


## Perulangan Dengan Pernyataan For

Pernyataan `for` di Python sedikit berbeda dari apa yang kita ketahui di bahasa lain seperti C atau Pascal. `for` di Python tidak menggunakan iterasi melalui sederetan aritmatika dari angka seperti `Pascal` atau memberikan pengguna untuk menentukan langkah-langkah iterasi dan kondisi untuk menghentikan sebuah iterasi seperti di `C`, Python hadir dengan iterasi yang bisa dilakukan untuk objek-objek sequence (objek yang memiliki urutan) seperti `string` atau `list`. 

```Python
>>> # Mengukur setiap item (string) di list
... kata = ['Kucing', 'Jendela', 'Cinta']
>>> for k in kata:
...     print(k, len(k))
... 
Kucing 6
Jendela 7
Cinta 5
```

Jika kita perlu untuk mengubah urutan iterasi sementara di dalam sebuah perulangan (misalnya untuk menduplikasi item yang dipilih), disarankan untuk membuat salinan. Sebuah iterasi untuk objek sequence tidak secara implisit membuat salinan. Salinan ini bisa dibuat dengan notasi irisan yang memang lebih mudah dan nyaman digunakan.

```Python
>>> for k in kata[:]: # buat salinan dengan notasi irisan "[:]"
...     if len(k) > 6:
...         kata.insert(0, k)
... 
>>> kata
['Jendela', 'Kucing', 'Jendela', 'Cinta']
```

## Fungsi Range

Jika kita perlu untuk melakukan itarasi dari urutan angka, kita bisa menggunakan fungsi build-in `range()`. Fungsi ini akan menghasilkan deretan angka aritmatika.

```Python
>>> for i in range(8):
...     print(i)
... 
0
1
2
3
4
5
6
7
```

`end point` yang diberikan tidak pernah menjadi bagian dari sebuah urutan angka yang dihasilkan dari `range()`. Misalnya `range(8)` dimana 8 adalah `end-point`, menghasilkan nilai-nilai berupa sederet angka mulai dari 0 sampai 7, karena jika dihitung 0 sampai 7 memiliki 8 nilai yaitu `0`,`1`,`2`,`3`,`4`,`5`,`6` dan `7`. Kita juga bisa membuat loncatan berdasarkan step atau langkah yang ditempatkan di argumen terakhir dari fungsi `range()`.

```
range(5, 10)
   5 sampai 9

range(0, 10, 3)
   0, 3, 6, 9

range(-10, -100, -30)
  -10, -40, -70
```

Kita juga bisa mengkombinasikan `range()` dan `len()` untuk iterasi di mana dalam iterasi tersebut kita mengakases tiap item yang ada di `list` melalui nomer indeksnya dan mencetak setiap item tersebut sehingga berdampingan dengan nomer indeks-nya.

```Python
>>> a = ['Jono', 'selalu', 'cayank', 'kamoh']
>>> for i in range(len(a)):
...     print(i, a[i])
... 
0 Jono
1 selalu
2 cayank
3 kamoh
```

Dari kasus di atas, ada cara lain yang lebih mudah digunakan dengan bantuan fungsi `enumerate()`. Perhatikan contoh berikut ini:

```Python
>>> a = ['Jono', 'selalu', 'cayank', 'kamoh']
>>> for indeks, data in enumerate(a):
...     print(indeks, data)
... 
0 Jono
1 selalu
2 cayank
3 kamoh
```

Satu hal yang terlihat aneh jika kita mencoba mencetak fungsi `range()` :

```Python
>>> print(range(8))
range(0, 8)
>>> range(8)
range(0, 8)
```

Mungkin kita mengira `range()` akan mengembalikan nilai berupa `list`, ternyata tidak ! Ini tidak seperti fungsi `range()` di Python 2, fungsi `range()` di Python 3 akan mengembalikan objek `range` dan bukan objek `list`. Hal ini tentunya memiliki alasan lain yaitu untuk menghemat ruang.

Tapi di sini kita bisa menyebut objek tersebut sebagai objek `iterable` atau objek yang bisa diiterasi. Untuk mengubahnya menjadi objek yang bisa di iterasi atau dengan kata lain untuk mengubahnya ke dalam bentuk `list`, gunakan fungsi konversi `list()`. Perhatikan contoh berikut ini:

```Python
>>> print(list(range(8)))
[0, 1, 2, 3, 4, 5, 6, 7]
>>> list(range(8))
[0, 1, 2, 3, 4, 5, 6, 7]
```

## Pernyataan Break, Continue dan Klausa Else Dalam Perulangan

Pernyataan `break` digunakan untuk keluar dari perulangan pada  iterasi `for` atau `while`. Pernyataan perulangan memiliki pernyataan klausa `else` dimana blok ini akan dieksekusi ketika perulangan terhenti baik terhenti karena kondisi perulangan menjadi `false` (`while`) ataupun karena item-item list telah habis di iterasi (`for`), tetapi blok ini tidak akan dieksekusi ketika sebuah perulangan terhenti karena pernyataan `break`. Berikut ini adalah contoh yang memberikan kita bagaimana klausa `else` bekerja yang dimiliki oleh pernyataan perulangan seperti berikut:

```Python
>>> for n in range(2,10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'sama dengan', x, '*', n//x)
...             break
...     else:
...         print(n, 'adalah angka prima')
... 
2 adalah angka prima
3 adalah angka prima
4 sama dengan 2 * 2
5 adalah angka prima
6 sama dengan 2 * 3
7 adalah angka prima
8 sama dengan 2 * 4
9 sama dengan 3 * 3
```

Ketika klausa `else` digunakan untuk perulangan, klausa `else` tersebut memiliki lebih banyak kesamaan ketika klausa ini digunakan dalam blok `try` dibandingkan dengan blok `if`. Blok `else` (klausa `else`) pada blok `try` akan dieksekusi ketika sebuah `exception` terjadi dan Blok `else` (klausa `else`) pada perulangan `for` atau `while` akan dieksekusi ketika pernyataan `break` tidak dieksekusi atau dengan kata lain ketika `break` tidak terjadi.

Pernyataan `continue` juga meminjam dari C. Pernyataan `continue` digunakan untuk melanjutkan iterasi berikutnya dan tidak lagi mengeksekusi pernyataan di bawahnya dari sebuah perulangan.

```Python
>>> for angka in range(2,15):
...     if angka % 2 == 0:
...         print("Angka genap ditemukan:", angka)
...         continue
...     print("Angka ditemukan:", angka)
... 
Angka genap ditemukan: 2
Angka ditemukan: 3
Angka genap ditemukan: 4
Angka ditemukan: 5
Angka genap ditemukan: 6
Angka ditemukan: 7
Angka genap ditemukan: 8
Angka ditemukan: 9
Angka genap ditemukan: 10
Angka ditemukan: 11
Angka genap ditemukan: 12
Angka ditemukan: 13
Angka genap ditemukan: 14
```

## Pernyataan Pass

Pernyataan `pass` tidak melakukan apapun. Pernyataan ini dapat digunakan ketika sebuah pernyataan secara sintaksis wajib ada namun program tidak mengharuskan melakukan aksi atau sesuatu.

```Python
>>> while True:
...     pass    # ditangguhkan, hingga melakuakn interupsi
... 
```

Pernyataan `pass` biasa digunakan untuk membuat class sederhana.

```Python
>>> class Mahasiswa:
...     pass
... 
```

Di tempat lain, pernyataan `pass` bisa digunakan sebagai `place-holder` untuk sebuah fungsi. Bagaimanapun pernyataan `pass` secara diam-diam diabaikan.

```Python
>>> def kalkulasiTask(*args):
...     pass
... 
```



