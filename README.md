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
Diminta agar alamat http://semerue11.pw memiliki alias http://www.semerue11.pw: \
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

### SOAL 8
Diminta untuk mengatur web server sehingga domain http://semerue11.pw memiliki DocumentRoot pada /var/www/semerue11.pw \
Pada PROBOLINGGO (web server), lakukan modifikasi pada file semerue11.pw.com \
![soal8A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/8A.png)\

### SOAL 10
Diminta agar web http://penanjakan.semerue11.pw menyimpan assets file yang memiliki DocumentRoot pada /var/www/ penanjakan.semerue11.pw \
Pada PROBOLINGGO, lakukan modifikasi pada file penanjakan.semerue11.pw.conf dengan menambahkan DocumentRoot \
![soal10A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/10A.png)\

### SOAL 13
Untuk mengakses file assets javascript awalnya harus menggunakan url http:// penanjakan.semerue11.pw /public/javascripts .
Karena terlalu panjang maka buatlah konfigurasi virtual host agar ketika mengakses file assets menjadi http://penanjakan.semerue11.pw /js . \
Pada PROBOLINGGO, lakukan modifikasi pada file penanjakan.semerue11.pw.conf dengan menambahkan Alias  \
![soal13A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/13A.jpg)\

### SOAL 14
Diminta untuk membuat web http:// naik.gunung.semerue11.pw bisa diakses hanya dengan menggunakan port 8888. \
Pada PROBOLINGGO, lakukan modifikasi pada file penanjakan.semerue11.pw.conf dengan menambahkan VirtualHost \
![Soal14A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/14A.PNG)\
Pada ports.conf, ditambahkan Listen untuk 8888\
![Soal14B](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/14B.PNG)\

### SOAL 15
Diminta agar web http://naik.gunung.semerue11.pw agar mempunyai autentikasi password dengan usernamae "semeru" dan password "kuynaikgunung"\
Pada PROBOLINGGO, file naik.gunung.semerue11.pw.conf diberi tambahan AutUserFile dll\
![Soal15A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/15A.PNG)\

### SOAL 16
Diminta agar saat mengunjungi IP PROBOLINGGO, akan dialihkan ke http://semerue11.pw \
Pada PROBOLINGGO, file \
![Soal16A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/16A.PNG)\

### SOAL 17
Diminta agar pada /var/www/ penanjakan.semerue11.pw/public/images semua request gambar dengan substring '"semeru" diarahkan menuju semeru.jpg \
Pada PROBOLINGGO, pada file .htaccess, berikan Rewrite \
![Soal17A](https://github.com/beruangsakti/Jarkom_Modul2_Lapres_E11/blob/main/Screenshoot/17A.jpg)\

## KESULITAN SELAMA PENGERJAAN
- terkadang jika kurang komunikasi, tanpa sadar ke-2 praktikan berusaha menggunakan vpn secara bersamaan
- UML terkdang mendadak tertutup sendiri karena sinyal yang kurang baik, sehingga agak memakan waktu
- adanya typo yang tidak disadari
- dll



