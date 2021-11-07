# Create Docker images 

1. untuk membuat Docker images ada beberapa cara,
2. yaitu kalian bisa mengambil docker images yang sudah ada di https://hub.docker.com 
3. atau membuat sendiri sesuai aplikasi yang kalian inginkan 

Contoh Disini saya akan memberi contoh 2 cara.
# Cara pertama membuat images dari docker hub.

* pertama-tama kalian bisa masuk ke server kalian.
* jika sudah pastikan di server anda sudah meng instalasi Docker.
* jika sudah kalian bisa buka web https://hub.docker.com 
* lalu kalian silahkan buat akun kalian dengan cara tekan sign.up.
* lalu masukan username yang kalian inginkan serta email beserta password yang kalian inginkan.
* jangan lupa untuk verfikasi im not a robot.

![dockerimg1](https://user-images.githubusercontent.com/90166916/140635358-d46d242e-130d-4aff-becb-0343b35d9d59.png)

* jika sudah masuk ke terminal kalian lalu masukkan perintah `docker login` lalu masukan id pass yang sudah kalian buat tadi.

![dockerimg2](https://user-images.githubusercontent.com/90166916/140635457-95f04d79-daf0-491f-8696-d8f73e1bc802.png)

* jika sudah kalian bisa kembali ke dockerhub kalian lalu cari saja image yang kalian perlukan.
* disini kita akan mencoba mencari `node.js` 

  ![dockerimg4](https://user-images.githubusercontent.com/90166916/140635659-1f3e26a2-feef-4acb-b22b-65476262431e.png)

* lalu tekan saja bagian tags.
* setelah itu cari images yang kalian inginkan.
* contoh saja disini saya ingin menggunakan `node:lts-apline3.14`

  ![dockerimg5](https://user-images.githubusercontent.com/90166916/140635658-e810e235-1e61-4063-9ff5-7efe132c294d.png)

* jika sudah copy aja perintah yang ada di dockerhub `docker pull node:lts-alpine3.14`
* jika sudah selesai cek menggunakan perintah `sudo docker images`

  ![dockerimg3](https://user-images.githubusercontent.com/90166916/140635668-68ee418b-316d-4576-95da-0fecb29ed9fb.png)
# Cara kedua membuat image kita sendiri

* disini saya ingin membuat images saya sendiri 
* kalian hanya tinggal menggunakan perintah `sudo docker build --tag (name):version lalu tambahkan titik .`
  
  `sudo docker build --tag backend:14 .`
  
* jika sudah kalian bisa cek menggunakan perintah 

  `sudo docker images` 
  
  ![dockerimg6](https://user-images.githubusercontent.com/90166916/140636148-6d4f9378-3a47-48cd-a414-410554071434.png)
