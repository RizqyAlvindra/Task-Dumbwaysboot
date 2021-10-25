# AWS SSL Confiiguration

* Masuk ke Dashboard Cloudflare
* Lalu tekan profil
* Setelahnya masuk ke API TOKENs

  ![ssl1](https://user-images.githubusercontent.com/90166916/138695650-29c67888-9e5a-4c0d-b16a-b4e0001e19d0.png)


* Lalu tekan saja Global IP key lalu masukan pass kalian dan konfimasi saya bukan robot.
* Lalu akan keluar API key kalian

  ![ssl2](https://user-images.githubusercontent.com/90166916/138695641-87dc1b14-b26c-4c03-9e0c-bce96b90ec5e.png)

* lalu masuk server kalian.
* lalu buat folder .cloudflare `mkdir .cloudflare` 
* setelah itu buat file untuk memasukan email dan API key kalian. `sudo nano API key`

  ![ssl3](https://user-images.githubusercontent.com/90166916/138695639-d5dfa680-a2d3-4e15-931b-1415a5ff794b.png)


* setelah itu masukan perintah `sudo chmod400 API key`
* jika sudah kita langsung installasi Certbot `sudo snap install --classic certbot`

  ![ssl4](https://user-images.githubusercontent.com/90166916/138695635-fc9fabc9-d823-44ca-99a6-11e81fbd61a1.png)

* `sudo ln -s /snap/bin/certbot /usr/bin/certbot`

  ![ssl5](https://user-images.githubusercontent.com/90166916/138695634-cc645d77-6e31-4fd4-82fe-04e41b30005a.png)

* lalu masukan perintah `sudo certbot` disini kalian diminta untuk memasukan email kalian dan memilih file mana yang akan kalian aktifkan dengan https

  ![ssl6](https://user-images.githubusercontent.com/90166916/138695630-ed5a8afb-6f9b-4c2d-9eb5-e5310dc3cf33.png)

* jika sudah selesai semua masuk ke folder /etc/nginx/dumbsound `cd /etc/nginx/dumbsound`
* lalu cek file kalian maka configurasi kalian akan berubah secara otomastis. `cat alvin.onlincecamp.id`

  ![ssl7](https://user-images.githubusercontent.com/90166916/138695626-887d01cc-7655-4f04-96f5-fe33e63de6cd.png)


* jika sudah cek `sudo nginx -t` untuk melihat apakah ada syntax yang eror.

![ssl8](https://user-images.githubusercontent.com/90166916/138695623-c2166af4-8354-4075-b4db-1270b6bce8a9.png)

* terakhir buka web browser https://alvin.onlinecamp.id 

![sslend](https://user-images.githubusercontent.com/90166916/138695619-72603709-74a3-4bcf-8c73-9a85409df7bf.png)


