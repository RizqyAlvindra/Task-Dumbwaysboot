# Web Server nginx

#Docker Nginx
1. buka web.browser hub.docker.com
2. cari nginx lalu pull image nginx

  ![web1](https://user-images.githubusercontent.com/90166916/142757104-daa55cf8-42b5-43fa-b728-906a8863a793.png)

3. setelah itu jalankan dengan menggunakan perintah

  `sudo docker run --name nginx -p 8888:80 -d nginx`
  
4. jika sudah cek apakah container sudah berjalan.

  ![web2](https://user-images.githubusercontent.com/90166916/142757099-65eebc64-c1f0-428b-9798-dc8b97c70947.png)


 # Reverse Proxy
 
 1. Frontend reverse.proxy and load balancing.

  ![web3](https://user-images.githubusercontent.com/90166916/142757307-c07b69c1-8429-4145-8060-e71004814232.png) 
 
 2. Backend reverse.proxy and load balancing.
 
  ![web4](https://user-images.githubusercontent.com/90166916/142757306-677d07b5-785b-4ef1-9b3a-830f3a2d1a23.png)

 3. CI/CD.
 
  ![web5](https://user-images.githubusercontent.com/90166916/142757305-10bca166-2bb8-4a48-8805-99c24793e13d.png)

 4. Monitoring prometheus,grafana.

  ![web6](https://user-images.githubusercontent.com/90166916/142757304-2b7ae29b-6d41-4636-be53-415e6edfca91.png)

 5. nginx.conf

  ![web7](https://user-images.githubusercontent.com/90166916/142757387-e19b8cfd-7712-4447-b299-8d70ee01ebfa.png)

 # SetUp SSL 
 
 1. masuk dashboard cloudflare kalian.
 2. masuk ke pilihan API TOKENS
 3. tekan Global ip key 
 4. jika sudah view API key kalian.
 
  ![web8](https://user-images.githubusercontent.com/90166916/142757663-7b3b3cb3-bb76-4cc2-bd38-c5825c73db22.png)

 5. masuk ker server nginx buat directory .cloudflare
 6. lalu buat file API.key
 
  ![web9](https://user-images.githubusercontent.com/90166916/142757659-9b6d1970-167e-4f85-b4a5-5d53c2104e33.png)

 7. set permission
 
  `sudo chmod400 API.key`

 8. install certbot.
 
  `sudo snap install --classic certbot`
 
  `sudo ln -s /snap/bin/certbot /usr/bin/certbot`

 9. Jalankan certbot

  ![web10](https://user-images.githubusercontent.com/90166916/142757725-e83bba31-3fe9-4d0b-a1c6-3a8902f3701c.png)

 # Custom Domain
 
  ![web11](https://user-images.githubusercontent.com/90166916/142757784-ede70a23-2c80-4363-99d8-7671960d03ac.png)

    
