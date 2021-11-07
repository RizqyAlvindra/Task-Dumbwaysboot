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
