# Tugas DevOps Week2.

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

# Langkah-langkah instalasi Node.js  

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
  
# Langkah-langkah membuat aplikasi sederhana menggunakan Node.js
* buatlah sebuah folder baru dengan menggunakan script `mkdir myapp-node.js`
* untuk pindah directory bisa menggunakan `cd myapp-nodejs`
* buatlah file package.json : npm init-y

  ![init1](https://user-images.githubusercontent.com/90166916/134492404-59dc098e-ea8a-4669-9d70-d23c4f621900.png)

* jika sudah bisa di cek di `ls`
* lalu selanjutnya install express : `npm install express --save`

  ![node js3](https://user-images.githubusercontent.com/90166916/134492790-ccbf3bff-836f-4086-855c-9eeaa2307807.png)
* selanjutnya masukkan script `nano index.js`
* jika sudah masukan: 
  
  ![nano](https://user-images.githubusercontent.com/90166916/134495071-1a2fbe34-f897-41f2-b7bd-6f8bd8c1e822.png)
* lalu simpan menggunakan `ctrl+x`
* kemudian tekan `y` lalu `enter`
* kemudian jalan kan dengan menggunakan perintah `node index.js`
  
  ![node js5](https://user-images.githubusercontent.com/90166916/134495621-ebb84835-1d1e-4590-87eb-c813c2a7ade2.png)
 
 * jika sudah buka web browser: `http://localhost:5000`

   ![Screenshot from 2021-09-23 15-45-10](https://user-images.githubusercontent.com/90166916/134496119-c4fff108-b64b-497f-af10-69cd24e9ec22.png)
   
# Langkah-langkah instalasi python3
* buka terminal lalu lakukan update terlebih dahulu dengan menggunakan script `sudo apt upgrade`
* lalu update juga sistem kalian `sudo apt upgrade -y`
* python sudah ada secara default : `python3 -v`
* lalu install package managernya : `sudo apt install python3 -pip`
* lalu instal flask : `sudo apt install python3-flask`

# Langkah-langkah membuat aplikasi sederhana dengan python3.
* seperti sebelumnya buatlah folder terlebih dahulu : `mkdir-python`
* pindah directory dengan : `cd python`
* lalu buat file index.py : `nano index.py`
* jika sudah masukan:

  ![Screenshot from 2021-09-23 15-47-22](https://user-images.githubusercontent.com/90166916/134497882-21429a8b-171d-4510-8d84-71a9db558816.png)

* lalu jalankan aplikasi : `python3 index.py`
  
  ![python11](https://user-images.githubusercontent.com/90166916/134502080-ed8df0cb-cbb4-4ce9-b89c-1f9ad1341b87.png)
* terakhir buka browser :`https://127.0.0.1:5000/`
  
  ![pythonfinish](https://user-images.githubusercontent.com/90166916/134502265-9493564d-4da1-42e5-9127-ac65f2a812ac.png)
  
# Langkah-langkah instalasi go/golang
* buka terminal lalu langsung saja instalasi go dengan cara `sudo apt install golang`
* lalu verifikasi versi go dengan cara : `go version`
  
  ![golang2](https://user-images.githubusercontent.com/90166916/134502817-bc1388fb-64f0-4fbd-8eb7-c92341efec83.png)
  
# Langkah-langkah membuat aplikasi sederhana dengan go/golang.
* buka terminal 
* lalu sama seperti sebelum-sebelumnya,buat lah folder terlebih dahulu.: `mkdir golang-app`
* lalu pindah directory :`cd golang-app`
* lalu buat sebuah file dengan : `nano index.go`
* jika sudah masukan:

  ![gogogo](https://user-images.githubusercontent.com/90166916/134504530-6dca15cf-0d28-4ce7-b748-2f426363bdc2.png)

* lalu jalankan aplikasinya : `go run index.go`

  ![golang4](https://user-images.githubusercontent.com/90166916/134505658-3d18b3cf-e9d2-44a4-8a8f-96c8967d8779.png)
  
* jika ingin di build : `go build index.go`

  ![golang5](https://user-images.githubusercontent.com/90166916/134505688-a24651e7-5b94-4b13-b8bb-664837e9729a.png)
  


