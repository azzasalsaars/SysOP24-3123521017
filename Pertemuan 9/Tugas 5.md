## FORK 01,02,dan 03
### Fork : parent - Child 
Penggunaan fork merupakan proses pembuatan salinan dari proses yamh sudah ada,setiap menggunakan fungsi fork program akan membuat salinan dari proses yang memanggilnya

-Pertama kita Cloning ke repo : https://github.com/ferryastika/operatingsystem.git ,kemudian masuk ke operting system untuk melihat isi direktori

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/c9d8909e-7acf-4276-821b-7f32f294bc29)

-install gcc g++
Instalasi ini dilakukan untuk mengompile program dan gcc g++ adalh compiler untuk bahasa C dan C++

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/36974588-d83d-491d-a112-f1b2e44f6d0b)

#### fork01
  ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/4c5d410e-1ea4-40f0-8c18-c1529cc27a25)
<br>
**Analisis** : Fork01 ini ketika dijalankan membuat salinan dari proses yang memanggilnya(parent proses),dan setelah melakukan fork proses parent dan child akan mencetak pesan yang sama karena menjalankan kode yang sama.
Menampilkan Hasil PID,PPID,dan UID.

#### fork02
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/434caf5b-6795-473e-9643-61adc302338b)
<br>
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/6e924f09-05d1-4392-bdd8-3439e7bb1dcb)
<br>
**Analisis** : Fork02 menunjukkan perbedaan antara parent dan child proses menggunakan nilai yang dikembalikan oleh fungsi fork,Perbedaan output menunjukkan bahwa kedua proses berbeda dan daat diidentifikasi. 

#### fork 03
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f8b5a94b-d5d0-46c1-a7b9-44728201a3fa)
<br>
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/fa6be0ad-23a3-44de-b572-b0b54028df79)
**Analisis** : Fork03 menunjukkan lebih banyak kompleksitas dalam hubungan parent dan child,dalam proses parent proses harus menunggu child proses selesai sebelum melanjutkan prosesnya sendiri.


