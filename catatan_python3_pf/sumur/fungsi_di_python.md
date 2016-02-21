# Fungsi Di Python

Kita bisa menggunakan kata kunci `def` untuk mendefinisikan sebuah fungsi di Python. selanjutnya setelah menulis kata kunci tersebut, harus diikuti dengan nama fungsinya serta beberapa parameter opsional yang diapit dengan tanda kurung. Setiap pernyataan di dalam sebuah fungsi (tubuh fungsi) harus menjorok 1 tab (4 spasi).

```Python
def nama_fungsi(param):
    pernyataan_1
    pernyataan_2
    pernyataan_ke_n
```

Pernyataan pertama dari tubuh fungsi secara opsional bisa berupa string literal. string literal ini digunakan untuk mendokumentasikan sebuah fungsi atau lebih dikenal sebagai `docstring`. `docstring` adalah sebuah alat yang digunakan untuk secara otomatis menghasilkan dokumentasi online atau dokumentasi dalam format cetakan. Cara ini sangat dianjurkan karena merupakan praktik yang baik untuk selalu mendokumentasikan sebuah program.

variabel global tidak bisa dirubah nilainya di dalam sebuah fungsi. Ada aturan tertentu untuk benar-benar merubah variabel global yang kita definisikan di luar fungsi untuk dapat diubah nilainya.

```Python
>>> my_global_var = 34
>>> def test():
...     my_global_var = 100
...     print(my_global_var)
... 
>>> test()
100
>>> my_global_var
34
```

Parameter atau argumen untuk fungsi merupakan variabel lokal. Argumen tersebut diteruskan di dalam fungsi dimana hal ini disebut sebagai `call by value` karena ketika kita memanggil fungsi tersebut dan melewatkan variabel yang berisi nilai ke dalamnya, maka variabel yang kita lewatkan tidak berubah nilainya walaupun argumen di fungsi tersebut diubah.

```Python
>>> def test(a):
...     a = a + 10
...     print(a)
... 
>>> a = 30
>>> test(a)
40
>>> a
30
```

Ketika kita mengakses sebuah fungsi dengan hanya nama fungsi-nya saja, maka hasilnya berupa tipe yang dinyatakan oleh interpreter sebagai fungsi yang dibuat oleh pengguna. Nilai ini dapat ditugaskan ke variabel lain (nama lain) yang kemudian variabel tersebut bisa digunakan sebagai fungsi. Hal semacam ini dinyatakan sebagai `mekanisme penamaan umum`:

```Python
>>> def luasPersegiPanjang(p, l):
...     print(p * l)
... 
>>> luasPersegiPanjang
<function luasPersegiPanjang at 0x7f1fb93b6048>
>>> hitungLuas = luasPersegiPanjang
>>> hitungLuas(10, 4)
40
>>> luasPersegiPanjang(10, 4)
40
```

Beberapa bahasa lain menganggap fungsi harus mengembalikan sebuah nilai, jika fungsi tidak mengembalikan nilai, maka fungsi tersebut dikenal sebagai `prosedur`. perhatikan pada fungsi `luasPersegiPanjang`, fungsi tersebut tidak mengembalikan sebuah nilai. Pada kenyataannya, fungsi di atas sekalipun tidak menyertakan pernyataan `return` untuk mengembalikan nilai, ia tetap mengembalikan nilai. Nilai yang dikembalikan oleh sebuah fungsi tanpa pernyataan `return` adalah `None`. `None` adalah nama built-in dari Python. Kita bisa melihat dan membuktikannya dengan bantuan fungsi `print()` untuk mencetak nilai kembali dari suatu fungsi sekalipun nilainya `None`.

```Python
>>> print(luasPersegiPanjang(10, 4))
40
None
```

Kita bisa mengubah fungsi untuk dapat mengembalikan nilai dengan kata kunci `return`. Perhatikan contoh di bawah ini:

```Python
>>> def luasPersegiPanjang(p, l):
...     return p * l
... 
>>> panjang, lebar = 20.4, 400.33
>>> luas = luasPersegiPanjang(panjang, lebar)
>>> luas
8166.731999999999
>>> round(luas, 2)
8166.73
```

Fungsi dapat melakukan hal tersebut karena adanya kata kunci `return`. Contoh di atas, hasil perkalian `p` dan `l` akan dikembalikan nilainya ke pemanggil fungsi tersebut. Dalam kata lain, nilai kembali dari sebuah fungsi akan ditampung di dalam variabel `luas` berupa nilai hasil perkalian dari `panjang` dan `lebar` yang dilakukan di dalam sebuah fungsi `luasPersegiPanjang`. Nilai yang ada di dalam variabel `luas` dibulatkan ke angka 2 digit setelah titik desimal.



