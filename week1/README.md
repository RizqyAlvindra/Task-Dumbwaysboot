# Alvin
TUGAS WEEK 1 DevOps
# Penjelasan 

* Deskripsi DevOps : DevOps adalah Kombinasi dari Development dan Operation yang bertugas sebagai penghubung antara divisi Development dan Operation untuk mempercepat rilis suatu produk ke publik.




* GitHub : Berfungsi sebagai Layanan berbasis cloud yang dapat menyimpan dan mengelola kode,serta mendokumentasikan dan mengontrol perubahanya.(Git HUb adalah contoh tools dari Source Code Management).



* Jenkins : Jenkins merupakan tools CI/CD berbasis open source yang berfungsi untuk mengotomasi perkerjaan yang dilakukan secara berulang (dalam tugas DevOps week 1 ini saya memilih jenkins sebagai contoh tools CI/CD dalam gambaran alur kerja DevOps yang saya buat)



# Penjelasan Basic Network :


Basic Network : adalah koneksi antara 2 komputer ataupun lebih yang saling terhubung bisa menggunakan kabel maupun nirkabel.

*Jenis-jenis jaringan Basic Network:

* PAN (Personal Area Network) : adalah jaringan komunikasi antar perangkat yang sangat dekat. (contoh kita menghubungkan laptop kita dengan hotspot di HP kita)

* LAN (Local Area Network) : adalah jaringan komunikasi yang hanya mencangkup wilayah kecil. (contoh jaringan internet Sekolah, Kampus, dan Kantor).,Dalam tugas DevOps week satu ini Local Area network adalah jenis jaringan yang digunakan dalam tugas saya.

* MAN (Metropolitan Area Network) : adalah jaringan komunikasi yang mencangkup wilayah provinsi.(contoh kantor yang memiliki beberapa kantor cabang).

* WAN (Wide Area Network) : adalah jaringan wirelles yang menggunakan sarana satelit.(contoh Bank internasional).


# Type Jaringan:

* Jaringan Client-Server : Server adalah Komputer yang menyediakan fasilitas bagi komputer-komputer lain di dalam suatu jaringan. client adalah komputer-komputer yang menerima atau menggunakan fasilitas yang di sediakan oleh server (dalam Tugas DevOps week 1 ini Jaringan client-server adalah jaringan yang tepat untuk gambaran flow saya dibawah)

* Jaringan Peer To Peer : jaringan ini tidak seperti client server , peer to peer lebih ke semua komputer yang terhubung dapat bertindak sebagai client maupun server.(antar terkoneksi)


* Ip Address(internet protocol address) : ip address adalah serangkain angka milik satu perangkat yang terhubung ke jaringan yang lebih luas. agar bisa saling bertukar informasi antar satu sama lain.(Dalam tugas DevOps week 1 ini jenis ip address yang saya gunakan adalah ip address publik , agar bisa berkomunikasi dengan jaringan yang lebih luas dan tidak perlu menggunakan VPN)



* Topology : suatu metode yang dapat menghubungkan antara satu komputer dengan komputer lainnya,serta bisa terhubung menggunakan kabel maupun nirkabel.(Dalam tugas DevOps week 1 ini mungkin jenis topology yang saya buat seperti gambar di bawah adalah topology mesh karena semuanya harus saling terkoneksi dan terhubung.)


* sebelumnya apasih topology mesh ? topology mesh adalah topology yang menerapkan semua server harus saling terkoneksi secara terpusat.dengan kata lain setiap node pada jaringan akan saling terhubung karena menggunakan kabel yang langsung menuju node yang dituju.(sedikit note node adalah titik titik yang menghubungkan antar perangkat) 
* di bawah ini adalah contoh topology mesh : 

![ddd](https://user-images.githubusercontent.com/90166916/134140951-4038ab88-e364-42f8-b816-65fb39327bef.jpg)

* gambaran carakerja nya sama seperti contoh alur kerja DevOps yang saya buat di bawah ini.

# Berikut Contoh Gambaran alur kerja DevOps yang saya buat :


![Alur Kerja DevOps](https://user-images.githubusercontent.com/90166916/133399577-0e92a41f-9d05-4cd1-9589-f07b104925b2.PNG)



* Penjelasan Terkait Gambar di Atas :


 Dimulai dengan Planning yang ingin dibuat contoh ingin membuat suatu aplikasi yand dapat membantu seorang pelajar menjadi dapat belajar secara mandiri, lalu ditentukanlah kita menginginkannya dengan fitur apa.Contoh kita menginginkan Ada dasbord untuk mengetahui apasih tujuan dari aplikasi ini ,lalu ada dapat melihat Jadwal materi apa saja yang akan di pelajari hari ini,,Ada absensi check in untuk perharinya,side Tugas,lalu meminta untuk ada notifikasi saat ada absensi terlambat maupun notifikasi tugas,Ratting kelas,dll.
Lalu kita akan meneruskan ke para Para Progammer untuk meng coding apa yang kita inginkan sesuai planning.Jika sudah para Progammer akan diminta untuk mengupload apa yang dia kerjakan ke GitHub agar bisa Sampai ke Tahapan selanjutnya yaitu CI/CD. Disini saya Memilih contoh toolsnya yaitu Jenkins. Nah saat sampai di CI/CD ini ada yang namanya Build,Testing,dan Deploy.





Nah saat procces CI/CD ini coding akan di test apakah ada kesalahan atau tidak.Contoh jika ada kesalahan maka Secara automatic CI/CD tidak akan meneruskan ke tahapan selanjutnya. Nah disini para Progammer akan Diberi tahu dan akan mengulang kembali jika ada kesalahan.Dan mengirim kembali ketahapan CI/CD jika sudah selesai di benarkan.Lalu jika coding tidak ada masalah sama sekali. Maka akan di release kemudian akan di teruskan ke deploy,lalu aplikasinya jalan ke cloud.Kemudian jika aplikasi sudah jalan di cloud Kita akan mengoprasikannya(operate).Seperti saat di planning Melihat apakah sudah ada yang mengerjakan tugas,absensi check in,dll.
setelah itu masuk ke tahapan terkahir yaitu Monitoring. disini kita seperti namanya monitoring kita akan memantau aplikasi ini. Apakah telah sesuai dengan yang kita expetasikan saat planning atau belum. serta di monitoring ini kita dapat memantau apakah ada bug atau tidak(menganalisa apakah terjadi eror atau tidak pada sistem aplikasi).,Jika ada maka akan di beritahukan ke tahapan semula ke Progammer agar meng fix bug tersebut.


# Revisi Tambahan 

* Source Code Management(SCM): adalah salah satu tools yang sering digunakan para development.yang memiliki kemampuan untuk mengatur perubahan dan konfigurasi dari suatu aplikasi.dibawah ini adalah contoh tools nya yaitu GIT


![gitimg](https://user-images.githubusercontent.com/90166916/134264435-8ea2d849-4dcf-43e8-86dc-e4021a96313f.png)\

Git merupakan salah satu contoh tools dari Source Code Management. Dengan menggunakan git para developer bisa merubah dan memeriksa kode mereka, serta mereka bisa melakukan VCS (Version Control System) untuk menambahkan versi baru, serta dapat kembali ke versi sebelumnya.


* Container Management Tools : adalah manajemen kontainer yang mengacu pada serangkaian praktik yang mengatur dan memelihara perangkat lunak. contoh toolsnya adalah Docker.

![dockerimg2](https://user-images.githubusercontent.com/90166916/134264866-b5c04b32-920a-462a-ba48-db81b7310856.png)

Docker merupakan container(wadah) untuk menyatukan berbagai file software dan pendukung lainya.Dengan menggunakan docker container ini sangat memungkinkan para developer dapat mengisolasikan kode ke dalam satu wadah sehingga dapat membantu developer umtuk memodifikasi dan memperbarui program tersebut.

Gambaran cara kerja ip address. (alur kerja DevOps)

Gambaran saya cara kerja ip address : dalam suatu perusahaan yang sudah jadi seperti gambar di atas pasti semua tahapan memiliki ip address contoh,komputer yang menyimpan data saat planning memilik ip address 192.168.1.10 nah saat ingin memberikan data planning itu ke para progammer pasti meiliki komputer yang memiliki ip berbeda contoh para komputer progammer memiliki ip 192.168.1.11., komputer yang menyimpan data planning ingin mengirimkan data tersebut kepada para progammer untuk di kerjakan menjadi sebuah codding.lalu pada saat kompter planning ingin mengirimkan data tersebut otomatis komputer di planning harus mengetahui ip para progmammer itu lalu jika sudah di verivikasi lalu bisa dikirimkan selama ada internet.(mungkin bisa dikatakan jenis ip ini adalah ip address statis , Karena dalam satu kantor)


OSI (open system inteconection) adalah : sebuah konsep dimana lapisan lapisan di komputer/koneksi komputer :


![OSI](https://user-images.githubusercontent.com/90166916/134108727-8ee71495-761b-4287-98b9-da94465d738e.jpg)


Penjelasan Gambar di atas :

* Physical : adalah untuk mendifinisikan media transmisi jaringan. contoh perangkat nya seperti wireless,fiber optik,hubs dll

* Data Link : adalah contoh perangkat keras seperti ethernet,switch dll

* Network : adalah menentukan jalur terbaik melalui jaringan.(ip address)

* Transport : adalah type koneksi yang mendukung komunikasi antara beragam perangkat di berbagai jaringan seperti TCP/UDP

* Session : adalah untuk data ataupun port 

* Presentation : mempunyai fungsi untuk mentranslasikan format data yang akan ditransmisikan oleh aplikasi melalui jaringan, ke dalam format yang dapat ditransmisikan oleh sebuah jaringan

* Application Layer : adalah lapisan pusat terjadinya interaksi antar pengguna(end user)., dengan aplikasi yang bekerja menggunakan fungsionalitas sebuah jaringan.


TCP/IP Concept : TCP adalah Transmision Control Protocol. sedangkan ip seperti yang kita tahu adalah Internet Protocol. kedua ini di jadikan satu karena fungsinya akan saling bekerja sama.


Berikut Contoh Gambar konsep TCP/IP :


![model tcp](https://user-images.githubusercontent.com/90166916/134110367-72ad93ce-8568-42b9-9714-ca3c66b31661.jpg)

* Network access : jaringan yang mengakses perangkat keras dan media yang membentuk suatu jaringan.
* Internet : menentukan jalur terbaik melalui jaringan internet(IP Address)
* Transport : type koneksi yang mendukung komunikasi antar beragam perangkat di berbagai jaringan.
* Application : mewakili data kepada pengguna ditambah pengkodean dan kontrol.







 
