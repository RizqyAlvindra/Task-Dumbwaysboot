# INSTALLATION GIT AND SSH KEY

* Untuk instalasi GIT kalian bisa menggunakan perintah `sudo apt install git -y`

  ![gitins](https://user-images.githubusercontent.com/90166916/139239769-2af2fbe0-3615-4d0e-96f2-58fa22c2d8c4.png)

* Dasar-dasar perintah git
  
  * git config adalah suatu perintah git untuk mengatur suatu konfigurasi tertentu seusai keinginan pengguna. contoh seperti membuat username,email. contoh perintah git untuk mengatur username dan email. 
    
    `git config --global user.name"alvin"`
    
    `git config --global user.email"rizqyalvindra@gmail.com`
    
    `git config --list`

   ![gitlist](https://user-images.githubusercontent.com/90166916/139241935-d7bd2a69-edea-4c78-b2cd-3f00cb72f70a.png)

  * git init adalah perintah git untuk membuat sebuah repository.

    `git init example`
    
   ![git1](https://user-images.githubusercontent.com/90166916/139241638-4a830a07-69bb-410b-893d-95462c66a5ed.png)
 
  * git add adalah perintah untuk menambahkan file ke index.

    `git add *namafile*`
    
    ![git2](https://user-images.githubusercontent.com/90166916/139245496-c815e4a9-40af-4be2-bd3f-ce3e632d2c54.png)

    `git add .` . untuk menandakan semua. 
    
  * git commit adalah perintah untuk melakukan commit pada perubahan ke head
 
    `git commit example`
    
    ![git4](https://user-images.githubusercontent.com/90166916/139246681-a5c4d755-01a0-4206-8e6a-79ef94a1f257.png)

  * git status adalah untuk menampilkan daftar file yang berunah bersama dengan file yang ingin ditambahkan atau di-commit.

    `git status` 
    
    ![git3](https://user-images.githubusercontent.com/90166916/139245905-9f1bfb54-8e5b-4c61-8a82-1c77591a6c57.png)

  * git clone adalah perintah untuk mengclone sebuah repository.

    `git clone https://github.com/sgnd/dumbplay-backend.git ../dumplay-backend`

    ![git5](https://user-images.githubusercontent.com/90166916/139247884-3c6c68d5-84ae-4b21-b8f0-daf4c621efb0.png)

  * git remote adalah perintah git untuk membuat user terhubung ke remote repository.
    
    sebelumnya kalian bisa membuat repository baru di github kalian , lalu jalankan saja seperti yang ada di github.
    
    ![git6](https://user-images.githubusercontent.com/90166916/139363261-8d6e176f-ce52-4262-a2a0-e9b20f1dcec9.png)

    ![git7](https://user-images.githubusercontent.com/90166916/139363265-817dd796-618d-4eab-9cce-0294ab4ff965.png)

    `git remote -v`
    
    `git remote add origin git@github.com:RizqyAlvindra/example.git`  
    
  * git push adalah sebuah perintah mengupload data yang ada pada database git lokal ke databese git di server.

    `git push origin *nama branch`
    
    ![git8](https://user-images.githubusercontent.com/90166916/139363480-889b5774-c6d6-4711-ad8e-88be10c41c4c.png)

  * Jika sudah kalian bisa refresh repository github kalian.

    ![git9](https://user-images.githubusercontent.com/90166916/139363633-fb7ff0b5-24f2-4b62-b185-cefd7c2896ff.png)

  * git branch adalah sebuah perintah untuk membuat versi dari sebuah repository. 

    `git branch *nama-branch-yang-ingin-digunakan.`
    
    `git branch staging`
    
    `git branch -a`
    
    ![git10](https://user-images.githubusercontent.com/90166916/139366320-70f9d452-7187-487c-8547-e106a41b8216.png)

  * git merge adalah perintah untuk menggabungkan sebuah branch ke brach yang aktif.
  
    ![git11](https://user-images.githubusercontent.com/90166916/139366947-7e99f5e0-67c8-47cb-8237-ea1872d1a07d.png)


