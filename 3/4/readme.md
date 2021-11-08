# Jenkins Instalation.

1. Karena Jenkins menggunakan java jadi kita install java terlebih dahulu. 

     `sudo apt install openjdk-8-jdk`

2. Setelah itu masukan perintah ini.

     `wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -`

     `sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`

3. jika sudah lakukan update terlebih dahulu.

     `sudo apt update`
  
4. lalu install jenkins.

     `sudo apt install jenkins`
  
     `sudo systemctl start jenkins`
  
     `sudo systemctl status jenkins`
  
     `sudo ufw allow 8080`
  
     `sudo ufw status`
  
     `sudo ufw allow OpenSSH`
  
     `sudo ufw enable`
  
      ![jenkins4](https://user-images.githubusercontent.com/90166916/140746804-63810f02-398b-499a-924a-30e61823a388.png)

5. Jika semua tahapan sudah selesai kalian bisa buka web.browser kalian lalu masukan ip.pub server kalian setelah itu masukan port si jenkins
6. Akses di terminal kalian perintah seperti dibawah lalu copy sercret keys tersebut lalu masukan ke dalam jenkins.
     `sudo cat /var/lib/jenkins/secrets/initialAdminPassword` 
     
     `44.199.147.36:8080`
  
      ![Jenkins5](https://user-images.githubusercontent.com/90166916/140747620-7bc1f582-df7b-49f4-a650-121f8b55b407.png)

7. Lalu pilih customize jenkins yang `install sugested plugins`

      ![Jenkins6](https://user-images.githubusercontent.com/90166916/140747611-63de2cc3-444f-4867-8377-6ee74267202c.png)

8. Setelah itu tunggu saja sampai proses selesai.

      ![Jenkins7](https://user-images.githubusercontent.com/90166916/140748863-1b8dcb75-7085-492a-a4bc-7c6a175da6f2.png)

9. Jika sudah set user password Jenkins kalian.

      ![Jenkins8](https://user-images.githubusercontent.com/90166916/140748870-d672d2f9-66f6-4756-b058-185eec5fc799.png)

10. Setelah itu bisa tekan next saja 
11. Dan Jenkins sudah berhasil di Install

      ![Jenkins9](https://user-images.githubusercontent.com/90166916/140748875-1ccbaca9-df05-487f-9fc8-5bf839084777.png)

      ![Jenkins10](https://user-images.githubusercontent.com/90166916/140748879-39be96b5-358f-4ef4-9e71-c312c95da2d6.png)

# Reverse Proxy and Setting Domain for Jenkins.

1. Sama seperti minggu" lalu kita buat terlebih dahulu domain kita di cloudfare dns.

      ![jenkinproxy1](https://user-images.githubusercontent.com/90166916/140798453-310a22b8-6c0c-4ede-8e97-07b44699cee4.png)

2. Jika sudah kita masuk ke server nginx kita.
3. Lalu buat directory baru di etc/nginx. 

   `cd /etc/nginx`

   `sudo mkdir jenkins.alvin.onlinecamp.id`
   
4. Lalu kita buat file reverse.proxy Jenkins kita.

   ```
   server {
    listen 80;
    server_name jenkins.alvin.onlinecamp.id;

    location / {
	    proxy_pass http://3.210.158.196:8080;
          }
     } ```


5. Jika sudah kita masuk ke nginx.conf dan masukan lokasi file.reverse proxy kita tadi.

   ![Jenkinproxy2](https://user-images.githubusercontent.com/90166916/140799320-56b24364-8870-4f61-8cb8-7e2783f25dad.png)

6. Jika sudah restart nginx kita setelah itu buka web.browser kalian.

   `sudo systemctl restart nginx`
   
   `jenkins.alvin.onlinecamp.id`
   
   ![Jenkinsproxy3](https://user-images.githubusercontent.com/90166916/140799584-922c9a98-4f44-4bbc-8938-d1f0349be7d6.png)
   
