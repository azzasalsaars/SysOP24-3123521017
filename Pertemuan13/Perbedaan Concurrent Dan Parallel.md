## ILUSTRASIKAN PERBEDAAN CONCURRENT DAN PARALLEL
### Ilustrasi
Dalam sebuah lestoran terdapat dua cara pelayanan dalam mengurus pelanggan
<br>
#### CONCURRENT(Bersamaan) :
Pelayan A melayani beberapa meja dengan cara mencatat pesanan di meja 1,lalu ke dapur untuk memberitahu koki.
dia pergi ke Meja 2 untuk mencatat pesanan berikutnya, dan kemudian kembali ke dapur untuk memastikan pesanan Meja 1 sedang diproses. Begitu seterusnya. Pelayan A bekerja dengan bergantian antar meja, 
sehingga semua pesanan akhirnya diproses tanpa harus menunggu satu selesai sepenuhnya sebelum mulai yang lain.
#### Parallel :
Terdapat dua pelayan(A Dan B).Pelayan A melayani Meja 1 dan Pelayan B melayani Meja 2. Keduanya bekerja pada saat yang sama untuk memproses pesanan masing-masing meja. 
Meja 1 dan Meja 2 bisa mendapatkan pesanan mereka lebih cepat karena tidak harus menunggu pelayan bergantian.

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/88d76089-0ed2-41cd-aef8-d3500a8fd17c)

### Penjelasan
**Cocurrent**(Bersamaan),Berarti menjalankan beberapa tugas hampir bersamaan dengan cara bergantian.Dalam proses ini sering melibatkan
satu CPU yang berganti-ganti antara tugas-tugas dengansangat cepat sehingga tampak seperti dilakukan bersama.
Sedangkan **Parallel** menjlankan nbebrapa tugas secara benar-benar bersamaan .Dalam komputasi, ini memerlukan bnyak CPU(ata core)dimana setipa CPU menjalankan tugas yang berbeda pada waktu yang sama.
