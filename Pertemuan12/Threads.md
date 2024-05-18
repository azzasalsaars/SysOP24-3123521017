## TUGAS THREADS

### 1. Contoh Pemrograman di Mana Multithreading Memberikan Performa Lebih Baik daripada Solusi Single-Threaded

Jawaban:
<br>
a. Server web yang melayani setiap permintaan dalam thread terpisah.<br> 
b. Aplikasi terparallelisasi seperti perkalian matriks di mana bagian-bagian berbeda dari matriks dapat dikerjakan secara paralel.<br>
c. Program GUI interaktif seperti debugger di mana satu thread digunakan untuk memantau input pengguna, thread lain mewakili aplikasi yang sedang berjalan, dan thread ketiga memantau performa.

### 2. Apa Dua Perbedaan Antara User-Level Threads dan Kernel-Level Threads? Dalam Keadaan Apa Salah Satu Tipe Lebih Baik dari yang Lain?

Jawaban:
<br>
a. User-level threads tidak diketahui oleh kernel, sedangkan kernel mengetahui kernel threads.<br>
b. Pada sistem yang menggunakan pemetaan M:1 atau M:N, user threads dijadwalkan oleh thread library dan kernel menjadwalkan kernel threads.<br> 
c. Kernel threads tidak perlu dikaitkan dengan suatu proses, sedangkan setiap user thread merupakan bagian dari suatu proses. Kernel threads umumnya lebih mahal untuk dipelihara daripada user threads karena harus diwakili dengan struktur data kernel.

### 3. Jelaskan Tindakan yang Diambil oleh Kernel untuk Melakukan Context-Switch antara Kernel-Level Threads

Jawaban:
<br>
Context switching antara kernel threads biasanya memerlukan penyimpanan nilai register CPU dari thread yang sedang dialihkan dan pemulihan register CPU dari thread baru yang dijadwalkan.

### 4. Sumber Daya Apa yang Digunakan Ketika Sebuah Thread Dibuat? Bagaimana Mereka Berbeda dari Sumber Daya yang Digunakan Ketika Sebuah Proses Dibuat?

Jawaban:
<br>
Karena sebuah thread lebih kecil daripada sebuah proses, pembuatan thread biasanya menggunakan lebih sedikit sumber daya daripada pembuatan proses. Membuat sebuah proses memerlukan pengalokasian blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file yang terbuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan pengalokasian struktur data kecil untuk menyimpan set register, stack, dan prioritas.

### 5. Misalkan Sebuah Sistem Operasi Memetakan User-Level Threads ke Kernel Menggunakan Model Many-to-Many dan Pemetaan Dilakukan Melalui LWPs. Selain Itu, Sistem Mengizinkan Pengembang Membuat Real-Time Threads untuk Digunakan dalam Sistem Real-Time. Apakah Penting untuk Mengikat Sebuah Real-Time Thread ke LWP? Jelaskan.

Jawaban:
<br>
Timing sangat krusial untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak diikat ke LWP, thread tersebut mungkin harus menunggu untuk diikat ke LWP sebelum berjalan. Pertimbangkan jika sebuah real-time thread sedang berjalan (terikat ke LWP) dan kemudian terblokir (misalnya harus melakukan I/O, telah di-preempt oleh real-time thread dengan prioritas lebih tinggi, menunggu kunci eksklusi mutual, dll.). Sementara real-time thread terblokir, LWP yang terikat padanya telah ditugaskan ke thread lain. Ketika real-time thread dijadwalkan untuk berjalan lagi, ia harus menunggu terlebih dahulu untuk diikat ke LWP. Dengan mengikat LWP ke real-time thread, Anda memastikan bahwa thread tersebut dapat berjalan dengan penundaan minimal setelah dijadwalkan.
