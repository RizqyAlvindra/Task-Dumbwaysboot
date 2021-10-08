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
          
    * contoh `git commit -m "tugas devops git"` untuk melakukan commmit.
    
      ![commit1](https://user-images.githubusercontent.com/90166916/136317188-dfb692e2-abd1-4bce-9448-638abe65bff9.png)  
      
    * lalu masukan perintah untuk melihat apakah sudah tersimpan di database git dengan menjalankan perintah ` git status`

      ![gitcommit2](https://user-images.githubusercontent.com/90166916/136317193-62946f0b-3158-44df-b302-197e0c0af815.png)

* git remote adalah perintah git untuk membuat user terhubung ke remote repository. 
  
  `git remote -v` adalah perintah untuk menampilkan repository yang sedang konfigurasi.
     
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
    * jika sudah masukan perintah selanjutnya yaitu `git commit -m "update contoh"

      ![gitcommit](https://user-images.githubusercontent.com/90166916/136337579-1b332e52-0c75-4753-bc46-234af5a47e10.png)

    * lalu masukan perintah `git push origin contoh` .

      ![gitpushorigin](https://user-images.githubusercontent.com/90166916/136337855-6877ee99-3bef-48e0-9d35-d76e42cd4b51.png)

    * jika sudah kalian bisa masuk ke github kalian , jangan lupa untuk pindah branch dan cek file kalian.

      ![gitbranch contoh](https://user-images.githubusercontent.com/90166916/136338132-51e9597b-d3b1-4f7f-874d-0aaf876ab1f5.png)
      
 * git pull adalah perintah untuk menyamakan perubahan yang terjadi pada server git. 

    * contoh disini kalian bisa ke github lalu ke add file dan create new file .\

      ![ddd](https://user-images.githubusercontent.com/90166916/136341626-07361194-f6f7-4a9d-b0a0-a6f03d9dc878.png)

    * lalu disini saya memasukan nama file dengan `alvinnew` dan isinya adalah `Tugas DevOps Week 4` lalu tekan commit changes.

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
* contoh study case saya disini adalah ingin menambahkan suatu file yang berisi script untuk menjalankan helloworld di development untuk di kirimkan ke staging dan production.
  * Pertama tama disini saya membuat repository baru dulu di github dengan menggunakan nama studycase.
  * lalu saya membuat directory baru di terminal yaitu `git init gitcase` lalu masuk ke directory gitcase.
  * lalu saya menginstall git terlebih dahulu `sudo apt install git-y`, jika sudah bisa di cek menggunakan `ls -a`
  * lalu disini saya membuat sebuah file yang bernama `touch main.go`.
  * lalu saya membuka teks editor untuk mengisi perintah untuk menjalankan hello world.
  * 
  *  
  

   
