# Reverse Proxy For Backend Application

* login ke server nginx kalian .

  ![backendprxy1](https://user-images.githubusercontent.com/90166916/139566973-bb9f9a2d-feda-40fe-a9de-88e0b18fcd46.png)

* lalu masuk ke folder nginx `cd /etc/nginx`
* lalu buat folder baru `sudo mkdir dumbsound-backend`
* lalu buat file reverse proxy `sudo nano alvin2.onlinecamp.id` 
* masukan ip pub backend kalian lalu masukan si port aplikasi backend yaitu 5000

  ```
  server {
            listen 80;
            server_name alvin2.onlinecamp.id;

            location / {
  	        proxy_pass http://44.199.147.36:5000;
          }
     }
     ```
     
* jika sudah simpan lalu keluar.
* keluar dari directory `cd ..`
* setelah itu masuk ke file nginx.conf `sudo nano nginx.conf`
* setelah itu masukan alamat file yang kalian buat tadi di bagian include.

  ![backendprxy2](https://user-images.githubusercontent.com/90166916/139567012-9ce62ca2-5c9c-4042-bbda-b1812d7ecaeb.png)

* jika reload nginx kalian `sudo systemctl reload nginx`
* lalu arahkan domain ke ip publik reverse-proxy server,untuk dapat berjalan di port 80 jangan lupa uncheck proxy status.

  ![backendprxy3](https://user-images.githubusercontent.com/90166916/139567046-336b5bd5-4e73-4ef2-8280-ed806185b28d.png)

* jika sudah buka web browser kalian lalu serarch nama domain kalian http://alvin2.onlinecamp.id/

  ![backendprxy4](https://user-images.githubusercontent.com/90166916/139567051-359a6371-d102-4b48-8946-21a75b989a8d.png)
