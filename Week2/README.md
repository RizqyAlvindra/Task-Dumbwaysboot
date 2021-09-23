# Tugas DevOps Week2

* Apa itu aplikasi :
  Aplikasi adalah sebuah perangkat lunak komputer yang melakukan fungsi spesifik secara langsung untuk pengguna akhir. Aplikasi dapat berjalan secara mandiri atau secara bersamaan dengan   sekelompok program.
  
  Untuk menjalankan aplikasi tertentu, kita memerlukan application runtime,sebelumnya apasih application runtime itu?
  jadi runtime application adalah perangkat lunak yang dirancang untuk mendukung pelaksanaan atau menjalankan program komputer yang ditulis dalam bahasa komputer.
  
  Contoh:
  
1. Menjalankan aplikasi yang dibuat dengan javascript (node.js) maka perlu install node.js
2. Menjalankan aplikasi yang dibuat dengan python maka perlu install python
3. Menjalankan aplikasi yang dibuat dengan golang maka perlu install golang

 
   contoh jika di terminal kita ingin menginstall aplikasi golang di terminal linux kita bisa menggunakan script:

* `sudo apt install golang`

# Langkah-langkah instalation Node.js  

* buka terminal (di tugas saya ini saya menggunakan terminal linux ubuntu)
* pertama download curlnya dulu `sudo apt install curl`
 
* masukkan code script `curl -o- https://raw.gitusercontent.com/nvm-sh/nvm/v0.38.0/install.sh|bash `
* jika sudah masukan `nvm use 14` untuk mengetahui node dan npm version berapa yang kalian pakai 
  
  Contoh
  ![Screenshot from 2021-09-23 17-19-48](https://user-images.githubusercontent.com/90166916/134491161-aef0880b-dbb1-42fa-ac74-8d37b69cd323.png)
* jika sudah sampai di tahap di atas instalasi Node.js telah berhasil.
* jika anda ingin mengecek anda bisa menggunakan perintah 
* `node -v`
* `npm -v`

   untuk mengetahui versi berapa yang digunakan.  
  
# Langkah-langkah membuat aplikasi sederhana menguunakan Node.js
* buatlah sebuah folder baru dengan menggunakan script `mkdir myapp-node.js`
* untuk pindah directory bisa menggunakan `cd myapp-nodejs`
* buatlah file package.json : npm init-y

  ![init1](https://user-images.githubusercontent.com/90166916/134492404-59dc098e-ea8a-4669-9d70-d23c4f621900.png)

* jika sudah bisa di cek di `ls`
* lalu selanjutnya install express : `npm install express --save`

  ![node js3](https://user-images.githubusercontent.com/90166916/134492790-ccbf3bff-836f-4086-855c-9eeaa2307807.png)
* selanjutnya masukkan script `nano index.js`
* jika sudah masukan 
  
  

