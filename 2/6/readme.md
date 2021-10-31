# SSL Configuration

* Langsung saja kita bisa pakai api seperti minggu lalu.
* kalian bisa cek di server nginx kalian lalu masuk `cd .cloudflare`
* cat `API.key`

![sslbackend1](https://user-images.githubusercontent.com/90166916/139567447-0b133fae-8f0d-4473-916d-ad1fe6051b55.png)

* karena minggu lalu kita sudah instalasi certbot jadi kita langsung saja jalankan perintah cerbot sendiri

  `sudo certbot`
  
  pilih alvin2.onlinecamp.id `2`
  
  ![sslbackend2](https://user-images.githubusercontent.com/90166916/139568087-60ed2878-bd93-4771-84f6-eefa818b1432.png)

* jika sudah kalian bisa masuk ke directory /etc/nginx/dumbsound-backend lalu cek file alvin2.onlinecamp.id.

  `cat alvin2.onlinecamp.id`
  
  ![sslbackend3](https://user-images.githubusercontent.com/90166916/139568112-cfa8baa1-f6ae-4ba4-8472-63cc2e51b73b.png)

* masukan perintah `sudo nginx -t` untuk melihat apakah ada syntax yang eror atau tidak.

  ![sslbackend4](https://user-images.githubusercontent.com/90166916/139568331-b0aa239d-ca3d-41c0-a102-6bbc084cee02.png)

* terakhir buka web browser kalian lalu search nama domain kalian https://alvin2.onlinecamp.id/

  ![sslbackend5](https://user-images.githubusercontent.com/90166916/139568314-bf301659-2b27-47f4-a618-d2fb788ab014.png)
