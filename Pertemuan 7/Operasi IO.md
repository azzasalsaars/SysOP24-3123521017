## TUGAS PENDAHULUAN

### Pendahuluan
1.Apa yang dimaksud redirection ? <br>
Redirection atau pemebelokan yang dilakukan untuk standard input,output dan error, yaitu untuk mengalihkan file descriptor dari 0, 1 dan 2	  

2.Apa yang dimaksud pipeline? <br>
Pipeline atau pipa adalah mekanisme untuk menghubungkan output dari satu perintah ke input dari perintah lain. 

3.Apa yang dimaksud perintah di bawah ini: <br>
 -Echo: Perintah yang digunakan untuk menampilkan text.
 -Cat: Perintah yang digunakan untuk melihat isi file.
 -More: Perintah uuntuk membuka file.
 -Sort: Perintah yang digunakan untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter.
 -Grep: Perintah yang digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengadung pola yang ditentukan.
 -Wc: Perintah yang digunakan untuk menghitung jumlah baris,kata dn karakter dari baris-baris masukan yang diberikan kepadanya.
 -Cut: Perintah yang digunakan untuk mengambil kolom tertentu dan baris-baris masukannya,yang ditentukan pada opinion -c.
 -Uniq: Perintah yang digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi,biasanya digabungkan dalam pipeline dengan sort.

### Percobaan Dan Hasil 

#### Percobaan  1 : File descriptor
1.	Output ke layar (standar output), input dari system (kernel)<br>

```
$ ps
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/52d0f000-5955-480e-99d1-ffb85322e093)
<br> Perintah ps digunakan untuk menampilkan proses yang sedang berjalan pada system

2.	 Output ke layar (standar output), input dari keyboard (standard input)
```
$ cat
```
Output hasil

   ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/e4eb92a1-dce2-476f-9794-c59bed570c8d)
<br> Menginputkan perintah cat yang dapat di gunkan untuk menuliskan apapun kemudian ketik Ctrl + d untuk berhenti menulis

3.	 Input dari keyboard dan output ke alamat internet
```
$ mail arna@eepis-its.edu
contoh surat yang langsung
dibuat pada standard input (keyboard)
[Ctrl-d]
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/c210b638-d525-41d9-b9be-4723381da8fa)
<br> Menginputkan perintah mail<user> yang digunakan untuk mengirim e-mail kemudian menginputkan cc,subject, dan email

4.	 Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error
maka tampilan error pada layar (standard error)
```
$ mkdir mydir
$ mkdir mydir (Terdapat pesan error)
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7f4efdf8-b73a-48bf-a948-8d6f5cff7b38)

Pertama menginputkan mkdir yang merupakan perintah untuk membuat sebuah directory,nama directorynya adalah mydir.Lalu menginputka perintah mkdir mydir dan keluar error.

#### Percobaan  2 : Pembelokan (redirection)
1.	Pembelokan standar output
```
$ cat 1> myfile.txt
Ini adalah teks yang saya simpan
Ke file myfile.txt
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/200fd96f-42c9-42ac-a7c2-40e2c3a4be04)

Menginputkan perintah cat 1> myfile.txt yang digunakan untuk menginputkan isi file yang sudah dibuat

2.	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
```
$ cat 0< myfile.txt  $ cat myfile.txt
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7c1535b9-3825-4473-9d9b-9a57962d35fa)

Menginputkan perintah cat 0< myfile.txt yang digunakan untuk membelokkan file input dari keyboard dan file sehingga antara  cat 0< myfile.txt dan myfile.txt memiliki keterkaitan.

3.	Pembelokan standar error untuk disimpan di file
```
$ mkdir mydir (Terdapat pesan error)
$ mkdir mydir 2> myerror.txt
$ cat myerror.txt
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f00b0314-cbda-414c-ab38-b03b2bbf0bd6)

Perintah mkdir mydir digunakan untuk membuat sebuah directory atau folder dengan nama mydir tetapi muncul disini muncul error karena sudah dibuat sebelumnya.Lalu perintah  mkdir mydir 2> myerror.txt  digunakan untuk membelokkan/memindahkan pesan error sebelumnya ke dalam file myerror.txt,kemudian tanda 2> itu menandakan output standar error.Selajutnya  pada perintah  cat myerror.txt digunakan untuk memunculkan teks dalam file myerror.txt yaitu berupa pesan error yang telah dibelokkan

4.	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file
descriptor 1.
```
$ ls filebaru (Terdapat pesan error)
$ ls filebaru 2> out.txt
$ cat out.txt
$ ls filebaru 2> out.txt 2>&1
$ cat out.txt
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/7b377c17-7d03-4f4b-9962-56a5bcbfa76f)

Perintah ls filebaru digunakan untuk menampilkan isi dari folder dari filebaru tetapi error karena directry file baru tidak ada . Kemudian, perintah ls filebaru 2> out.txt untuk memindahkan pesan dalam file out.txt lewat standar error yang ditandai dengan 2>. Kemudian, ls filebaru 2> out.txt 2>&1 fungsinya sama dengan cat out.txt

5.  Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file
descriptor 2 yaitu standar error
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/24c7b906-c879-487f-b874-d932c9947814)

Perintah echo “mencob menulis file” 1> baru digunakan untuk menulis kata  mencoba menulis  file” yang kemudian di pindahkan ke filebaru yang ditandai dengan >1.Lalu perintah cat filebaru 2> baru 1>&2 untuk membelokkan tampilan filebaru  ke standard output dengan tanda 1>&2 yaitu descriptor 2 standar error. 

6.	Notasi >> (append)
```
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat 
$ echo “kata keempat” > surat
$ cat surat
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f630322f-3839-4e71-88c1-40d2eb69716f)

Perintah echo “kata pertama” > surat digunakan untuk  menulis kalimat “ kata pertama”.Kemudian perintah echo “kata kedua” >> surat untuk menulis kata kedua  ke dalam file surat tanpa menghapus teks sebelumnya yang di tandai >> .Perintah echo “kata ketiga” >> surat untuk menulis kata  ketiga dalam file ssurat tanpa menghapus teks sebelumnya,kemudian teks tersebut ditampilkan dengan perintah cat surat.Selanjutnya perintah echo “kata keempat” > surat digunkan untuk menulis kata keempat tapi menghapus teks sebelumnya yaitu di tandai dengan >.kemudian perintah cat surat lagi untuk menamilkan isi file surat.

7. Notasi here document (<<++ …. ++) digunakan sebagai pembatas input dari
keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa
saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
```
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
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/f9610e62-22b3-422a-9ddc-53ae4bfb0da5)

Tanda ++..++ sebagai pembatas input dari keybard,tanda ini bisa diganti tanda apasaja asalkan pada awal dan akhirnya sama.Perintah cat <<++ kemudian menegtikkan kalimat kemudian enter maka bisa mengetikkan bebrapa kalimat lagi ,tetapi sistem akan berhenti dengan mengetikkan tanda ++ dan menampilknnya.

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya
menampilkan file 1, kemudian menampilkan input dari keyboard dan
menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari
keyboard
```
$ cat myfile.txt – surat
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/77a1c75f-a30f-45e4-bba6-e6673fa8a96b)

Digunakan untuk menampilkan isi myfile.txt sekaligus menamiplkan file surat.

9. Untuk membelokkan standart output ke file, digunakan operator >
```
$ echo hello
$ echo hello > output
$ cat output
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/95592923-0be6-4f6c-821f-e7f6bf3bf6e9)

echo hello digunakan untuk menampilkan teks  hello  di saat itu juga. Perintah echo hello > output untuk membelokkan kata hello ke file output dan perintah cat output untu menampikan isi dari file output.

10. Untuk menambahkan output ke file digunakan operator >>
```
$ echo bye >> output
$ cat output
```
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

#### Percobaan  3 : melihat siapa yang sedang aktif
1.	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
```
$ who  $ who | sort  $ who | sort –r  $ who > tmp  $ sort tmp $ rm tmp
```
Output hasil

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/97fa9835-b969-4cf0-931f-ad2cb6e2e037)

 
Perintah who digunakan untuk melihat siapa saja yang aktif.Perintah who > tmp  $untuk membelokkan output who ke file tmp. Perintah sort tmp mengurtutan baris teks dalam file tmp,dan perintah  rm tmp untuk menghapus file tmp

```
$ ls –l /etc | more
```
Output hasil

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/eae45bf8-9c8a-4866-a889-7da4843b7ea7)

Selanjutnya, untuk perintah ls -l etc digunakan untuk melihat isi dari direktori (folder) /etc dan akan di pipeline dengan tambahan perintah more dengan tujuan mempermudah untuk menggabungkan dua perintah sekaligus.
```
$ ls –l /etc | sort | more
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/1c74790e-b629-4b2e-89b2-762118428eda)

Perintah ls –l /etc | sort | more hamir sama demngan sbelumya tetapi terdapat perintah “sort” untuk mengurutkan tampilan dari siapa saja yang aktif.

#### Percobaan 4 : Filter
2.	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
```
$ w –h | grep <user>
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/167d2e27-8457-43de-b67a-51bf4614d4e4)

```
$ grep <user> /etc/passwd   $ ls /etc | wc   $ ls /etc | wc –l
```
Output hasil
 
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/61a58ed6-16a8-4b45-9f5e-0b5eb1ac29b7)

```
$ cat > kelas1.txt Badu Zulkifli Yudi Ade
[Ctrl-d] $ cat > kelas2.txt
Budi
Gama
Asep
Muchlis
[Ctrl-d]
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/80e9a8a2-ff01-44b2-8e00-70a0a7ca224c)

Perintah cat > kelas1.txt umtuk mengisi file kelas1.txt yaitu Badu
Zulkifli Yulizir Yudi Ade dan ntuk berhenti [Ctrl-d] begitu juga dengan perintah cat > kelas2.txt.
```
$ cat kelas1.txt kelas2.txt | sort
$ cat kelas1.txt kelas2.txt > kelas.txt
$ cat kelas.txt | sort | uniq
```
Output hasil

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/5f5a18ca-0ed3-4ca4-bf3e-bdec360d5ba0)

	
Perintah cat kelas1.txt kelas2.txt | sort di gunakan untuk menampilkan isi file kelas1.txt kelas2.txt dengan mengurutkan sesuai abjad yang terdahulu. Kemudian perintah cat kelas1.txt kelas2.txt > kelas.txt untuk membelokkan output ke file kelas.txt ,kemudin menampilkan file kelas.txt dengan  cat kelas.txt | sort | uniq yang mana uniq digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi,biasanya digabungkan dalam pipeline dengan sort.

### LAPORAN

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru.
-	Untuk melihat daftar direktori aktif, gunakan perintah $ ls, sedangkan untuk
membelokkan tampilan standard output ke file baru, gunakan ‘>’

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/4019b52c-ad16-4d06-90ba-834938f1ee89)

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan
standard output ke file baru tanpa menghapus file baru sebelumnya.
- Untuk melihat daftar lengkap dari direktori /etc/passwd, gunakan perntah $ ls, sedangkan
untuk membelokkan tampilan standard output ke file baru tanpa menghapus file baru
sebelumnya, gunakan ‘>>’

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/133199cf-23c4-4f39-a653-04ccc759ff88)

3.	Urutkan file baru dengan cara membelokkan standard input.
- Untuk mengurutkan file, gunakan perintah $ sort, sedangkan untuk membelokkan
standard input, gunakan ‘<’

![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/a17bcd78-f0f2-487c-a9fb-2f75d110ff42)
 
4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
- Untuk mengurutkan file, gunakan perintah $ sort, sedangkan untuk membelokkan
standard input, gunakan ‘<’, sedangkan untuk membelokkan standard output ke file,
gunakan ‘>’. Pembelokan standart input dan standart output dapat dikombinasikan
asalkan tidak boleh menggunakan nama file yang sama sebagai standart input dan output
 
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/1c335f02-d19c-4ccc-9ce9-af84daf8f0b6)

5. Buatlah direktori latihan2 sebanyak 2 kali dan belokkan standard error ke file
rmdirerror.txt.
- Gunakan perintah $ mkdir untuk membuat direktori baru. Saat membuat direktori yang
sama sebanyak dua kali, akan muncul pesan error. Pesan error itu kemudian dibelokkan
ke file dengan menggunakan ‘2>’
 
6. Urutkan kalimat berikut :
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
Dengan menggunakan notasi here document (<@@@ …@@@)
- Pertama, buat notasi here document yang akan dibelokkan ke sebuah file kemudian isi
document tersebut. Setelah diisi dan diakhiri, isi dokumen akan tersimpan ke file yang
dibelokkan. File tersebut kemudian diurutkan menggunakan perintah $ sort
 
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ac7b90fe-30f2-4652-9b6c-c12b639b39f6)

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan
filter dan tambahkan data tersebut ke file baru.
- Untuk mendapatkan jumlah baris, kata, dan karakter (secara berurutan) dari sebuah file,
gunakan perintah wc yang dipipakan dengan perintah cat. Hasilnya kemudian bisa
ditambahkan ke file menggunakan ‘>>’

 ![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ebfd712b-3d96-488e-b1d1-98428e994f2f)

8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
```
$ cat > hello.txt
dog cat
cat duck
dog chicken
chicken duck
chicken cat
dog duck
[Ctrl-d]
$ cat hello.txt | sort | uniq
$ cat hello.txt | grep “dog” | grep –v “cat”
```
-	Perintah Uniq digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan. Pola ini disebut regular expression. Salah satu regular expression dari grep adalah -v (invert0match), yang akan menampilkan baris yang
TIDAK mengandung pola yang ditentukan.
 
![image](https://github.com/azzasalsaars/SysOP24-3123521017/assets/160559457/ddcefe0d-0be1-4a9f-8b04-3b7ef8149d1a)





