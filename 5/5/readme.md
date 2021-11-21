# Database

1. Buka web.browser hub.docker.com
2. ansible-playbook docker install.
  
  ![ansible-docker install](https://user-images.githubusercontent.com/90166916/142753273-3c29dc5b-584e-4f96-a2d7-543b8022b97d.png)
  
4. cari postgresql dan mysql dan lakukan perintah pull.
 
  ![db1](https://user-images.githubusercontent.com/90166916/142752169-4a5222a2-9d19-44d0-98ad-7b688c0c99bf.png)

  ![db2](https://user-images.githubusercontent.com/90166916/142752167-8d658c48-d9aa-499d-89e5-5c930489a22d.png)

3. jalankan mysql dan postgresql menjadi container

  `sudo docker run --name alvin -e MYSQL_ROOT_PASSWORD=alsangar123 -d -p 3306:3306 mysql:latest`

  `sudo docker run --name postgres -e POSTGRES_PASSWORD=alsangar123 -d -p 5432:5432 postgres:latest`

4. cek si container.

  ![db3](https://user-images.githubusercontent.com/90166916/142752253-3f498e90-e604-4fd3-a372-0bf7082f457c.png)

5. masuk ke dalam container dan buat Database.

  * mysql
  
  ![db4](https://user-images.githubusercontent.com/90166916/142752308-611df468-d14f-4118-ac04-d9d26623863f.png)

  * postgres

  ![db5](https://user-images.githubusercontent.com/90166916/142753059-5546c8c5-92e9-483b-aade-25a1e505634d.png)

  ![db6](https://user-images.githubusercontent.com/90166916/142753057-266596e2-7947-4297-a6a6-ee9181ab3cd9.png)
  
