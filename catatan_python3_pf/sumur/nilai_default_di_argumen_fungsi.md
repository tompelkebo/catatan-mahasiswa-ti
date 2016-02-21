# Nilai Default Di Argumen Fungsi

Kita bisa menentukan nilai default untuk satu atau lebih argumen pada sebuah fungsi. Dengan begini, sebuah fungsi yang memiliki argumen lebih dari satu bisa digunakan atau bisa dipanggil dengan meluluskan nilai ke beberapa argumen utamanya saja.

Untuk melakukan ini, kita bisa menugaskan nilai di dalam sebuah argumen layaknya penugasan nilai ke dalam variabel seperti biasanya.


```Python
def test(a, b=1, c='String'):
    pass

```

`b` dan `c` adalah argumen yang memiliki nilai default. ketika fungsi di atas di panggil, kita hanya perlu melewatkan nilai ke argumen pertamanya saja (`a`), namun kita juga masih bisa melewatkan ke argumen `b` dan `c` walaupun itu opsional.

```Python
call1 = test(2)
call2 = test(2, 3)
call3 = test(2, 3, 'My Name Is Tom Kebo')
```
Nilai default dari argument dievaluasi pada titik dimana sebuah fungsi di definisikan dalam ruang lingkup definisi, jadi:

```Python
i = 5

def f(arg=i):
    print(arg)

i = 6
f()    # mencetak 5
```

**Perhatikan!**, Nilai default hanya dievaluasi sekali. Jika kita sebuah objek seperti `list`, `dictionary` atau `instance` dari `class` sebagai argumen maka nilai tersebut bisa diubah, dalam kata lain perubahan nilainya juga terlihat diluar fungsi. Hal ini dikenal sebagai `pass by reference`.

```Python
def f(a, L=[]):
    L.append(a)
    return L

print(f(1))
print(f(2))
print(f(3))
```

Hasil yang diperoleh:

```
[1]
[1, 2]
[1, 2, 3]
```
Bentuk keduanya, perhatikan contoh berikut:

```Python



Jika kita ingin nilai default sebagai argumen tidak dapat diubah sekalipun kita melewatkan objek ke dalamnya (fungsi), kita bisa menulis fungsi seperti di bawah ini sebagai gantinya:

```Python
def f(a, L=None):
    if L is None:
        L = []
    L.append(a)
    return L
```


[]()# Nilai Default Di Argumen Fungsi

Kita bisa menentukan nilai default untuk satu atau lebih argumen pada sebuah fungsi. Dengan begini, sebuah fungsi yang memiliki argumen lebih dari satu bisa digunakan atau bisa dipanggil dengan meluluskan nilai ke beberapa argumen utamanya saja.

Untuk melakukan ini, kita bisa menugaskan nilai di dalam sebuah argumen layaknya penugasan nilai ke dalam variabel seperti biasanya.


```Python
def test(a, b=1, c='String'):
    pass

```

`b` dan `c` adalah argumen yang memiliki nilai default. ketika fungsi di atas di panggil, kita hanya perlu melewatkan nilai ke argumen pertamanya saja (`a`), namun kita juga masih bisa melewatkan ke argumen `b` dan `c` walaupun itu opsional.

```Python
call1 = test(2)
call2 = test(2, 3)
call3 = test(2, 3, 'My Name Is Tom Kebo')
```
Nilai default dari argument dievaluasi pada titik dimana sebuah fungsi di definisikan dalam ruang lingkup definisi, jadi:

```Python
i = 5

def f(arg=i):
    print(arg)

i = 6
f()    # mencetak 5
```

**Perhatikan!**, Nilai default hanya dievaluasi sekali. Jika kita membuat nilai default sebagai objek yang bersifat `mutable` (seperti `list`, `dictioary` atau `instance` dari `class`), maka fungsi tersebut akan terus terakumulasi oleh argumen yang dilewatkan pada pemanggilan fungsi berikutnya.

```Python
def f(a, L=[]):
    L.append(a)
    return L

print(f(1))
print(f(2))
print(f(3))
```

Hasil yang diperoleh:

```
[1]
[1, 2]
[1, 2, 3]
```

Jika kita ingin nilai default sebagai argumen tidak dapat terakumulasi pada nilai argumen yang dilewatkan pada pemanggilan berikutnya, kita bisa menulis fungsi seperti di bawah ini sebagai gantinya:

```Python
def f(a, L=None):
    if L is None:
        L = []
    L.append(a)
    return L
```

Jika kita melewatkan sebuah objek seperti `list`, `dictionary` atau `instance` dari `class` yang sifatnya `mutable` sebagai argumen, maka nilai tersebut bisa diubah di dalam fungsi, dalam kata lain perubahan nilainya juga terlihat diluar fungsi. Hal ini dikenal sebagai `pass by reference`.

```Python
>>> y = [3,4,5]
>>> def g(x):
...     x.append(1)
... 
>>> g(y)
>>> y
[3, 4, 5, 1]
>>> y
[3, 4, 5, 1]
>>> g(y)
>>> y
[3, 4, 5, 1, 1]
```
Dimana `y` di definisikan di luar fungsi, namun nilainya bisa diubah di dalam fungsi. perubahannya berdampak diluar fungsi.




