# Connect multiple sever to prometheus.

1. masuk ke server monitoring kita.
2. masuk ke directory /etc/prometheus/
3. edit file prometheus.yml
4. disini kita tambahkan ip server kita yang ingin kita monitoring.
  
  ![multi1](https://user-images.githubusercontent.com/90166916/141744051-31577d7d-78bf-4a06-be5c-d5041970ca7a.png)

5. jika sudah tekan ctrl+x.
6. lalu reload si prometheus

  `sudo systemctl restart prometheus.service`
  
7. jika sudah kita cek dengan menggunakan status untuk melihat apakah ada eror atau tidak.

  `sudo systemctl status prometheus.service`

8. jika sudah buka web.browser kalian dan masukan ip serverkalian lalu port s aplikasi.  

  http://34.226.252.105:9090
  
  ![multi2](https://user-images.githubusercontent.com/90166916/141746261-4f69bd7e-f71f-4652-a009-1583b5ff4173.png)

# Reverse Proxy Grafana.

1. set security grup server monitoring.
2. arahkan ke server nginx.
3. lalu buat reverse proxy untuk si grafana.
4. `cd /etc/nginx/`
   
   `sudo mkdir grafana`
   
   `sudo nano monitoring.alvin.onlinecamp.id`
   
5.  reverse.proxy
``` server {
    listen 80;
    server_name monitoring.alvin.onlinecamp.id;

    location / {
	    proxy_pass http://34.226.252.105:3000;
    }
}
```

6. lalu masuk ke web browser cloudflare 
7. buat dns baru dengan nama 

  `monitoring.alvin.onlinecamp.id`
  
8. lalu masukan ip server nginx.

  ![multi3](https://user-images.githubusercontent.com/90166916/141749208-883fc2a3-7ce2-4e19-a5d2-d9ae6c9fbe33.png)

9. jika sudah masuk ke server nginx
10. lalu masuk ke file nginx.conf

  `sudo nano cd /etc/nginx/nginx.conf`

11. lalu di bagian include masukkan lokasi reverse.proxy kalian tadi.

   ![multi4](https://user-images.githubusercontent.com/90166916/141749548-8630a162-8ea9-447b-89f6-7c566e8367e6.png)

12. jika semua step telah selesai.
13. jalankan restart nginx.
14. lalu cek dengan menggunakan status untuk melihat ada eror atau tidak.

   `sudo systemctl restart nginx`
   
   `sudo systemctl status nginx`

  ![multi5](https://user-images.githubusercontent.com/90166916/141750030-55958400-1541-4ee3-9758-362331995c29.png)

15. terakhir buka web browser kalian lalu masukan nama domain kalian.

    http://monitoring.alvin.onlinecamp.id
    
   ![multi6](https://user-images.githubusercontent.com/90166916/141750027-7f93833d-160d-4b64-ab5a-244c30b9313d.png)

# Grafana Theme

   * Pergi ke menu Configuration lalu cari Prometheus.
   * lalu masukan ip server prometheus kalian dan masukan port si aplikasi.
   
   ![grafana1](https://user-images.githubusercontent.com/90166916/141752808-4ad978ea-2724-4abf-b066-ceffaeeecf45.png)
   
   * setelah itu tekan save dan test.
   * setelah itu tekan tanda + di menu.
   * lalu tekan create.
   * lalu tekan add an empty panel. 
   * setelah itu buka server prometheus kalian.
   * lalu cari saja apa yang kalian butuhkan untuk melakukan monitoring.
   * contoh saya mencari build info

   ![grafana2](https://user-images.githubusercontent.com/90166916/141757841-978c846c-299f-4629-a517-b5ee183ff368.png)

   * setelah itu masuk ke grafana masuk ke empypanel yang tadi jika sudah masukan ke bagian metrics browser.
   
	```node_exporter_build_info{branch="HEAD", goversion="go1.16.7", instance="18.233.109.255:9100", job="node_exporter_metrics",revision="26645363b486e12be40af7ce4fc91e731a33104e", version="1.2.2"}```

   * setelah itu tekan apply

   ![grafana3](https://user-images.githubusercontent.com/90166916/141758225-67c31e2f-5dc3-42f2-bf14-ef8f5eb0ed0a.png)

   * dan kalian bisa lihat Dashboard kalian.

   ![grafana4](https://user-images.githubusercontent.com/90166916/141758353-17182675-336b-4115-8f03-b4801484ec99.png)

   * lakukan seperti di atas lagi jika kalian ingin menambahkan beberapa panel lagi.
