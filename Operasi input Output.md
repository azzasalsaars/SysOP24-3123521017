## TUGAS PENDAHULUAN

1.	Apa yang dimaksud redirection ?
Redirection atau pemebelokan yang dilakukan untuk standard input,output dan error, yaitu untuk mengalihkan file descriptor dari 0, 1 dan 2	  

2.	Apa yang dimaksud pipeline?
Pipeline atau pipa adalah mekanisme untuk menghubungkan output dari satu perintah ke input dari perintah lain. 

3.	Apa yang dimaksud perintah di bawah ini:
Echo: Perintah yang digunakan untuk menampilkan text.
 
 Cat: Perintah yang digunakan untuk melihat isi file.
 
 More: Perintah uuntuk membuka file.
 
 Sort: Perintah yang digunakan untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter.
 
 Grep: Perintah yang digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengadung pola yang ditentukan.
 
 Wc: Perintah yang digunakan untuk menghitung jumlah baris,kata dn karakter dari baris-baris masukan yang diberikan kepadanya.
 
 Cut: Perintah yang digunakan untuk mengambil kolom tertentu dan baris-baris masukannya,yang ditentukan pada opinion -c.
 
 Uniq: Perintah yang digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi,biasanya digabungkan dalam pipeline dengan sort.

## PERCOBAAN DAN HASIL 

#### Percobaan  1 : File descriptor
1.	Output ke layar (standar output), input dari system (kernel)
$ ps

Output hasil

   ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/52d0f000-5955-480e-99d1-ffb85322e093)


Perintah ps digunakan untuk menampilkan proses yang sedang berjalan pada system

2.	 Output ke layar (standar output), input dari keyboard (standard input) $ cat
Output hasil

   ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/e4eb92a1-dce2-476f-9794-c59bed570c8d)

Menginputkan perintah cat yang dapat di gunkan untuk menuliskan apapun kemudian ketik Ctrl + d untuk berhenti menulis

3.	 Input dari keyboard dan output ke alamat internet
$ mail arna@eepis-its.edu
contoh surat yang langsung
dibuat pada standard input (keyboard)
[Ctrl-d]
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/c210b638-d525-41d9-b9be-4723381da8fa)

Menginputkan perintah mail<user> yang digunakan untuk mengirim e-mail kemudian menginputkan cc,subject, dan email

4.	 Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error
maka tampilan error pada layar (standard error)
$ mkdir mydir
$ mkdir mydir (Terdapat pesan error)

Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7f4efdf8-b73a-48bf-a948-8d6f5cff7b38)

Pertama menginputkan mkdir yang merupakan perintah untuk membuat sebuah directory,nama directorynya adalah mydir.Lalu menginputka perintah mkdir mydir dan keluar error.

#### Percobaan  2 : Pembelokan (redirection)
1.	Pembelokan standar output
$ cat 1> myfile.txt
Ini adalah teks yang saya simpan
Ke file myfile.txt
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/200fd96f-42c9-42ac-a7c2-40e2c3a4be04)

Menginputkan perintah cat 1> myfile.txt yang digunakan untuk menginputkan isi file yang sudah dibuat

2.	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
$ cat 0< myfile.txt  $ cat myfile.txt
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7c1535b9-3825-4473-9d9b-9a57962d35fa)

Menginputkan perintah cat 0< myfile.txt yang digunakan untuk membelokkan file input dari keyboard dan file sehingga antara  cat 0< myfile.txt dan myfile.txt memiliki keterkaitan.

3.	Pembelokan standar error untuk disimpan di file
$ mkdir mydir (Terdapat pesan error)  $ mkdir mydir 2> myerror.txt       $ cat myerror.txt
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f00b0314-cbda-414c-ab38-b03b2bbf0bd6)

Perintah mkdir mydir digunakan untuk membuat sebuah directory atau folder dengan nama mydir tetapi muncul disini muncul error karena sudah dibuat sebelumnya.Lalu perintah  mkdir mydir 2> myerror.txt  digunakan untuk membelokkan/memindahkan pesan error sebelumnya ke dalam file myerror.txt,kemudian tanda 2> itu menandakan output standar error.Selajutnya  pada perintah  cat myerror.txt digunakan untuk memunculkan teks dalam file myerror.txt yaitu berupa pesan error yang telah dibelokkan

4.	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file
descriptor 1.
$ ls filebaru (Terdapat pesan error)
$ ls filebaru 2> out.txt
$ cat out.txt
$ ls filebaru 2> out.txt 2>&1
$ cat out.txt
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7b377c17-7d03-4f4b-9962-56a5bcbfa76f)

Perintah ls filebaru digunakan untuk menampilkan isi dari folder dari filebaru tetapi error karena directry file baru tidak ada . Kemudian, perintah ls filebaru 2> out.txt untuk memindahkan pesan dalam file out.txt lewat standar error yang ditandai dengan 2>. Kemudian, ls filebaru 2> out.txt 2>&1 fungsinya sama dengan cat out.txt

5.  Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file
descriptor 2 yaitu standar error
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/24c7b906-c879-487f-b874-d932c9947814)

Perintah echo “mencob menulis file” 1> baru digunakan untuk menulis kata  mencoba menulis  file” yang kemudian di pindahkan ke filebaru yang ditandai dengan >1.Lalu perintah cat filebaru 2> baru 1>&2 untuk membelokkan tampilan filebaru  ke standard output dengan tanda 1>&2 yaitu descriptor 2 standar error. 

6.	Notasi >> (append)
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat 
$ echo “kata keempat” > surat
$ cat surat
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f630322f-3839-4e71-88c1-40d2eb69716f)

Perintah echo “kata pertama” > surat digunakan untuk  menulis kalimat “ kata pertama”.Kemudian perintah echo “kata kedua” >> surat untuk menulis kata kedua  ke dalam file surat tanpa menghapus teks sebelumnya yang di tandai >> .Perintah echo “kata ketiga” >> surat untuk menulis kata  ketiga dalam file ssurat tanpa menghapus teks sebelumnya,kemudian teks tersebut ditampilkan dengan perintah cat surat.Selanjutnya perintah echo “kata keempat” > surat digunkan untuk menulis kata keempat tapi menghapus teks sebelumnya yaitu di tandai dengan >.kemudian perintah cat surat lagi untuk menamilkan isi file surat.

7. Notasi here document (<<++ …. ++) digunakan sebagai pembatas input dari
keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa
saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
$ cat <<++
Hallo, apa kabar ?
Baik-baik saja ?
Ok!
++
$ cat <<%%%
Hallo, apa kabar ?
Baik-baik saja ?
Ok!
%%%
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f9610e62-22b3-422a-9ddc-53ae4bfb0da5)

Tanda ++..++ sebagai pembatas input dari keybard,tanda ini bisa diganti tanda apasaja asalkan pada awal dan akhirnya sama.Perintah cat <<++ kemudian menegtikkan kalimat kemudian enter maka bisa mengetikkan bebrapa kalimat lagi ,tetapi sistem akan berhenti dengan mengetikkan tanda ++ dan menampilknnya.

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya
menampilkan file 1, kemudian menampilkan input dari keyboard dan
menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari
keyboard
$ cat myfile.txt – surat
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/77a1c75f-a30f-45e4-bba6-e6673fa8a96b)

Digunakan untuk menampilkan isi myfile.txt sekaligus menamiplkan file surat.

9. Untuk membelokkan standart output ke file, digunakan operator >
$ echo hello
$ echo hello > output
$ cat output
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/95592923-0be6-4f6c-821f-e7f6bf3bf6e9)

echo hello digunakan untuk menampilkan teks  hello  di saat itu juga. Perintah echo hello > output untuk membelokkan kata hello ke file output dan perintah cat output untu menampikan isi dari file output.

10. Untuk menambahkan output ke file digunakan operator >>
$ echo bye >> output
$ cat output
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/077e8529-67b1-4827-ac17-48a0c40789fb)

-Perintah echo bye >> output digunakan untuk menambahkan teks bye ke file output yang di tandai dengan >> , dan perintah cat output untuk menmpilkan isi file output.

11. Untuk membelokkan standart input digunakan operator <
$ cat < output
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/9a736368-cf41-4eff-a8f8-1fd9feae9d68)

Perintah cat < output digunakan untuk membelokkan standard input dari file output. Ternyata, perintah tersebut mempunyai fungsi yang sama dengan perintah cat output pada nomor sebelumnya.

12. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak
boleh menggunakan nama file yang sama sebagai standart input dan output.

Output  hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/e79d4169-99cc-41e3-a238-49833f206864)

Perintah cat < output > out dan cat out merupakan perintah yang digbumngkan untuk membelokkan standard output dari file output menjadi standard input untuk file out sehingga hasil standard output‐nya sama. Selanjutnya, perintah cat < output >> out digunakan untuk membelokkan standard output dari file output menjadi penambahan output ke file yang bernama out. Sehingga, output dari file out akan ditambahkan dengan output dari file output. Selanjutnya perintah cat output >> out, cat out, cat < output > output, cat output, cat < out >> out tidak ada output karena menggunakan nama file yang sama.
