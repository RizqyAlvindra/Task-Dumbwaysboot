# Reverse Proxy

* pertama tama masuk ke server terlebih dahulu `ssh alvin@35.172.97.51`

  ![serverproxy1](https://user-images.githubusercontent.com/90166916/138682591-6f3b6430-52b0-4137-9949-1a43c51975de.png)

* lakukan update dan upgrade terlebih dahulu. `sudo apt update` `sudo apt upgrade`
* jika sudah install nginx `sudo apt install nginx`

  ![serverproxy2](https://user-images.githubusercontent.com/90166916/138682594-9dac9849-b2ac-4dc9-845c-d7a85392e896.png)

* lalu masuk ke folder nginx `cd /etc/nginx/`
* jika sudah buat directory baru `sudo mkdir dumbsound`
* lalu masuk ke dalam folder dumbsound `cd dumbsound`
* setelah itu buar file configurasi `sudo nano alvin.onlinecamp.id`
* jika sudah masukan script seperti berikut. noted! ip proxypass adalah ip frontend kalian lalu di ikuti oleh port si aplikasi.
  ```
  server {
	          listen 80;
	          server_name alvin.onlinecamp.id;

	          location / {
		        proxy_pass http://18.233.208.203:3000;
	        }
       }
 
 
 
 * setelah itu save.
 * lalu kembali ke folder nginx setelah itu masuk ke file nginx.conf `sudo nano nginx.conf`
 * di bagian include kalian tambahkan lokasi file reverse proxy kalian. `include /etc/nginx/dumbsound/*;`

  ![serverproxy3](https://user-images.githubusercontent.com/90166916/138682596-b24020f9-f0f1-40f8-b269-e0928eaf9fe6.png)


 * jika sudah langsung saja keluar.
 * setelah itu kalian bisa reload nginx kalian. `sudo systemctl reload nginx`
 * lalu arahkan domain ke ip publik reverse-proxy server,untuk dapat berjalan di port 80 jangan lupa uncheck proxy status.

  ![serverproxy4](https://user-images.githubusercontent.com/90166916/138682605-65241441-4750-4f30-aa81-0e9576d68fd9.png)

 * jika sudah buka web browser lalu search http://alvin.onlinecamp.id/

  ![serverproxyend](https://user-images.githubusercontent.com/90166916/138682607-8cb546c6-e29c-4c1a-899f-041d6983375a.png)

 

