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
12. lalu kita copy file ke server database `scp -r dumbplay.sql alvin@3.212.47.145:/home/alvin`
13. lalu copy .env `cp .env-copy .env`
  
 
