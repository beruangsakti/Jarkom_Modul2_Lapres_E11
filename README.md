# Jarkom_Modul2_Lapres_E11

# SOAL

Semeru adalah salah satu gunung yang terkenal di Jawa Timur. Bibah adalah salah satu juru kunci
Semeru. Bibah ingin menyebarkan keindahan Semeru pada dunia sehingga dia membeli 3 buah server
yang berada di MALANG , MOJOKERTO dan PROBOLINGGO . Server MALANG akan digunakan
sebagai DNS Server Master, MOJOKERTO akan digunakan sebagai DNS Server Slave dan
PROBOLINGGO akan digunakan sebagai Web Server. Selain 3 server terdapat 2 klien yang digunakan
untuk testing oleh Bibah yaitu GRESIK dan SIDOARJO . Untuk menyambungkan semua jaringan
tersebut Bibah memberi router di SURABAYA .

### SOAL 1
Diminta untuk membuat sebuah website utama dengan alamat http://semeruyyy.pw , dimana yyy pada alamat diganti sesuai nama kelompok, sehingga menjadi http://semerue11.pw :\
Pada UML MALANG(DNS server master), file semerue11.pw diisikan seperti pada gambar \
![soal1A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/1A.PNG)\
Pada client (GRESIK dan SIDOARJO), dilakukan setting terhadap nameserver dengan merubah isi file resolv.conf dengan cara mengetikkan ```nano /etc/resolv.conf``` pada masing-masing client dan isikan nameserver diikuti IP MALANG\
![soal1B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/1B.PNG)\
Setelah itu, dapat dilakukan pengetesan dengan cara melakukan ping terhadap semerue11.pw
![soal1C](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/1C.PNG)


### SOAL 2
Diminta agar alamat http://semerue11.pw memiliki alias http://www.semerue11.pw:\
Kembali pada UML MALANG, file semerue11 diberi modifikasi tambahan CNAME untuk mengatur alias, seperti pada gambar:\
![soal2A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/2A.PNG)\
Lakukan pengecekan dengan melakukan ping\
![soal2B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/2B.PNG)\


### SOAL 3
Diminta agar alamat http://semerue11.pw memiliki subdomain http://penanjakan.semerue11.pw
yang diatur DNS-nya pada MALANG dan mengarah ke IP Server PROBOLINGGO:\
Pada UML MALANG, file semerue11.pw diberi modifikasi tambahan lagi, seperti pada gambar:\
![soal3A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/3A.PNG)\
Alamat IP yang ditambahkan pada gambar adalah alamat IP milik PROBOLINGGO.\
Dilakukan pengecekan dengan melakukan ping ke penanjakan.semerue11.pw.\
![soal3B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/3B.PNG)\


### SOAL 4
Diminta membuat reverse domain untuk domain utama:\
Pada UML MALANG, dilakukan penambahan konfigurasi untuk reverse domain pada file /etc/bind/named.conf.local \
![soal4A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/4A.PNG)\
Masih pada UML Malang, isikan file 71.151.10.in-adrr.arpa sebagai berikut\
![soal4B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/4B.PNG)\
Setelah dilakukan reset, dapat dilakukan tes pada Client untuk mengetahui apakah pengaturan sudah benar\
![soal4C](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/4C.jpg)\


### SOAL 5
Diminta agar MOJOKERTO dijadikan DNS Server Slave:\
Pada MALANG, /etc/bind/named.conf.local diberi tambahan pada bagian dalam zone "semerue11.pw" \
![soal5A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/5A.PNG)\
Pada MOJOKERTO, /etc/bind/named.conf.local dibuat sesuai pada gambar berikut \
![soal5B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/5B.PNG)\
Untuk melakukan testing, matikan MALANG terlebih dahulu\
![soal5C](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/5C.PNG)\
Pada file /etc/resolv.conf milik Client, diberi tambahan seperti pada gambar untuk setting terhadap nameserver \
![soal5D](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/5D.PNG)\
Lakukan tes dengan melakukan ping terhadap semerue11.pw\
![soal5E](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/5E.PNG)\
Ping dapat dilakukan meskipun MALANG telah dimatikan

### SOAL 6
Diminta membuat subdomain dengan alamat http://gunung.semerue11.pw yang didelegasikan pada MOJOKERTO dan mengarah ke IP Server PROBOLINGGO:
Pada MALANG, file /etc/bind/jarkom/semerue11.pw diberi modifikasi\
![soal6A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/6A.PNG)\
Masih pada MALANG, dilakukan modifikasi pada file /etc/bind/named.conf.options\
![soal6B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/6B.PNG)\
Pada MOJOKERTO, edit file /etc/bind/named.conf.local dengan menambahkan zone baru\
![soal6C](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/6C.PNG)\
Pada MOJOKERTO, edit file /etc/bind/delegasi/gunung.semerue11.pw \
![soal6D](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/6D.PNG)\
Dilakukan pengecekan dengan cara melakukan ping dari Client\
![soal6E](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/6E.PNG)\



