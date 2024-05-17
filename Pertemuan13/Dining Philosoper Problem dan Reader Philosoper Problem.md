## Dining Philosopr Problem dan Reader Philosper Problem dengan solusi

### 1.Dining Philosopher Problem
Masalah ini menggambarkan lima filsuf yang duduk di meja bundar.Setiap filsuf bergantian antara makan dan berpikir.
Di antara setiap dua filsuf ada satu garpu. Untuk makan, seorang filsuf membutuhkan dua garpu. Masalahnya adalah menghindari deadlock, di mana setiap filsuf mengambil satu garpu dan menunggu garpu kedua, menyebabkan semua filsuf kelaparan.

**Solusi**: untuk menhindari deadlock<br>
1.Menggunakan Asimetris (pendekatan Aritmetik),yaitu Nomor ganjil mengambil garpu kiri terlebih dahulu, lalu garpu kanan.
Nomor genap mengambil garpu kanan terlebih dahulu, lalu garpu kiri.
<br>
2.Membatasi jumlah filsuf yang bisa makan bersama dengan Menggunakan semaphore untuk membatasi hanya empat filsuf yang bisa mengambil garpu pada satu waktu.

### 2.Reader philosopher problem
masalah ini melibatkan beberapa pembaca dan penulis yang berbagi sumber daya data yang sama.Readers dapat membaca data seccra bersamaan, tetapi penulis memerlukan akses eksklusif.
Namun masalahnya dalah enghindari kelaparan untuk pembaca atau penulis dan memastikan sinkronisasi yang tepat.

**Solusi**: <br>
1.Prioritas pembaca,Pembaca tidak boleh menunggu selama tidak ada penulis yang sedang menulis dan
Penulis menunggu sampai tidak ada pembaca yang membaca.
<br>
2.Prioritas Penulis yaitu Penulis tidak boleh menunggu terlalu lama dan Jika ada penulis yang menunggu, pembaca baru tidak boleh memulai membaca.
