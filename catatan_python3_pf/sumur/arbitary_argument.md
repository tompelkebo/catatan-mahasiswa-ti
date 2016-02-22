# Arbitary Argument

Biasanya, argumen `variadic` ini akan menjadi yang terakhir setelah `argumen formal`, karena mereka mengambil argumen yang tersisa yang dilewatkan ke fungsi. Setiap `argumen formal` yang muncul setelah argumen `*args` hanya ada `argumen kata kunci`, yang berarti bahwa mereka hanya dapat digunakan sebagai `argumen kata kunci` dan bukan sebagai `argumen posisi`.

```Python
>>> def gabung_kata(*args, sep="@"):
...     return sep.join(args)
... 
>>> gabung_kata("tompel", "kebo", "kece")
'tompel@kebo@kece'
>>> gabung_kata("tompel", "kebo", "kece", sep="-")
'tompel-kebo-kece'
```

Sebenarnya apa itu `args` ? kita sudah membahas di artikel sebelumnya bahwa args adalah sebuah argumen yang bertipe `tuple` dimana ia merangkul semua nilai yang dilewatkan sebagai parameter di dalam sebuah fungsi yang mana nilai tersebut merupakan `argumen posisi`. Hanya untuk mengingat kembali bahwa `*args` harus didahului sebelum `**kwargs`.

```Python
>>> def gabung_kata(*args, sep="@"):
...     print(args, type(args))
... 
>>> gabung_kata("tompel", "kebo", "kece")
('tompel', 'kebo', 'kece') <class 'tuple'>
```





 


