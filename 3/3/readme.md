# Install Application.

1. Install Nginx.
  
   * Untuk menginstalasi kalian bisa menggunakan perintah seperti ini. untuk membuat image serta menjalankan si aplikasi.

    `sudo docker run --name nginx -p 8888:80 -d nginx`
    
      ![docker1](https://user-images.githubusercontent.com/90166916/140637021-b1151170-dabd-45dd-855b-d932c793d169.png)

   * Jika sudah kalian bisa cek container kalian apakah ada kesalahan atau tidak.
   * Jika ada kesalahan kalian bisa gunakan perintah logs.
    
    `sudo docker container ls`
    
    `sudo docker logs (masukan nama container ataupun container id kalian.`
    
      ![docker2](https://user-images.githubusercontent.com/90166916/140637020-3a015465-3e96-4e3e-be84-ec99efd0c010.png)

  * jika sudah kalian bisa buka web.browser kalian lalu masukan ip.pub kalian lalu port si container

    `35.172.97.51:8888`
    
      ![docker3](https://user-images.githubusercontent.com/90166916/140637019-342f09ef-90e2-4766-a341-5b56a1381adc.png)

2. Instalasi Frontend application.

  * Pertama-tama saya membuat terlebih dahulu file Docker file dengan menggunakan dengan script seperti berikut.

    ``` 
        FROM node:14.18.1
        WORKDIR /DW16WYD0W-APP-DUMPLAY/client
        COPY . .
        RUN npm install
        EXPOSE 3000
        CMD [ "npm", "start" ]
    ```
  * Setelah itu saya membuat image untuk aplikasi frontend 

    ```
    sudo docker build --tag frontend:14 .
    ```
   
  * Jika sudah cek terlebih dahulu apakah images nya sudah ada atau belum.

    `sudo docker images`
    
      ![docker4](https://user-images.githubusercontent.com/90166916/140637608-1dfa9a01-6809-4810-a18b-386075eb0b19.png)

  * Setelah itu saya membuat containernya terlebih dahulu.

    ```
    sudo docker container create --name frontend -p 2000:3000 frontend:14
    ```
    
  * Jika sudah cek container apakah sudah terbuat atau belum.

    `sudo docker container ls -a`
    
      ![docker5](https://user-images.githubusercontent.com/90166916/140637672-31617a87-1812-40fe-8fa8-56ca43adcb5d.png)

  * Jika sudah ada langsung saja kita jalankan si container.

3. Instalasi aplikasi Backend. 
  
  *  Pertama-tama saya membuat terlebih dahulu file Docker file dengan menggunakan dengan script seperti berikut.

    ``` 
        FROM node:14.18.1
        WORKDIR /DW16WYD0W-APP-DUMPLAY/client
        COPY . .
        RUN npm install
        EXPOSE 5000
        CMD [ "npm", "start" ]
    ```
  *  Setelah itu saya membuat image untuk aplikasi backend.

    ` sudo docker build --tag backend:14 .`
  
  *  Jika sudah cek terlebih dahulu apakah images nya sudah ada atau belum.
  
    `sudo docker images`
     
   ![docker4](https://user-images.githubusercontent.com/90166916/140637608-1dfa9a01-6809-4810-a18b-386075eb0b19.png)
  
  *  Setelah itu saya membuat containernya terlebih dahulu.

    `sudo docker container create --name backend -p 4000:5000 backend:14`
    
  * Jika sudah cek container apakah sudah terbuat atau belum.

    `sudo docker container ls -a`
  
      ![docker6](https://user-images.githubusercontent.com/90166916/140640312-f2b37bae-9972-4c56-982b-bbcb2925e66a.png)

  * Jika sudah kita langsung saja jalankan si container.

    `sudo docker container start backend`
  
  * Jika semua tahapan telah selesai kaian bisa masuk ke web.browser kalian lalu masukan ip.pub kalian setelah itu masukan si port container.

    `3.208.255.202:4000`
    ![docker7](https://user-images.githubusercontent.com/90166916/140640305-b53ce8dc-c3b9-41af-8b30-71247aace854.png)
    
# Instalasi Backend-Frontend menggunakan Docker-compose.

  * Buat terlebih dahulu file docker-compose.yaml 
  * 
