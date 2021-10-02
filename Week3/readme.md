# Tugas DevOps Week3
# Manage Server With Terminal

* Apa itu Terminal  
  Terminal adalah sebuah command prompt dimana kita bisa mengontrol suatu file,membuat folder,lalu membuat dan mengubah suatu akses,dan masih banyak lagi yang bisa kita kerjakan di terminal.
* BASH(bourne again shell)
  Bash adalah suatu bahasa yang berjalan di linux dan mempunyai fungsi sebagai penerjemah antara user dan sistem operasi.
  
  contoh jika ingin meng-install nginx maka tinggal melakukan `sudo apt install nginx` 
  
# Teks Editor Menggunakan Nano
* Teks editor adalah sebuah aplikasi yang berjalan di atas terminal, dan gunanya sendiri untuk memanipulasi data pada suatu file. dan secara default sudah ada pada sistem operasi linux. untuk memeriksanya anda bisa menggunakan perintah ` nano -- Version `

![1nano](https://user-images.githubusercontent.com/90166916/135576009-829cf636-4a71-4acb-9c26-99d1c38ca801.png)

* Cara membuka file dengan nano :
  contoh `nano alvin`

![2nano](https://user-images.githubusercontent.com/90166916/135576561-f64f63f9-bd52-49ac-ba10-52d56dcc52b6.png)
![3nano](https://user-images.githubusercontent.com/90166916/135576095-6e52428e-3fbe-4c8b-96b5-cafaf3d3c848.png)
# Macam-Macam shortcut Nano
* `ctrl X` untuk keluar dari editor.

* `ctrl O` untuk mengubah nama file , tetapi juga bisa untuk save tanpa harus mengubah nama file , tekan saja `Enter` tetapi jika menggunakan ini kalian tidak akan keluar dari editor.

![5nano](https://user-images.githubusercontent.com/90166916/135576137-56d3edee-59ba-4965-bebc-2d0cf4751c1d.png)

![4nano](https://user-images.githubusercontent.com/90166916/135576117-71d0360a-20d8-4a31-ab38-05974621f622.png)

* `ctrl W` untuk mencari teks , contoh anda ingin mencari `FROM golang` secara otomatis anda akan di arahkan ke line yang ingin anda cari.

![6nano](https://user-images.githubusercontent.com/90166916/135576156-307f1807-857e-4ad2-a7c9-317701470d12.png)

![7nano](https://user-images.githubusercontent.com/90166916/135576166-81595347-e963-49f9-9cbd-3966e260630c.png)

* `alt A` untuk memilih teks dengan cursor.

![8nano](https://user-images.githubusercontent.com/90166916/135576178-f25753b5-b2e9-4746-ac9f-ecf9308532c2.png)

* `alt 6` untuk melakukan copy teks yang sudah di pilih.

* `ctrl U` untuk melakukan paste teks yang sudah di copy tadi.

![9nano](https://user-images.githubusercontent.com/90166916/135576196-076f019f-3616-4eb5-92f3-ac83c5cb3c70.png)

* `ctrl K` untuk melakukan cut pada teks yang sudah di pilih.

![10nano](https://user-images.githubusercontent.com/90166916/135576214-edcba8ea-79e3-47e2-a263-eb81fd770ea3.png)

* `ctrl A` untuk kembali ke awal baris.

![11nano](https://user-images.githubusercontent.com/90166916/135576234-ad2cb4fa-01d3-4c1b-83be-881731c3c922.png)

* `ctrl E` untuk kembali ke akhir baris. 

![12nano](https://user-images.githubusercontent.com/90166916/135576256-e0396dfc-3089-4b00-b739-bbcd71379577.png)

# Manipulasi Teks
  sebenarnya kita bisa meng edit file di terminal tanpa menggunakan teks editor nano
* Berikut contoh perintah yang dapat di gunakan.
  1. `cat`
  2. `sed`
  3. `grep`
  4. `sort`
  5. `echo`
  
  
 Kita akan bahas satu persatu
* cat adalah suatu perintah yang dapat melihat isi dari suatu file tanpa harus membuka teks editor `nano` serta juga dapat membuat isi file pada output.
  
  Contoh penggunaan: 
  1. `cat alvin` untuk melihat isi file.

  ![cat1](https://user-images.githubusercontent.com/90166916/135578166-9701c851-5305-4d4c-afcf-ab246f06f561.png)

  2. `cat > file.alvin` untuk membuat file baru serta memasukan teks.
  
  ![cat2](https://user-images.githubusercontent.com/90166916/135578210-22847654-c2e2-42c1-9fb7-84d2b3a6bc51.png)
  
  ![cat3](https://user-images.githubusercontent.com/90166916/135578224-49090280-4a85-437e-816f-c2f7b55570dd.png)
  
  3. `cat file.alvin file.alvin2 > file.alvin3` : untuk menggabungkan 2 file serta menyimpan juga ke file ke 3.

![cat4](https://user-images.githubusercontent.com/90166916/135578240-deaf498c-8245-47a9-9454-e10387062eb8.png)

![cat5](https://user-images.githubusercontent.com/90166916/135578264-10104a8f-8cae-43a2-bf45-24139c2eae40.png)

* sed(stream editor) adalah suatu perintah yang dapat melakukan manipulasi teks dasar pada file dengan cepat.

![cat6](https://user-images.githubusercontent.com/90166916/135578282-fd617dca-da62-4266-8376-1aa7e69499a8.png)

  Contoh penggunaan:
  1. `sed -i 's/hello/holla/g' file.alvin3` untuk mengganti kata hello menjadi holla di file.alvin ke 3.

  ![sed](https://user-images.githubusercontent.com/90166916/135579279-00dae431-ff10-4bb3-8ba8-a46a2b20a1aa.png)

* grep adalah suatu perintah untuk mencari sebuah teks dalam file yang sudah di buat.

  Contoh penggunaan:
  1. `grep semarang file.alvin3` secara otomatis akan mencari kata "semarang" di file.alvin3.

  ![grep1](https://user-images.githubusercontent.com/90166916/135579349-2826d686-4e85-457f-8175-848a0fab80b6.png)

  2. `grep -c semarang file.alvin3` untuk menghitung berapa banyak sih kata "semarang" di file.alvin3.

  ![grep2](https://user-images.githubusercontent.com/90166916/135579370-0fac788d-ff49-47df-8fc3-cb52b633fc0c.png)

  3. `grep alvin * ` untuk mencari kata "alvin" di semua file.

  ![grep3](https://user-images.githubusercontent.com/90166916/135579391-8fdfb23b-3fab-40ad-a621-5f5c012d17e0.png)

 * sort adalah perintah untuk mengurutkan data secara ascending maupun descending. 

  Contoh penggunaan:
  1. `sort file .alvin3` urutan dari yang terkecil hingga terbesar.

  ![sort1](https://user-images.githubusercontent.com/90166916/135579583-eb4dbb96-ea6b-4217-9377-36fea1603306.png)

  2. `sort -r file.alvin3` urutan dari yang terbesar hingga terkecil.

  ![sort2](https://user-images.githubusercontent.com/90166916/135579593-b97feb9b-6a9d-41c2-9628-94c333bc2479.png)

* echo adalah perintah untuk mencetak pesan dari hasil perintah lain. 

  Contoh penggunaan:
  1. `echo "Semarang it's a Beautifull Place"` untuk mencetak pesan yang ingin kita buat.
  
  ![echo1](https://user-images.githubusercontent.com/90166916/135579868-93380b66-e916-4b05-ac7d-6366d310704a.png)

  
  2. `echo "hello there" >> file.alvin3` untuk menambahkan teks di file yang di tentukan.
  
  ![echo3](https://user-images.githubusercontent.com/90166916/135579874-9e1e0dae-bcb4-47a7-8c55-1d5495d118dc.png)

  
  3. `echo "goodbye" > file.alvin3` untuk me-replace semua teks yang ada di file.alvin3 dan diganti teksnya menjadi "goodbye".

  ![echo4](https://user-images.githubusercontent.com/90166916/135579885-a512e207-c842-4bd3-ba81-734c51c69b2d.png)



# Monitoring 
  Monitoring adalah mengamati kinerja sistem secara realtime.
* contoh beberapa perintah yang dapat di gunakan untuk monitoring server.
    1. htop adalah suatu perintah untuk memonitoring system,kita juga dapat melihat berapa sih penggunaan memory dan cpu yang kta pakai.
       
       Cara instalasi htop : `sudo apt install htop -y`
       
       ![htop](https://user-images.githubusercontent.com/90166916/135580276-a4d657a3-8313-477d-a307-84d29276fe21.png)

    2. lsof(list open file) adalah perintah untuk melihat seluruh isi file aktif yang sedang berjalan di sistem.

       Contoh perintah : 
                         
      1. `lsof` untuk menampilkan seluruh proses
                         
    ![lsof](https://user-images.githubusercontent.com/90166916/135583331-72c20229-d90f-491d-8c68-aae32c7cbb0f.png)
                         
      2. `lsof -u alvin` untuk menampilkan proses yang dilakukan oleh si user "alvin"
                         
     ![lsof2](https://user-images.githubusercontent.com/90166916/135583385-c59d4023-7e5c-4e14-a153-d9f27eb46e16.png)

                         
      3. `lsof -i:80` untuk menampilkan proses berjalan yang menggunakan port:80
      
      
    ![lsof3](https://user-images.githubusercontent.com/90166916/135583436-861c2606-eb1c-4a6d-9a30-0689a14dd180.png)

                          
    3. Ps (process status) adalah perintah untuk mengetahui proses yang sedang berjalan di sistem.

       Contoh perintah : 
       
       
       1.`ps -f -u alvin` adalah untuk menampilkan proses pada user "alvin"
       
       ![ps1](https://user-images.githubusercontent.com/90166916/135580559-b2642e7a-725f-4403-aaaa-01950972f620.png)
       
       2.`ps -aux` adalah untuk menampilkan semua proses secara lengkap.
    
        ![ps2](https://user-images.githubusercontent.com/90166916/135580515-171e9aaa-c696-4b3e-93b0-b4322a8f8b6f.png)
  
  # Network Firewall
  * Network Firewall adalah perintah untuk mengamankan sebuah server.
    
    Tools yang bisa digunakan adalah iptables dan ufw.
  * Network Iptable adalah sebuah tools di linux untuk memberi dukungan langsung terhadap keamanan sistem serta beberapa keperluan jaringan.tetapi Iptables juga       bisa digunakan untuk melakukan seleksi terhadap paket yang datang seperti output dan input.berdasarkan ip,port,dll.
  * Network uncomplicated firewall (ufw) adalah fitur frontend iptables pada linux untuk melakukan konfig firewall.
    *jika di sistem tidak ada ufw anda bisa melakukan instalasi dengan cara `sudo apt install ufw -y`
    
    ![ufw1](https://user-images.githubusercontent.com/90166916/135583805-69f994cd-a440-46a4-ac7e-91f940cd8467.png)

  # Macam-Macam perintah ufw 
  * `sudo ufw default deny incoming` untuk memblokir akses yang masuk.

    ![ufw2](https://user-images.githubusercontent.com/90166916/135583970-ab737923-6fb1-446b-9370-45b740c0392b.png)

  * `sudo ufw default allow outgoing` untuk membuka semua akses yang keluar.

    ![ufw3](https://user-images.githubusercontent.com/90166916/135584296-e408b3b2-c590-45d0-ae03-fa1b9ddd531d.png)
  
  * `sudo ufw app list` untuk menampilkan apk yang di dukung oleh ufw pada server.

    ![ufw4](https://user-images.githubusercontent.com/90166916/135584542-ecefb404-30ec-41b7-a704-9a2878a4f68e.png)

  * `sudo ufw allow "nginx full"` untuk mengizinkan akses dari luar ke dalam untuk apk Nginx.

    ![ufw5](https://user-images.githubusercontent.com/90166916/135584935-61e8425f-458d-45d6-94ad-3024f5b83aaa.png)

  * `sudo ufw allow 30` untuk membuka akses untuk port 30.

    ![ufw6](https://user-images.githubusercontent.com/90166916/135585868-2e9b7b5c-e904-4be9-9a36-687640f68939.png)

  * `sudo ufw allow 30/tcp` untuk membuka akses port 30 dengan koneksi tcp.
       
    ![ufw7](https://user-images.githubusercontent.com/90166916/135585923-0fd0e18a-c7c6-4ae2-913d-0b27433b3ec9.png)

  * `sudo ufw allow 30/udp` untuk membuka akses untuk port 30 dengan koneksi udp.

    ![ufw8](https://user-images.githubusercontent.com/90166916/135586216-96ec16bc-186c-4218-8bc2-f91a5054a05e.png)

  * `sudo ufw deny 40` untuk memblokir semua akses ke port 40

    ![ufw9](https://user-images.githubusercontent.com/90166916/135586437-dc4784f2-ffc2-42a1-8d95-cf93520784be.png)

  * `sudo ufw delete deny 40` untuk menghapus konfigurasi.(harus sama dengan apa yang kita ingin hapus)

    ![ufw10](https://user-images.githubusercontent.com/90166916/135586977-4023abce-7497-44dc-b43a-98cb8ea239ab.png)

 # System Perfomance 
 * System Performance berfungsi memantau server.
 * Beberapa tools :
   1. vmstat
   2. iostat
   3. nmon
 * Penjelasan Tools diatas :
  1. vm stat adalah tools untuk menampilkan penggunaan memory dan swap dan juga memberi informasi soal proses , interrupt system , kecepatan I/O dan statistik CPU secara real time , sebelumnya instal dulu `sudo apt install sysstat -y` 
  
  ![vmstat1](https://user-images.githubusercontent.com/90166916/135589829-519f9e84-0a36-4cbf-8270-4ffeb606f41f.png)
  
  * Untuk menjalankan masukan perintah `vm stat` di terminal kalian.
  
  ![vmstat2](https://user-images.githubusercontent.com/90166916/135590139-926641ec-8006-43b3-9926-f921953b05fb.png)
  
  * Gunakan vmstat `-sSM ` agar mudah dibaca.
  
  ![vmstat3](https://user-images.githubusercontent.com/90166916/135590435-9f7ea9f7-04d0-4c32-9541-e015679f1a17.png)

  * `vmstat 2 4` untuk menampilkan data "2" detik sebanyak "4" kali.
  
  ![vmstat4](https://user-images.githubusercontent.com/90166916/135590897-982bb348-01d6-45ff-803e-b013e39285b0.png)
  
  2. iostat adalah tools untuk memantau input atau output sistem, melihat berapa lama perangkat yang aktif yang kaitannya dengan kecepatan I/O. dan iostat secara default sudah ada jika kalian sudah menginstall vmstat.
  
  ![iostat1](https://user-images.githubusercontent.com/90166916/135592513-ec385f7f-bbbd-405f-a70c-d9f3426559f3.png)

  3. Nmon adalah tools untuk memonitoring dengan data yang lebih lengkap , untuk instalasi jalankan perintah ini `sudo apt install nmon -y`
  
  ![nmon1](https://user-images.githubusercontent.com/90166916/135593183-641398d7-417a-455b-9180-3d8e8b3caa6d.png)

  * jika sudah jalankan perintah `nmon`.
  
  ![nmon2](https://user-images.githubusercontent.com/90166916/135593209-51634509-091f-453a-8594-8af05043b17b.png)
 
# Penejelasan CMS Manajer
* CMS Manajer adalah platform yang dibuat untuk memudahkan pengguna yang tidak memiliki pengetahuan tentang server.,Dengan CMS Manajer kita bisa membuat server dengan mudah dan hanya klik saja.
* Dibawah ini adalah tampilan website dari CMS manajer.

  ![cms1](https://user-images.githubusercontent.com/90166916/135601830-41ccce28-ee4d-44b7-9ed2-5488b365a23d.png)

* Cara registrasi CMS Manajer Dan Membuat Aplikasi.
  1. Pertama-tama kalian bisa buka web browser dan search `cmsmanajer.com` lalu jika sudah kalian klik tombol SIGN UP di pojok kanan atas. Jika sudah kalian Nama kalian , Email , Password , Nomer Hp , Negara ,dan Pekerjaan. Jika sudah tekan create account.
  
  ![cms2](https://user-images.githubusercontent.com/90166916/135603218-223ed974-9c42-4a64-a39a-5f8fcdf0e77b.png)
  
  2. lalu kalian bisa tekan tombol Dashboard di pojok kanan atas.
  3. Jika sudah kalian bisa tekan apps dan tekan Create App

  ![cms3](https://user-images.githubusercontent.com/90166916/135603495-e8a8d9e2-24e1-4860-953b-7d36ab31a0a2.png)

  4. Lalu pilih kalian ingin membuat app apa, disini ada banyak pilihan

  ![cms4](https://user-images.githubusercontent.com/90166916/135603735-6e400c02-e745-4136-b21d-a3d2b24ee316.png)

  5. Contoh disini saya ingin membuat aplikasi Docker.lalu langsung saja tekan create

  ![cms5](https://user-images.githubusercontent.com/90166916/135603884-a8658651-593e-4b0a-b0b3-d2cf5d9d242b.png)

  6. Lalu tunggu saja. pembuatan tidak terlalu lama tergantung internet masing-masing.
  
  ![cms6](https://user-images.githubusercontent.com/90166916/135604233-0740c8e0-2bea-439f-b966-da8b5bbd49e2.png)

  7. Jika sudah cek di app dan sudah jadi.
  
  ![cms7](https://user-images.githubusercontent.com/90166916/135604634-aa959049-5a1c-4da7-9a86-a6e8497fa0d0.png)
  
  ![cms8](https://user-images.githubusercontent.com/90166916/135604656-a59e43cf-a6ab-4320-8e63-e4fb3faee90e.png)

# Cara menghubungkan server di CMS Manajer
* Ke Dashboard lalu tekan Connect Server.
* Disini kalian bisa memilih web server yang ingin digunakan.atau jika belum tau ingin menggunakan web server yang mana kalian bisa memilih i'll choose later.
* Kemudian ada Server Name . Tulis saja nama server yang ingin kalian gunakan.
* Kemudian ada Ip Address isi Ip address yang sudah ditentukan masing masing

  ![cms9](https://user-images.githubusercontent.com/90166916/135605394-4a0eb7ac-a236-4cb7-841a-dd051c236bc0.png)
 
* Lalu centang ssh key jika kalian ada code ssh untuk digunakan.

  ![cms10](https://user-images.githubusercontent.com/90166916/135606898-c685d06b-0122-4af5-87c2-5a069afacbd2.png)

* jika tidak bisa lanjutkan ke tahapan selanjutnya yaitu password.
* Jika sudah tunggu sampai pembuatan selesai
* jika sudah selesai akan otomatis masuk ke dasboard dengan nama server yang kalian tentukan tadi.

![cms12](https://user-images.githubusercontent.com/90166916/135607279-36a34aa4-72b8-409e-9dd0-bc2f7dfb026a.png)

![cms11](https://user-images.githubusercontent.com/90166916/135607316-10a4b81d-ff12-4286-b4ce-433c3b67a279.png)
