## TUGAS 3

1.Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operasi.

#### Jadi tahap-tahap dalam siklus CPU sbb:

Fetch (Pengambilan):
 
CPU mengambil instruksi dari memori utama (RAM) berdasarkan alamat yang ditunjukkan oleh counter program (Program Counter).
Instruksi ini kemudian disimpan di dalam register instruksi 
        
Decode (Dekode):

CPU menerjemahkan instruksi yang telah diambil dari memori.Instruksi ini dibagi menjadi bagian-bagian yang dapat dimengerti flooleh CPU, seperti opcode dan operand.

Execute (Eksekusi):
        
CPU menjalankan instruksi yang telah didekode.Ini dapat melibatkan operasi aritmatika, logika, perpindahan data, atau instruksi kontrol untuk mengubah aliran eksekusi.

        
#### Peran Bahasa pemrograman adalah:

Bahasa pemrograman adalah alat untuk mengekspresikan logika dan instruksi yang diinginkan untuk dilakukan oleh program.Bahasa pemrograman menyediakan struktur dan sintaks yang dapat dimengerti oleh manusia untuk menulis kode program.Contoh bahasa pemrograman termasuk C, C++, Java, Python, dll.

#### Peran Compiler adalah sbb:

Compiler adalah perangkat lunak yang menerjemahkan kode program yang ditulis dalam bahasa pemrograman tingkat tinggi menjadi bahasa mesin yang dapat dimengerti oleh komputer.Compiler memproses kode program,memeriksanya untuk kesalahan sintaksis, dan menghasilkan output dalam bentuk file biner atau kode objek.Output ini kemudian dapat dieksekusi oleh CPU.
    
#### Peran dari sitem operasi adalah :

Sistem operasi (OS) bertanggung jawab atas manajemen sumber daya komputer, termasuk CPU, memori, perangkat masukan/keluaran, dan jaringan.
OS menyediakan antarmuka antara aplikasi (termasuk program yang ditulis dalam bahasa pemrograman) dan perangkat keras komputer.Saat program dieksekusi, OS memfasilitasi akses ke sumber daya sistem yang diperlukan, mengelola proses, dan menyediakan lingkungan yang aman dan stabil bagi eksekusi program.

2.Membaca dan memahami

3.Menjalankan VM Debian

-$ make

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/8ab13ec7-3a8b-47e6-80b7-072dd9407881)

menginstal make dengan cara menginputkan apt upgrade
kemudian apt install make


-$ make clean

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7b6f817d-4385-4a09-b65f-1ebbc109398b)


-$ sudo make install

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f6b892bc-2210-4052-9a2c-072ed75ec857)


-$ sudo make uninstal

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/9e77d84a-8064-41b3-8045-cf5d6d752955)


-$ iops64 $(nproc) 1

 $ flops64 $(nproc)

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/4e435d63-aa98-438a-9183-a173d790f93a)



-$ iops64 $(nproc) 2

flops64 $(nproc)

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ca12c855-ee08-4b57-ba49-ffff259a9d2a)


![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f439cccc-ab93-44f1-9866-d9230e3bd5a4)

-$ iops64 $(nproc)3

flops64 $(nproc)
  
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/6e189ddc-23b4-4b66-89fc-c5cbc0a5214e)



![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/c74ea6c0-d22e-4974-a625-329960df0d70)


  
-$ iops64 $(nproc)4

flops64 $(nproc)

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/a028543e-8ca8-444a-bc2c-9d195e746ef4)


-$ iops64 $(nproc)5

flops64 $(nproc)

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/1530d68b-00d9-486b-8d23-24aabda22931)


#### Perbandingan hasil iops dan flops

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ce286884-d5e8-4f3b-b349-7b0a0f257166)

#### Analisis

CPU : Intel Core i3-1005G1CPU@ 1.20GHz

1.iops64 melakukan benchmarking untuk operasi bilangan bulat 64-bit perdetik,total iops dihitung sebagai jumlah operasi dari semua thread.Iops yang di laporkan pada awalnya adalah 5606999684.

2.Flops64 melakukan benchmarking untuk operasi floating point 64-bit per detik,total flops dihitung sebagai jumlah perasi dari semua thread. FLOPS yang di laporkan pada awalnya adalah 5769843664.

ini menunjukkan bahwa sistem Debian memiliki kemampuan yang cukup besar dalam melakukan operasi bilangan bulat dan floating point pada level 64-bit, dengan throughput yang tinggi pada jumlah thread atau inti prosesor yang digunakan. Hal ini menunjukkan kinerja yang baik dari CPU pada sistem tersebut.

## Proses Bagaimana CPU berjalan 

Pada setiap detik jam, CPU akan melakukan salah satu dari tiga hal, yaitu mengambil intruksi dari alamt memori,memcahkan kode instruksi tersebut,dan menjalankan instruksi secara berulang-ulang dalam satu lingkaran sehingga akan dihitung dengan grafik :

![CPU kosong drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/aacd58d9-5200-432b-92cb-8f75e3cf7c98)

1.Jam perhitungan proses disetel ke 0 dalam proses Fetch 

![CPU 1 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/b83a6e08-a69d-45af-a820-83b1bb9d72f9)

sehingga dalam proses tersebut perhitungan CPU mengambil intruksi 0 di memori dan memasukkan ke dalam register instruksi.

2.Proses Dekode

![CPU 2 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/8d4a5094-78d7-48d1-924c-620d4700bbc1)

CPU menerjemahkan instruksi bagian pertama kemudian instruksinya di muat dengan alamatnya adalah 6,jadi nilai dalam alamat 6 akan di muat dalam akumulator.

3.Proses Execute

![CPU 3 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/029f8456-6289-4e4c-99d8-b4060066a9b2)

Setelah dijalankan akan menuju proses Execute menggunakan nilai di alamat 6,Kemudian dalam akumulator nilainya adalah 1.

### Proses selanjutnya

Fetch ke-2

![CPU 4 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/cc8ee2ac-ff99-4a7a-a7c4-d522b5bfa994)

program counter bertambah dan CPU mengambil insruksi berikutnya di bit memori.

Decode ke-2

![CPU 5 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/9da557f9-9a2d-427e-a616-fee0276d2ce3)

CPU menerjemahkan instruksi,lalu menambahkan 1 dan alamatnya adalah 7,jadi menambahkan alamat 7 ke dalam apa yang sudah ada di akumulator. Jalankan lagi CPU

Execute ke-2

![CPU 6 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7676fbe1-888b-4f9b-ac54-a12c11110673)

Mengeksekusi intruksi dengan menambahkan nilai kel alamta 7 maka nilainya dalam accumulator 1+1 menjadi 2.

Fetch ke-3

![CPU 7 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/1e89fa81-f924-4ee6-95ba-976bb636309e)

Mengambil dari lokasi memori berikutnya yaitu nomor 2.

Decode ke-3

![CPU 8 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/3dde241a-8082-4b02-82bf-c580c4162109)

mendecode untuk menyimpan nilai di akumulator ke dalam RAM di alamat 6,Jalankan

Execute ke-3

![CPU 9 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ad09c6ea-61e7-4dd8-ae88-5f515eeeb0e4)

Alamat 6 sekarang memiliki nilai 2 di dalamnya.

Fetch ke-4

![CPU 10 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/74b6b8cc-f1e5-4a28-817b-b5b7fcd8090b)

Mengambil instrukasi baru dengan lompatan alamat dan mengambil 1 dalam dekode instruksi

Decode ke-5

![CPU 11 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/60d833e9-625f-4dac-a5cd-943c417bf804)

Lompat ke alamat nomor 1 

Execute ke -4

![CPU 12 drawio](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/dc88c8ee-adc1-4471-82c8-571928cfe67f)

Penghitungan kembali ke 1.

Kemampuan untuk melompat, mengulang, dan membuat instruksi secara rekursif adalah salah satu dasar dalam ilmu komputer.


