# Frontend and Reverse Proxy ubuntu server
   Sebelumnya apa sih reverse proxy itu ?
  
   Jadi Reverse Proxy merupakan sebuah fitur/modul di dalam sebuah webserver, yang berfungsi untuk melakukan port forwarding suatu request, dari public request menuju ke dalam sistem.
  
   Ditugas mingguan kali ini kita mendapatkan tugas untuk mendeploy aplikasi dumbsound di server yang telah kita buat tadi.
  
1. Frontend dumbsound  
  
 * pertama tama kalian bisa buka terminal kalian lalu kalian bisa masuk ke server yang tadi sudah kalian buat. contoh punya saya disini adalah `ssh alvin@192.168.1.120` lalu masukan password kalian.

   ![dwply1](https://user-images.githubusercontent.com/90166916/138571585-6e5572c5-9779-4925-beac-419e91bc2a94.png)
   
   ![dwply2](https://user-images.githubusercontent.com/90166916/138571587-33fb290d-2450-472d-ab6d-0d26e00ced3d.png)


 * lalu kalian bisa menggunakan perintah `git clone https://github.com/sgnd/dumbplay-frontend.git` untuk mengclone aplikasi yang nanti akan kita kerjakan.
 * jika sudah kalian bisa meng install node js menggunakan perintah `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash` 
 * lalu masukan masukan perintah `exec bash`
 * jika sudah terinstall kalian bisa cek menggunakan perintah `nvm -v` 
 * kemudian kita install node.js `nvm install 14`.
 * untuk cek version kita bisa menggunakan perintah `node -v` lalu untuk mengecek npm bisa menggunakan perintah `npm -v`.

   ![Screenshot from 2021-10-24 04-08-26](https://user-images.githubusercontent.com/90166916/138571654-01b9edde-8d0d-4352-8f89-0c372bf43ece.png)

 * jika sudah kalian bisa masuk ke directory yang tadi kita clone `cd dumbplay-frontend`
 * lalu masukan perintah `npm install`

   ![dwply3](https://user-images.githubusercontent.com/90166916/138571588-b252daaa-4c55-43e6-b040-9f6af30787e8.png)

 * setelahnya `npm start`

   ![dwply4](https://user-images.githubusercontent.com/90166916/138571589-9558164d-9f54-46ba-b7ea-05dd564d5726.png)

   ![dwply5](https://user-images.githubusercontent.com/90166916/138571590-7ed7cb3a-cc1c-4f7d-b246-81ca5c9e5894.png)

 * jika sudah kalian bisa cek di web browser kalian lalu masukan ip kalian setelah itu masukan port si aplikasi `192.168.1.120:3000`
  
   ![dwfrntend](https://user-images.githubusercontent.com/90166916/138571757-c50f1f26-7008-4d91-a4af-ecb51c2f7a98.png)

2. Reverse Proxy 

 *  pertama-tama kalian bisa install terlebih dahulu nginx `sudo apt install nginx`
 *  jika sudah kalian bisa cek menggunakan perintah `sudo systemctl status nginx` 

   ![dwproxy1](https://user-images.githubusercontent.com/90166916/138572660-86f2185d-1268-49e7-a9ec-59583c5376f6.png)

 *  lalu kalian bisa masuk ke directory /etc/nginx `cd /etc/nginx` 
 *  jika sudah kalian bisa buat directory dengan menggunakan perintah `mkdir dwplay`
 *  setelah itu kalian bisa masuk terlebih dahulu ke dalam file nginx.conf `sudo nano nginx.conf`, lalu masukan di bagian blog include lalu masukan lokasi directory yang kalian buat tadi `include /etc/nginx/dwplay/*;(* bintang : digunakan untuk bisa mendeteksi semua file )

   ![dwproxy2](https://user-images.githubusercontent.com/90166916/138572659-19c5bee4-fb48-4747-a757-a300dd1973c2.png)

   ![dwproxy3](https://user-images.githubusercontent.com/90166916/138572657-224b60b1-04a8-4c8f-896f-c67a732649fe.png)

 *  selanjutnya masuk ke directory yang kalian buat tadi `cd dwplay` dan buat sebuah file dengan nama dwplay.xyz `sudo nano dwplay.xyz`
 *  lalu disini kita buat script reverse proxy.
 *  masukan saja seperti script berikut : 

   ![dwproxy6](https://user-images.githubusercontent.com/90166916/138572954-a6411d02-b7fb-433f-9e5c-dbb22644d312.png)

 *  jika sudah bisa keluar dari teks editor menggunakan `ctrl X` lalu tekan `Y` dan `Enter`.
 *  lalu kaliab bisa reload nginx kalian `sudo systemctl reload nginx`

   ![dwproxy7](https://user-images.githubusercontent.com/90166916/138573031-781ff868-54c0-4e6b-83de-1786595f9952.png)

 *  Jika sudah kalian bisa pindah ke local kalian lalu masuk ke  file /etc/hosts `sudo nano /etc/hosts` , setelah itu masukkan ip server kalian dan nama file .xyz yang tadi kalian buat `192.168.1.120  dwplay.xyz`

   ![dwproxy7,1](https://user-images.githubusercontent.com/90166916/138573167-72d58097-a080-4fc2-8efb-6791e45bb845.png)

   ![dwproxy8](https://user-images.githubusercontent.com/90166916/138573129-33627bd0-8e55-4a73-a078-ac01421a1cb5.png)

 *  setelah itu kita coba ping untuk melihat apakah sudah connect atau belum. `ping dwplay.xyz`

   ![dwproxy9](https://user-images.githubusercontent.com/90166916/138573292-587eaea4-f45a-4ab6-ab25-c4050959e936.png)

 *  jika sudah kita bisa kembali server lalu masuk ke directory yang tadi kalian clone `cd dumbplay-frontend`
 *  jika sudah langsung jalankan si aplikasi saja dengan perintah `npm start`

   ![dwproxy10](https://user-images.githubusercontent.com/90166916/138573407-22e6a8ad-9d0e-47b7-a28c-01ff81748977.png)

   ![dwproxy11](https://user-images.githubusercontent.com/90166916/138573408-7afa79ca-d7ba-442f-98d9-204696fd4f08.png)

 *  lalu kalian bisa buka web browser kalian dan search nama domain yang tadi kalian sudah buat `dwplay.xyz`
  
   ![dwplayreverseproxy](https://user-images.githubusercontent.com/90166916/138573405-517917f9-b57b-482e-9f16-34cdf6476863.png)

