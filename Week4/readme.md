# Tugas DevOps Week4
# Dokumentasi Proses Tiap Perintah Git

* Sebelum pembahasan dimulai jika kalian belum menginstall git di terminal kalian, kalian bisa install terlebih dahulu menggunakan perintah `sudo apt install git -y`


![gitins](https://user-images.githubusercontent.com/90166916/136250623-52bcb77a-ea00-4e1b-aad3-0281c0c6d97c.png)


jika sudah selesai kalian bisa mengecek git kalian menggunakan perintah `git --version`.


![gitver](https://user-images.githubusercontent.com/90166916/136250661-5f58f50d-3644-4e36-9c3a-8ed033d2b5ee.png)

* git config adalah suatu perintah git untuk mengatur suatu konfigurasi tertentu seusai keinginan pengguna. contoh seperti membuat username,email.
  contoh perintah git untuk mengatur usename dan email.
    * `git config --global user.name"alvin"` perintah ini untuk mengatur nama dari user.
    * `git config --global user.email"rizqyalvindra@gmail.com"` perintah ini untuk mengatur email dari si user.
    * lalu jika sudah kalian bisa menggunakan perintah `git config --list` untuk melihat user dan email yang kalian pakai.
    
    
         ![gitlist](https://user-images.githubusercontent.com/90166916/136250885-3fb3a348-56e5-4b18-9bb2-a9d567a6ceba.png)

    
* Konfigurasi SSH key untuk github:
    * buat sebuah ssh key dengan menjalankan perintah `ssh-keygen`.
    * kemudian jalankan perintah `cat~/.ssh/id_rsa.pub` untuk melihat ssh key kalian.
    
    ![sshgit](https://user-images.githubusercontent.com/90166916/136309443-cd0067f5-b795-4838-9667-842a71a8ff92.png)

    
    * lalu copy ssh key yang muncul dan masukan ke dalam config github dengan membuka github,lalu tekan profil, lalu pergi ke setting, lalu pilih ssh and gpg keys, lalu tekan saja new ssh dan masukan ssh key yang tadi kalian copy. lalu add ssh key.

        ![sshkey](https://user-images.githubusercontent.com/90166916/136310234-166a3d70-08c4-4310-b5f6-28735ce86618.png)

    * jika sudah kalian bisa cek di setting lalu ke menu yang tadi ssh and gpg keys , maka ssh keys akan secara otomatis masuk ke profil kalian.

        ![sshkey2](https://user-images.githubusercontent.com/90166916/136310252-bad354ed-400f-4ea8-9249-3ea02597aa22.png)

    * lalu kalian bisa cek di terminal dengan menggunakan perintah `ssh -T git@github.com` maka akan keluar seperti ini 
      
        ![ssh t](https://user-images.githubusercontent.com/90166916/136310015-fabad379-36cd-42f4-af22-2030dec042be.png)
* git init adalah suatu perintah git untuk membuat repository baru.
    * contoh disini saya akan membuat repositry "alvin" yaitu perintahnya `git init alvin`
      
      ![gitinit1](https://user-images.githubusercontent.com/90166916/136311339-e1e62c90-8c5a-423d-8c5d-abe1800187a6.png)
      
      ![gitinit2](https://user-images.githubusercontent.com/90166916/136311349-3a3792c6-db1f-43f7-be7d-5f0dd5309c5a.png)
      
* git ignore adalah sebuah file yang berisi daftar nama nama file/directory yang akan diabaikan oleh git.
    * contoh disini saya membuat beberapa file.
    
      ![gitignore3](https://user-images.githubusercontent.com/90166916/136314998-d4dd99d2-29cd-496a-95ab-12d3e1e1417a.png)
      
      ![gitignorels](https://user-images.githubusercontent.com/90166916/136315058-9457d048-7458-478f-98ce-ca0d575e9511.png)

    * lalu kalian masukan perintah `nano .gitignore` lalu saya akan memasukan `alvin2` untuk mengabaikan alvin2 oleh git.

      ![ignore2](https://user-images.githubusercontent.com/90166916/136312678-d40aae34-2bee-42cf-8044-33268d9784cc.png)
      
    * lalu kalian bisa menggunakan perintah git status untuk melihat daftar file
       
      ![gitignore4](https://user-images.githubusercontent.com/90166916/136314839-77760037-9138-44f6-8812-badc1613a6af.png)
     
* git add adalah perintah untuk menambahkan file ke index
    * contoh `git add .` untuk melakukan staged pada semua file ( kecuali yang terdaftar pada gitignore).
    
      ![gitadd1](https://user-images.githubusercontent.com/90166916/136316527-bf16f29f-379e-4f41-9347-85ae48b9eccd.png)
      
      ![gitadd](https://user-images.githubusercontent.com/90166916/136316239-afc36c5b-e567-4e66-b679-3371707e2b7e.png) 

* git commit adalah perintah untuk melakukan commit pada perubahan ke head
          
    * contoh `git commit -m "tugas devops git"` untuk melakukan commit.
    
      ![commit1](https://user-images.githubusercontent.com/90166916/136317188-dfb692e2-abd1-4bce-9448-638abe65bff9.png)  
      
    * lalu masukan perintah untuk melihat apakah sudah tersimpan di database git dengan menjalankan perintah ` git status`

      ![gitcommit2](https://user-images.githubusercontent.com/90166916/136317193-62946f0b-3158-44df-b302-197e0c0af815.png)

* git remote adalah perintah git untuk membuat user terhubung ke remote repository. 
  
  `git remote -v` adalah perintah untuk menampilkan repository yang sedang konfigurasi.
  
  ![gitremote-v](https://user-images.githubusercontent.com/90166916/136683316-60f72efb-cedd-45fa-aed2-838f7d2a1714.png)
  
     
    * Contoh disini kita akan melakukan remote pada layanan github.
    * pertama tama kalian buat repository github disini saya menggunakan nama tugasdevopsweek4
    * masukan deskripsi contoh disini saya menggunakan diskripsi try perintah git.
    * lalu tentukan repository yang ingin kalian gunakan publik atau private 
    * kemudian klik create repository
      
      ![create repository](https://user-images.githubusercontent.com/90166916/136318945-043830b3-f37c-4c7c-99b3-cd2ebbcdb4f5.png)
     
    * lalu jika proses membuat repository telah selesai, jalankan perintah `git branch -M main`
    * lalu masukan perintah `git remote add origin git@github.com:RizqyAlvindra/tugasdevopsweek4.git`
    * lalu `git push -u origin main`  
    * disini perintah saya gabungin semua dan setiap setelah perintah di tambahkan `;`
      
      ![git remote2](https://user-images.githubusercontent.com/90166916/136319968-bcbfbac3-fbbb-404c-a299-70f8087cf7f5.png)
      
    * setelah semua step telah selesai silahkan cek di github kalian masing-masing.
    
      ![sss](https://user-images.githubusercontent.com/90166916/136333008-bd11a5bd-a2e7-44ea-93ab-790166a8d046.png)
      
* git branch adalah sebuah perintah untuk membuat versi dari sebuah repository. di lapangan perintah seperti ini digunakan untuk membuat versi Development , Staging ,dan Production., untuk menghapus branch yang nanti akan kalian buat kalian bisa menggunakan perintah `git branch -d branch-name`.
* git checkout adalah sebuah perintah untuk perpindahan branch.
* git push adalah sebuah perintah mengupload data yang ada pada database git lokal ke databese git di server.
    * contoh disini saya ingin membuat branch dengan nama "contoh". ` git branch contoh ` lalu untuk melihat list lokasi anda dan branch apa saja yang ada kalian bisa menggunakan perintah `git branch -a`

      ![git brnch1](https://user-images.githubusercontent.com/90166916/136335979-ec40a152-3679-4167-9a16-d248dc302797.png)
      
    * lalu bagaimana cara memindah isi file di branch main ke contoh dan bagaimana cara push nya?
    * caranya dengan menggunakan perintah `git checkout contoh` j
    * jika sudah kalian bisa menggunakan perintah ` git branch -a ` untuk melihat lokasi anda sekarang.
      
      ![git checkout](https://user-images.githubusercontent.com/90166916/136336686-8ff3208f-65e4-457c-8098-ac8aadd580d0.png)
      
    * lalu masukan perintah ` git add . `
    * jika sudah masukan perintah selanjutnya yaitu `git commit -m "update contoh"`

      ![gitcommit](https://user-images.githubusercontent.com/90166916/136337579-1b332e52-0c75-4753-bc46-234af5a47e10.png)

    * lalu masukan perintah `git push origin contoh` .

      ![gitpushorigin](https://user-images.githubusercontent.com/90166916/136337855-6877ee99-3bef-48e0-9d35-d76e42cd4b51.png)

    * jika sudah kalian bisa masuk ke github kalian , jangan lupa untuk pindah branch dan cek file kalian.

      ![gitbranch contoh](https://user-images.githubusercontent.com/90166916/136338132-51e9597b-d3b1-4f7f-874d-0aaf876ab1f5.png)
      
 * git pull adalah perintah untuk menyamakan perubahan yang terjadi pada server git. 

    * contoh disini kalian bisa ke github lalu ke add file dan create new file .\

      ![ddd](https://user-images.githubusercontent.com/90166916/136341626-07361194-f6f7-4a9d-b0a0-a6f03d9dc878.png)

    * lalu disini saya memasukan nama file dengan `alvin` dan isinya adalah `Tugas DevOps Week 4` lalu tekan commit changes.

      ![newfile git](https://user-images.githubusercontent.com/90166916/136341617-9648c5d7-a876-4956-81e2-c4c44409d18b.png)
      
    * jika sudah masuk ke terminal lalu masukan perintah `git pull origin contoh` 

      ![gittpull](https://user-images.githubusercontent.com/90166916/136340685-24f85b89-4d38-4bf8-9a72-5324693af3ab.png)
      
 * git clone adalah perintah untuk mengambil repository.
  * contoh disini saya ingin mengambil repository dari tliron untuk mengganti tema linux.
      ![gitclone2](https://user-images.githubusercontent.com/90166916/136345291-d40486fa-4acd-45cd-b8b4-876fc926e114.png)
     * pertama tama kalian masukan perintah seperti ini `git clone https://github.com/tliron/install-gnome-themes ~/install-gnome-themes`
      ![gitclone1](https://user-images.githubusercontent.com/90166916/136345282-46923f37-4b26-4202-a353-25e7288409f9.png)
     * lalu jika kalian ingin melanjutkan bagaimana cara menginstall theme ini silahkan buka web berikut https://github.com/tliron/install-gnome-themes. karna di sini saya hanya ingin menjelaskan bagaimana cara menggunakan `git clone`.
 * git status adalah untuk menampilkan daftar file yang berunah bersama dengan file yang ingin ditambahkan atau di-commit.
     * `git status` 
     
        ![gitstatus](https://user-images.githubusercontent.com/90166916/136347273-7e69841b-0531-410b-8b56-7f6dc557ad25.png) 
      
 * `git rm` adalah perintah untuk menghapus file dari index dan directory kerja. contoh `git rm (lalu masukan nama file yang ingin kalian hapus)`
   
   ![rmgit](https://user-images.githubusercontent.com/90166916/136348162-749f633e-d6ca-40fb-9a5d-853cd1e57304.png)

 * `git show` adalah untuk menampilkan informasi tentang object pada git.

   ![gitshow](https://user-images.githubusercontent.com/90166916/136348560-5fbed485-f613-4e65-bfe4-f748385287bf.png)

 * `git ls-tree HEAD` untuk menampilkan susunan object berdasarkan nama dan mode setiap sistem dan nilai blob SHA-1 .

   ![githead](https://user-images.githubusercontent.com/90166916/136483758-a9049f78-2519-463d-bc68-0a1701f897d9.png)
   
 * git merge adalah perintah untuk menggabungkan sebuah branch ke brach yang aktif.


# Buatlah study case melakukan git merge dari branch development ke staging kemudian production.
* contoh study case saya disini adalah ingin menambahkan suatu file yang berisi script untuk menjalankan helloworld di main untuk di kirimkan ke develpoment, staging dan production.
  * Pertama tama disini saya membuat repository baru dulu di github dengan menggunakan nama studycase.

    ![studycase1](https://user-images.githubusercontent.com/90166916/136515493-690e06d7-0824-4d9a-9204-90b403842c7b.png)


  * lalu saya membuat directory baru di terminal yaitu `git init gitcase` .

    ![studycase2](https://user-images.githubusercontent.com/90166916/136515510-999069a8-69b0-409c-b4e1-b3742de6b580.png)


  * lalu masuk ke directory yang kalian buat tadi `cd gitcase`.

    ![studycase3](https://user-images.githubusercontent.com/90166916/136515527-e0ab8915-1591-4f01-9535-01c9fc03121d.png)


  * lalu saya menginstall git terlebih dahulu `sudo apt install git-y`, jika sudah bisa di cek menggunakan `ls -a`
  
    ![studycase4](https://user-images.githubusercontent.com/90166916/136515530-e2b291a2-e3fb-4c4d-be74-ee4314a63e56.png)
   
    ![studycase5](https://user-images.githubusercontent.com/90166916/136515533-cde82866-3d15-476a-b48a-ab9e7350c54d.png)

  
  * lalu disini saya membuat sebuah file yang bernama `touch main.go`.
  
    ![studycase6](https://user-images.githubusercontent.com/90166916/136515534-f7e79ca6-78f2-4648-963d-a105638d629d.png)
 
  
  * lalu saya membuka teks editor untuk mengisi perintah untuk menjalankan hello world.
  
    ![studycase7](https://user-images.githubusercontent.com/90166916/136515535-4152aab9-c75c-420e-8fcb-b33b4729091d.png)
  
  * masukan `git status` untuk melihat daftar file.
  
    ![studycase8](https://user-images.githubusercontent.com/90166916/136515539-8156f844-89f5-4fb4-b2ae-124ce59b22a4.png)
  
  * jika sudah masukan perintah `git add .` untuk menambahkan file ke index.
  
    ![studycase9](https://user-images.githubusercontent.com/90166916/136515540-27c8479f-b3d4-4612-a94d-9ba9da6cb6e7.png)
  
  * lalu bisa di cek menggunakan `git status` 
  
    ![studycase10](https://user-images.githubusercontent.com/90166916/136515541-1b5ca863-60fc-40b1-a29c-4cf86b648b6d.png)

  
  * `git commit -m "studycase"` untuk melakukan commit.
  
    ![studycase11](https://user-images.githubusercontent.com/90166916/136515547-87500bde-87c7-42a2-883e-9a9eacae8059.png)
  
  * lalu cek lagi menggunakan `git status`.
  
    ![studycase12](https://user-images.githubusercontent.com/90166916/136515548-85bf75b5-89b8-42d7-91e1-a6c95b8acd2c.png)

  
  * lalu disini saya membuat branch yang bernama `main` dengan `git branch -m main`
  
    ![studycase13](https://user-images.githubusercontent.com/90166916/136515553-38b5cd1a-d0ee-48e4-ba89-ee93176138d7.png)
  
  * lalu saya menggunakan git remote untuk menghubungkan user ke remote repository `git remote add add origin git@github.com:RizqyAlvindra/studycase.git`.
  
    ![studycase14](https://user-images.githubusercontent.com/90166916/136515555-cc6c0b47-055f-4cf3-9502-bdb5bc6834a3.png)
  
  * pertama tama disini saya push terlebih dahulu branch main `git push -u origin main` .
  
    ![studycase15](https://user-images.githubusercontent.com/90166916/136515557-09023c2d-dd79-4616-98ed-bd6139036f8f.png)

  
  * setelahnya saya membuat beberapa branch. yaitu Development , Staging ,dan Production.
  
    ![studycase16](https://user-images.githubusercontent.com/90166916/136515561-89805b3c-1f04-434a-b6fa-a2f449fc99a0.png)
  
  * untuk mengecek bisa menggunakan `git branch -a` untuk melihat daftar branch apa saja yang ada.
  
    ![studycase17](https://user-images.githubusercontent.com/90166916/136515564-36996d5b-0f8b-4477-bc12-ac8c90e6ca6d.png)
  
  * lalu disini saya pindah branch terlebih dahulu menggunakan `git checkout Staging`
  
    ![studycase18](https://user-images.githubusercontent.com/90166916/136515568-e13d07a0-1528-451a-b0ed-94f28039d6d2.png)

  
  * lalu saya menggunakan git merge untuk menggabungkan sebuah branch ke branch aktif. `git merge Development` , `git merge Staging` ,dan `git merge Production`.
  
    ![studycase19](https://user-images.githubusercontent.com/90166916/136515573-58911152-725c-468c-a5e0-95807485b921.png)

    ![studycase20](https://user-images.githubusercontent.com/90166916/136515577-4e8c46e8-edba-427a-9722-9636bf09dfe3.png)

    ![studycase21](https://user-images.githubusercontent.com/90166916/136515584-52674bfa-c40b-42a7-bb9d-ed6598af11ea.png)
  
  * jika sudah, saya akan push satu-persatu. `git push origin Development` , `git push origin Staging` ,dan `git push origin Production`.
  
    ![studycase22](https://user-images.githubusercontent.com/90166916/136515589-7bf874fb-897b-4225-b45f-eef7777db6cc.png)

    ![studycase23](https://user-images.githubusercontent.com/90166916/136515593-292b9aa3-6511-4540-bd85-32862e36413d.png)

    ![studycase24](https://user-images.githubusercontent.com/90166916/136515595-5ff35ab3-68d7-446f-9474-2db907febbac.png)
  
  * jika sudah selesai kalian bisa cek di github kalian,lalu cek di masing masing branch ,dan semua branch sudah ada file `main.go` . 
    
    ![studycase25](https://user-images.githubusercontent.com/90166916/136515597-5a11e16f-e965-4c6f-8784-e6da39132755.png)

    ![studycase26](https://user-images.githubusercontent.com/90166916/136515601-91ac4abc-ae45-47d8-93a0-9c1547cd42c0.png)

    ![studycase27](https://user-images.githubusercontent.com/90166916/136515602-ad7446d1-5fba-436c-a83f-25b77aa1ad93.png)


# Buatlah dokumentasi reverse proxy berdasarkan aplikasi yang telah dibuat pada minggu ke 2.
  * pertama tama disini saya install terlebih dahulu multipass `sudo snap install multipass`
  
    ![al1](https://user-images.githubusercontent.com/90166916/136653544-d4213c85-fd16-4a00-a15b-f4214725b7ac.png)

  * lalu saya membuat server dengan nama alvin menggunakan perintah `multipass launch --name alvin`
  
    ![al2](https://user-images.githubusercontent.com/90166916/136653675-8913a11b-1df0-4e80-a253-35e47971b7f1.png)

  * jika sudah bisa cek dengan menggunakan perintah `multipass ls`
  
    ![al3](https://user-images.githubusercontent.com/90166916/136653768-d67932ec-b9c7-4457-bc83-83fa8c17a127.png)   
  
  * setelahnya bisa masuk ke server dengan menggunakan perintah `multipass shell alvin`

    ![al4](https://user-images.githubusercontent.com/90166916/136653840-04ee8c59-4776-4693-ab26-84c0f038590d.png)

  * lalu install nginx terlebih dahulu. `sudo apt install nginx`
  
    ![al5](https://user-images.githubusercontent.com/90166916/136653889-8d908841-31c6-4b9a-96c6-7dc5f16b8533.png)
  
  * `sudo systemctl status nginx` untuk melihat status nginx.
  
    ![al6](https://user-images.githubusercontent.com/90166916/136653964-036c4171-5d2d-4f7e-abf8-074f4ae193dc.png)
  
  * lalu masuk sistem dengan cara ` cd /etc/nginx/ ` lalu disini saya membuat directory dengan nama nodejs-week2 `mkdir nodejs-week2`.
  
    ![al7](https://user-images.githubusercontent.com/90166916/136654133-9b763d34-f056-47e2-a020-d115312d3d48.png)  
  
    ![al8](https://user-images.githubusercontent.com/90166916/136654140-df3964f3-38cb-469f-9212-c109d7fe320e.png)
  
  * jika sudah masuk ke teks editor `sudo nano nginx.conf` lalu beri tambahan di bagian include dengan `include /etc/nginx/node-week2/*;` jika sudah lalu keluar dengan menggunakan `ctrl X` lalu tekan `Y` dan `Enter`.
  
    ![al9](https://user-images.githubusercontent.com/90166916/136654385-e0b07246-c7ee-4654-9119-73b84f55c013.png)
  
  * selanjutnya adalah masuk ke dalam drirectory nodejs-week2 , lalu masukan perintah `sudo nano tugas` dan masukan script seperti contoh di bawah.
    
    ![al10](https://user-images.githubusercontent.com/90166916/136654516-bcda31cb-8837-45dd-8aa0-c23286d1e600.png)

    ![al11](https://user-images.githubusercontent.com/90166916/136654520-0a381b15-096e-4986-be36-7fae0dec7477.png)
    
  * jika sudah lalu keluar menggunakan `ctrl X` lalu tekan`Y` setelah itu`Enter` untuk keluar.
  * lalu keluar dari directory `cd` lalu masukan perintah `sudo nano /etc/hosts` . lalu tambahkan ip local kalian dan nama server kalian tadi (domainprivate.xyz)
  
    ![al12](https://user-images.githubusercontent.com/90166916/136654664-8c8a046f-23bb-44be-b676-5189c1eb66c5.png)
  
  * jika sudah buat file index.js `nano index.js` dan masukan script seperti tugas minggu ke 2. 
  
  ![al13](https://user-images.githubusercontent.com/90166916/136654750-8252f6a0-3198-4f0c-b8a0-95c7a2673d03.png)
  
  * lalu download terlebih dahulu node.js nya `curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -` lalu `sudo apt-get install -y nodejs`. lalu bisa cek menggunakan `node -v`
  
    ![al14](https://user-images.githubusercontent.com/90166916/136654802-249a6340-af67-4599-bf37-59a9d2d5323c.png)
  
    ![al15](https://user-images.githubusercontent.com/90166916/136654874-b0abafb8-8db8-428d-a512-0c5dc38c8bba.png)
  
    ![al16](https://user-images.githubusercontent.com/90166916/136654876-1ea7354d-3c2d-449f-8113-96a73d02da20.png)
    
  * lalu restart nginx `sudo systemctl restart nginx` 

    ![al17](https://user-images.githubusercontent.com/90166916/136654992-ecff17b9-3487-483b-8584-9fe19f84357a.png)

  * lalu kalian bisa melihat nginx kalian dengan cara buka web browser lalu masukan name server tadi yatu `domainprivate.xyz`

    ![proxy2](https://user-images.githubusercontent.com/90166916/136655134-82b76fc8-84a9-4b08-a0f1-ac235ef28bcd.png)

  * lalu untuk menjalankan apk tadi jalankan perintah `node index.js` 

    ![al18](https://user-images.githubusercontent.com/90166916/136655213-8e605797-acb2-4a00-9570-db5cd317a99e.png)

  * jika sudah cek web browser dengan memasukan ip server anda terlebih dahulu lalu portnya `10.206.130.237:5000`

    ![proxy3](https://user-images.githubusercontent.com/90166916/136655138-771575e9-d4b5-493f-bc33-2bc07bea5fcd.png)

  * lalu terakhir tambah lagi di tab browser kalian dan masukan `domainprivate.xyz:5000`

    ![proxy1](https://user-images.githubusercontent.com/90166916/136655111-90e30d14-ec1f-41a6-a408-8a8d5aae75e2.png)


