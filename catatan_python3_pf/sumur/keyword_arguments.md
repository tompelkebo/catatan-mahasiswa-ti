# Keyword Arguments Python

Di dalam pemanggilan fungsi, kita juga bisa melewatkan argument dengan menggunakan kata kunci dalam bentuk `kwargs=nilai`. Dalam pemabahasan ini kita akan menngenal `argumen posisi`, `argumen kata kunci`, `argumen opsional` dan `argumen non-opsional` (formal). `argumen opsional` dapat berupa `argumen kata kunci` atau `argumen posisi` lalu `argumen formal` juga dapat berupa `argumen kata kunci` dan `argumen posisi`. 

```
[1] argumen opsional:
    + argumen kata kunci
    + argumen posisi

[2] argumen formal:
    + argumen kata kunci
    + argumen posisi 
```

Konsep lain seperti:

```
Parameter Formal     : Kumpulan Argumen Formal
Parameter Non Formal : Kumpulan Argumen Opsional
```
Maka dengan kata lain kita dapati konsep sebagai berikut :

1. Setiap `parameter formal` merupakan satu atau lebih `argumen formal` dan setiap `argumen formal` dapat berlaku  sebagai `argumen kata kunci` dan `argumen posisi` sesuai variasinya.

2. Setiap `parameter non formal` merupakan satu atau lebih `argumen opsional` dan setiap `argumen opsional` dapat berlaku  sebagai `argumen kata kunci` dan `argumen posisi` sesuai variasinya.

3. Setiap `parameter non formal` harus menjadi parameter kedua setelah `parameter formal`.


Perhatikan contoh berikut ini:

```Python
def parrot(voltage, 
        state='a stiff', action='voom', 
        type='Norwegian Blue'):
    print("-- This parrot wouldn't", action, end=' ')
    print("if you put", voltage, "volts through it.")
    print("-- Lovely plumage, the", type)
    print("-- It's", state, "!")
```

Fungsi di atas menerima satu argumen yang formal (`voltage`) dan memiliki tiga argumen opsional (`state`, `action` dan `type`). Kembali ke konsep, kita analisis dari fungsi di atas:

1. `parameter formal` : argumen berupa `voltage` yang harus ada ketika pemanggilan sebuah fungsi `parrot`.
2. `parameter non formal`: argumen berupa `state`, `action` dan `type`.

Fungsi ini bisa dipanggil dengan berbagai cara seperti pada contoh berikut:

```Python
# 1 argumen formal (voltage) dengan enggunakan argumen posisi
parrot(1000)

# 1 argumen formal (voltage) dengan enggunakan argumen kata kunci             
# sehingga ada 1 argumen kata kunci                     
parrot(voltage=1000) 

# 1 argumen formal dengan menggunakan argumen kata kunci
# 1 argumen opsional dengan menggunakan argumen kata kunci
# sehingga ada 2 argumen kata kunci  
parrot(voltage=1000000, action='VOOOOOM') 
  
# 1 argumen opsional dengan menggunakan argumen kata kunci
# 1 argumen formal dengan menggunakan argumen kata kunci
# sehingga ada 2 argumen kata kunci        
parrot(action='VOOOOOM', voltage=1000000)     
 
# 1 argumen formal dengan menggunakan argumen posisi
# 2 argumen opsional dengan menggunakan 2 argumen posisi  
# sehingga ada 3 argumen posisi
parrot('a million', 'bereft of life', 'jump')    
   
# 1 argumen formal dengan menggunakan argumen posisi
# 1 argumen opsional dengan menggunakan argumen kata kunci
# sehingga ada 1 argumen posisi dan 1 argumen kata kunci
parrot('a thousand', state='pushing up the daisies')  
```

Pemanggilan di bawah ini menjadi tidak valid:

```Python
# tidak menyertakan argumen wajib
parrot()             

# tidak ada kata kunci argumen setelah kata kunci
# argumen pada argument pertama
parrot(voltage=5.0, 'dead')  

# duplikasi nilai pada argumen yang sama
parrot(110, voltage=220)     

# mengakses argumen yang tidak ada
parrot(actor='John Cleese')  
```
Dalam pemanggilan fungsi, argumen yang menggunakan kata kunci harus sesuai misalnya seperti `action`, `state` dan `type`. Ini termasuk argumen non-opsional atau wajib seperti `voltage=1000`. Berikut ini adalah contoh yang salah ketika kita mencoba untuk melewatkan nilai ke dalam fungsi lebih dari yang sudah ditetapkan:

```Python
>>> def function(a):
...     pass
...
>>> function(0, a=0)
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
TypeError: function() got multiple values for keyword argument 'a'
```

Argumen dengan bentuk `**argumen` menerima sebuah nilai berupa objek `dictionary`. Argumen ini berisi semua `argumen kata kunci`, kecuali `argumen formal`.

Argumen dengan bentuk `*argumen` menerima `tuple` yang berisi semua `argumen posisi` di luar dari daftar `argumen formal`. Perlu diperhatikan bahwa `**argumen` didahului dengan `*argumen`.

```Python
def cheeseshop(kind, *arguments, **keywords):
    print("-- Do you have any", kind, "?")
    print("-- I'm sorry, we're all out of", kind)
    for arg in arguments:
        print(arg)
    print("-" * 40)
    keys = sorted(keywords.keys())
    for kw in keys:
        print(kw, ":", keywords[kw])
```

Fungsi di atas bisa digunakan seperti ini:

```Python
cheeseshop("Limburger", "It's very runny, sir.",
           "It's really very, VERY runny, sir.",
           shopkeeper="Michael Palin",
           client="John Cleese",
           sketch="Cheese Shop Sketch")
```

dan tentu saja itu akan mencetak:

```
-- Do you have any Limburger ?
-- I'm sorry, we're all out of Limburger
It's very runny, sir.
It's really very, VERY runny, sir.
----------------------------------------
client : John Cleese
shopkeeper : Michael Palin
sketch : Cheese Shop Sketch
```

Perhatikan pada daftar nama `argumen kata kunci` dibuat dengan menyortir hasil kuncinya dengan method `sorted()` sehingga hasilnya lebih terurut.