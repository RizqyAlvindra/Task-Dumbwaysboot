# Setup Database

1. Pertama kalian bisa membuka aws kalian dan buat server untuk backend dan database.

   ![set up 1](https://user-images.githubusercontent.com/90166916/139522575-903e920a-4a17-449a-a605-97cc6e2c4266.png)

2. jika sudah kalian bisa buat security grup untuk database ke back end.

  ![setup 2](https://user-images.githubusercontent.com/90166916/139522632-5e1e19b1-4dee-4163-a31f-79392c10b1aa.png)

3. jika sudah kalian bisa masuk ke terminal kalian lalu masuk ke server kalian. jangan lupa untuk melakukan `sudo apt update` dan `sudo apt upgrade`
4. disini karena saya sudah men setting agar tidak usah masuk menggunakan ip saya menggunakan perintah `ssh alvin@backend` dan `ssh alvin@database`

  ![setup 3](https://user-images.githubusercontent.com/90166916/139522738-7b699303-fc17-46d1-a524-fcb3a87bed37.png)

  ![set up 4](https://user-images.githubusercontent.com/90166916/139522744-03bbc07b-1caf-4dee-9869-1468e8cd6fdc.png)

5. lalu saya melakukan clone si aplikasi backend di server backend `git clone https://github.com/sgnd/dumbplay-backend.git`
6. jika sudah selesai kalian bisa masuk ke directory yang anda clone tadi.
7. lalu baca file readme `cat README.md`
8. lalu kalian bisa install terlebih dahulu node.js kalian
   
   `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash`
   
   `exec bash`
   
   `nvm install 14`
   
9. lalu lakukan npm install.
10. jika sudah lakukan perintah seperti yang ada di readme.md 
11. disini kita install terlebih dahulu sequelize `npm install --save-dev sequelize-cli -g`
12. sebelum kita mengcopy file dumbplay.sql untuk di teruskan ke database kita harus set permissionnya pubkey dan password di server database kita `/etc/ssh/sshd.config/` terlebih dahulu menggunakan perintah nano `sudo nano /etc/ssh/sshd.config`

   ![set up 6](https://user-images.githubusercontent.com/90166916/139525789-4b7c7a47-c8d9-444c-a037-45949d5e97f7.png)
   
   disini kita harus ganti passwordautentication dari no menjadi yes.

   ![set up 7](https://user-images.githubusercontent.com/90166916/139525830-28b0a5d6-50eb-4c84-8e8a-c35ff04956f9.png)
   
   lalu hilangkan `#` dari pubkeyautentication.

14. lalu kita copy file ke server database `scp -r dumbplay.sql alvin@3.212.47.145:/home/alvin`
15. lalu copy .env `cp .env-copy .env`
16. jika sudah kita pindah ke database.
17. tekan `ls` untuk melihat file dumbplay.sql kita tadi sudah berhasil di copy disini atau belum.
   
   ![set up 5](https://user-images.githubusercontent.com/90166916/139523214-55a01d8a-befe-4759-8eda-bacc892093fe.png)

16. lalu instal terlebih dahulu mysql server

   `sudo apt install mysql-server`
   `sudo mysql_secure_installation`
   
   disini kita ikuti saja seperti petunjuk pertama tekan `yes` lalu set passwordnya low saja `0` lalu masukan password yang kalian inginkan. jika sudah tekan `yes` semua saja.
   
   lalu masuk ke `/etc/mysql` lalu ubah bind address menjadi 0.0.0.0 ` sudo nano mysql.conf.d/mysqld.cnf`
   
   ![set up database mysql](https://user-images.githubusercontent.com/90166916/139527645-3104ba36-41bb-42d3-b81f-218567559fd7.png)
   
17. jika sudah kalian bisa masuk ke root dengan menggunakan cara `sudo mysql -u root -p` lalu masukan password kalian.
18. lalu buatlah database menggunakan perintah. `CREATE databases dumplay;`
19. lalu kalian bisa cek menggunakan perintah `show databases;`

   ![set up 8](https://user-images.githubusercontent.com/90166916/139526306-d43e1668-8977-45e7-809d-cce68f792474.png)

20. lalu buat user sekalian menggunakan perintah .

   `CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';`
    *masukan user yang kalian inginkan serta masukan password yang kalian inginkan.
   
   `GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';`
    *masukan perintah ini untuk mengkonfirmasi user kalian.
    
21. jika sudah masuk ke server backend kalian .
22. lalu masuke directory config `cd config` lalu masukan user root kalian di file config.json `sudo nano config.json`

   ![set up 9](https://user-images.githubusercontent.com/90166916/139526726-f1caeb9c-e443-40f1-a2a8-0a161b8f65fb.png)
   *ganti user password seperti yang kalian buat di database lalu ganti juga host nya menjadi ip publik kalian.
   
23. jika sudah kalian bisa masukan perintah `sequelize db:migrate` di directory dumbplay-backend.
24. jika sudah selesai kalian bisa kembali ke database kalian.
25. lalu masuk ke user root kalian.
26. lalu masukan perintah `show databases;`
27. lalu masuk ke database dumbplay `use dumplay`
28. lalu masukkan `show tables` 

   ![set up 10](https://user-images.githubusercontent.com/90166916/139527765-24cd1691-9947-44e0-89bb-a28b83cec90e.png)
    dan kalian bisa lihat database sudah masuk semua.
   
