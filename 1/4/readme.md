# AWS Server for application

* pertama tama kalian bisa masuk ke terminal
* lalu masuk ke directory kalian yang ada key pair sebelumnya.
* jika sudah masuk ke server dengan cara`ssh -i dumbways.pem ubuntu@18.233.208.203`

  ![app server1](https://user-images.githubusercontent.com/90166916/138645730-0a409403-b19d-47ac-9c44-cbf12cbe7093.png)

* lalu update dan upgrade terlebih dahulu `sudo apt update` sudo apt upgrade`
* jika sudah install node.js
* `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash`
* `exec bash`
* `nvm install 14`
* `node -v` `npm -v` untuk melihat version.

  ![app server2](https://user-images.githubusercontent.com/90166916/138645727-18f91e86-2d4b-4f6c-bcf4-e738981bb68c.png)

* jika sudah selesai sekarang clone aplikasi dumbsound `git clone https://github.com/sgnd/dumbplay-frontend.git`

  ![app server3](https://user-images.githubusercontent.com/90166916/138645700-ea98ae88-b478-479e-9a6a-79288be51c96.png)

* jika sudah masuk ke directory dumbplay-frontend `cd dumbplay-frontend`

  ![app server4](https://user-images.githubusercontent.com/90166916/138645699-b959f8c9-12ad-4c15-b4b9-37dc9fc501c3.png)

* jika sudah langsung jalankan saja `npm install` dan `npm start`

  ![app server 5](https://user-images.githubusercontent.com/90166916/138645696-b0a92e9c-71c9-4efb-80db-baca3d6a5382.png)

  ![app server 6](https://user-images.githubusercontent.com/90166916/138645692-0fcc8cd0-cd83-4f0d-b3a3-3bd946e2b127.png)

* setelah semua selesai kalian bisa akses di web browser kalian lalu masukan ip server kalian lalu port si aplikasi. `18.233.208.203:3000`


  ![app server end](https://user-images.githubusercontent.com/90166916/138645687-45989596-57da-4485-991b-019ac32779e7.png)

