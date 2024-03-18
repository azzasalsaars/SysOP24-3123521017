## TUGAS 3

1.Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operasi.

#### Jadi tahap-tahap dalam siklus CPU sbb:

    Fetch (Pengambilan):
        CPU mengambil instruksi dari memori utama (RAM) berdasarkan alamat yang ditunjukkan oleh counter program (Program Counter).
        Instruksi ini kemudian disimpan di dalam register instruksi 
        
    Decode (Dekode):
        CPU menerjemahkan instruksi yang telah diambil dari memori.
        Instruksi ini dibagi menjadi bagian-bagian yang dapat dimengerti             flooleh CPU, seperti opcode dan operand.

    Execute (Eksekusi):
        CPU menjalankan instruksi yang telah didekode.
        Ini dapat melibatkan operasi aritmatika, logika, perpindahan data, atau instruksi kontrol untuk mengubah aliran eksekusi.

        
#### Peran Bahasa pemrograman adalah:
    Bahasa pemrograman adalah alat untuk mengekspresikan logika dan instruksi yang diinginkan untuk dilakukan oleh program.
    Bahasa pemrograman menyediakan struktur dan sintaks yang dapat dimengerti oleh manusia untuk menulis kode program.
    Contoh bahasa pemrograman termasuk C, C++, Java, Python, dll.

#### Peran Compiler adalah sbb:

    Compiler adalah perangkat lunak yang menerjemahkan kode program yang ditulis dalam bahasa pemrograman tingkat tinggi menjadi bahasa mesin yang dapat dimengerti oleh komputer.
    Compiler memproses kode program, memeriksanya untuk kesalahan sintaksis, dan menghasilkan output dalam bentuk file biner atau kode objek.
    Output ini kemudian dapat dieksekusi oleh CPU.
    
#### Peran dari sitem operasi adalah :

    Sistem operasi (OS) bertanggung jawab atas manajemen sumber daya komputer, termasuk CPU, memori, perangkat masukan/keluaran, dan jaringan.
    OS menyediakan antarmuka antara aplikasi (termasuk program yang ditulis dalam bahasa pemrograman) dan perangkat keras komputer.
    Saat program dieksekusi, OS memfasilitasi akses ke sumber daya sistem yang diperlukan, mengelola proses, dan menyediakan lingkungan yang aman dan stabil bagi eksekusi program.

2.Membaca dan memahami

3.Menjalankan VM Debian

-$ make

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/8ab13ec7-3a8b-47e6-80b7-072dd9407881)


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

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ca12c855-ee08-4b57-ba49-ffff259a9d2a)


![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f439cccc-ab93-44f1-9866-d9230e3bd5a4)

- iops64 $(nproc)3
  flops64 $(nproc)
  
  ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/6e189ddc-23b4-4b66-89fc-c5cbc0a5214e)



![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/c74ea6c0-d22e-4974-a625-329960df0d70)


  
-iops64 $(nproc)4
flops64 $(nproc)

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/a028543e-8ca8-444a-bc2c-9d195e746ef4)


-iops64 $(nproc)5
flops64 $(nproc)

   ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/1530d68b-00d9-486b-8d23-24aabda22931)


#### Perbandingan hasil iops dan flops

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ce286884-d5e8-4f3b-b349-7b0a0f257166)

#### Analisis


