# Docker Swarm & Microservices

1. Buat 3 server untuk learder dan worker di aws dengan requirment seperti dibawah:
  
  * ubuntu:20.4
  * T2.small.
  * Storage: 10Gb.  
  * Security group: all-trafic
  
  ![last1](https://user-images.githubusercontent.com/90166916/143732491-e126f742-907f-4bbf-bfd9-54a5ce439d25.png)

2. Install Docker.

  ```
  - hosts:
   - 34.199.73.27
   - 54.80.88.240
   - 35.153.107.121
  become: yes
  tasks:
      - name: update
        shell: sudo apt update

      - name: upgrade
        apt:
          upgrade: dist

      - name: install snap docker
        shell: sudo snap install docker
  ```

  ![last2](https://user-images.githubusercontent.com/90166916/143732542-5409d847-0eb4-44f7-bdb0-8b5d1e14b9aa.png)

3. Docker Swarm. 

  * Masuk ke Worker 
  * Masukan perintah ` sudo docker swarm init --advertise-addr (ip-kalian) `
  
  ![last3](https://user-images.githubusercontent.com/90166916/143732720-bf553d46-d22e-4b11-82da-53c71cd25489.png)

4. Join Docker swarm.

  * Buat file.yml
  * 
    ```
     - hosts:
     - 54.80.88.240
     - 35.153.107.121
     become: yes
     tasks:
       - name: join
         shell: docker swarm join --token SWMTKN-1-5wpcx0uv5exxu1b2g5grafpx3nk3vrme89z6d10tj9uiph2d0k-ac1kkxg6j2i72viejaq8fuw6c 34.199.73.27:2377
    ```
    
    ![last4](https://user-images.githubusercontent.com/90166916/143732851-bd8404ea-38a9-4f04-b629-472e35fa2ed2.png)
  
  * Cek dengan menggunakan perintah `sudo docker node ls`

    ![last5](https://user-images.githubusercontent.com/90166916/143732885-03c254ae-4e9e-4da9-a7e1-850aa8861975.png)

5. Push image ke Docker-Registry.
  
  * Buat repo di hub.docker 
  
  * ![hubdockerswarm](https://user-images.githubusercontent.com/90166916/143732931-548f932a-6e96-41b3-9bb1-798cdee9c522.png)
  
  * Clone repository mentor kita. 
    
    `git clone https://github.com/ogak/dumbways-microservice.git`
   
  * Build docker-compose 

    ![last6](https://user-images.githubusercontent.com/90166916/143733120-ca72360f-b781-480f-8ee0-abf188db28f2.png)
  * Login Docker

    ![last5 6](https://user-images.githubusercontent.com/90166916/143733179-f327617d-7617-4f4c-acb8-f6386bdcc483.png)

  * Tag image ke hub.docker kita.

    ![last7](https://user-images.githubusercontent.com/90166916/143733119-894bdda6-8258-4513-b733-eb2a3d1f52ed.png)
    
  * Push image ke Docker registry.

    ![last8](https://user-images.githubusercontent.com/90166916/143733117-cef2c8ea-8109-4f50-ac52-a4a104e3db50.png)
  
6. Pull Docker image ke worker kita.

  ```
  - hosts:
   - 35.153.107.121
   - 54.80.88.240
  become: yes
  tasks:
      - name: pull todo user
        shell: sudo docker pull alvin/todo-user:2.0

      - name: pull todo todo
        shell: sudo docker pull alvin/todo-todo:2.0

      - name: pull todo skill
        shell: sudo docker pull alvin/todo-skill:2.0

      - name: pull todo services
        shell: sudo docker pull alvin/todo-services:2.0

      - name: pull todo profile
        shell: sudo docker pull alvin/todo-profile:2.0
  ```      
  
  ![last9](https://user-images.githubusercontent.com/90166916/143733275-e4d7a63b-214c-4831-90a0-7eeb8b746ed0.png)

7. Deploy
  
  * Masuk ke server leader
  * Jalankan perintah seperti Gambar di bawah.

  ![last10](https://user-images.githubusercontent.com/90166916/143733391-f0bfb527-9b16-438b-be24-2c554a733f3d.png)

  * Untuk me replica gunakan perintah.
    
   `sudo docker service scale (id-docker-service)=(jumlah yang di inginkan`
    
  ![last11](https://user-images.githubusercontent.com/90166916/143733466-69039130-1c80-4192-ad3b-5ca6d01a5720.png)

  * Buka web.browser kalian lalu masukan ip leader kalian lalu port si apk.

  ![last12](https://user-images.githubusercontent.com/90166916/143733505-86ae940d-8bc6-4e1a-9cd3-9f1e5e3f5529.png)
