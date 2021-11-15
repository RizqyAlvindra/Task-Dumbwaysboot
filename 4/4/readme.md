# SetUp Server With Ansible.

1. Installation Ansible.

  * ikuti langkah-langkah seperti berikut
  * lakukan update terlebih dahulu. 

    `sudo apt update`
    
  * `sudo apt install software-properties-common`
  * `sudo add-apt-repository --yes --update ppa:ansible/ansible`
  * `sudo apt install ansible`
  * jika langkah di atas sudah kalian lakukan makan ansible telah berhasil di install

2. SetUp Server.

  * pertama buat directori baru dengan nama ansible-playbook
  * lalu buat file dengan nama inventory. lalu masukan ip server kalian yang ingin kalian setup.
  * `nano Inventory`
   
    ![ans1](https://user-images.githubusercontent.com/90166916/141717495-ecb32e88-5021-4779-8868-1d2e1bcf07b3.png)
  
  * setelah itu kita coba jalankan ansible untuk ping semua server.
    
    `ansible all -m ping`
    
    ![ans2](https://user-images.githubusercontent.com/90166916/141717766-1ecd62aa-4eca-4306-ad5b-acd50ddc4b64.png)
  
3. SetUp install nginx.
  
  * buat file .yml
  * nano nginx.yml 
  * lalu masukkan perintah seperti gambar dibawah.
    
    ![ans3](https://user-images.githubusercontent.com/90166916/141719068-d7212245-3b2e-49af-a95a-bf74a955db86.png)

  * jika sudah kita jalankan saja config tadi menggunakan ansible.

    `ansible-playbook ngix.yml`
    
    ![ans4](https://user-images.githubusercontent.com/90166916/141719138-28cbac99-0999-4900-ac2e-6425fa80476b.png)

4. Setup Docker Instalation.
  * buat file.yml
   
  * `nano Docker.yml`
  * masukan perintah di bawah.
    ``` 
    - hosts:
        - 3.210.158.196
        - 3.208.255.202
        - 18.233.109.255
        - 35.172.97.51
      become: yes
       tasks:
            - name: install snap docker
              shell: sudo snap install docker
    ```

5. SetUp Docker Container.
   * disini kita lanjutkan saja docker.yml yang tadi
   * tambahkan isi file seperti gambar dibawah.
   * 
    `nano Docker.yml`
  
    ![ans5](https://user-images.githubusercontent.com/90166916/141722896-c581a9f2-c0f3-47dc-b380-7912529b0e4e.png)

   * jika sudah kita jalankan saja config tadi menggunakan ansible.

    `ansible-playbook -K docker.yml`
    
    ![ans6](https://user-images.githubusercontent.com/90166916/141722890-44b692c7-2836-4e12-a2ea-a820f6a1712f.png)

   * jika sudah cek di server kalian apakah container sudah berjalan.

    ![ans7](https://user-images.githubusercontent.com/90166916/141728213-5821c59c-e0cf-454e-a067-9798679bc4cc.png)

    ![ans8](https://user-images.githubusercontent.com/90166916/141728212-ddc3a9a8-6bde-44a9-8685-a68674de223d.png)
    
6. Setup Node_exporter.
   
   * buat file.yml terlebih dahulu
   * sebelumnya pastikan di semua server telah di setting node_exporter.service
   * sudo nano node_exporter
    ```- name: Setup Node exporter
   hosts: 
    - 3.210.158.196
    - 3.208.255.202
    - 18.233.109.255
    - 35.172.97.51
   become: yes
   tasks:
    - name: Update system
      shell: sudo apt update

    - name: Download node exporter
      shell: "wget https://github.com/prometheus/node_exporter/releases/download/v1.2.2/node_exporter-1.2.2.linux-amd64.tar.gz"
      args:
        executable: /bin/bash

    - name: Extract node exporter
      shell: "tar xvfz node_exporter-1.2.2.linux-amd64.tar.gz"
      args:
        executable: /bin/bash

    - name: Move node exporter to /usr/local/bin
      shell: sudo mv node_exporter-1.2.2.linux-amd64/node_exporter /usr/local/bin
      args:
        executable: /bin/bash

    - name: Daemon-reload
      shell: sudo systemctl daemon-reload
      args:
        executable: /bin/bash

    - name: Enable node exporter
      shell: sudo systemctl enable node_exporter
      args:
        executable: /bin/bash

    - name: Start node exporter
      shell: sudo systemctl start node_exporter
      args:
        executable: /bin/bash
    ```
   * jika sudah jalankan perintah ansible.

    `ansible-playbook -K node_exporter.yml`
    
    ![ans9](https://user-images.githubusercontent.com/90166916/141739402-52dcef81-b138-4aca-8633-3b528ceb235f.png)

    ![ans10](https://user-images.githubusercontent.com/90166916/141739395-97974e62-165c-47f7-b22f-bc6891eca55d.png)

   * jika sudah kita coba akses 1 server di web.browser
   
    ![ans11](https://user-images.githubusercontent.com/90166916/141739698-2d526080-9486-4e96-ab69-9aa3f98aaefe.png)

    ![ans12](https://user-images.githubusercontent.com/90166916/141739692-d2347956-f870-435e-b9ee-0ee07a882a22.png)

    * karena disini punya saya ada yang eror di satu server
    * jadi saya ulangi pembuatannya di satu server tersebut.
    * buat config.yml
    
    `sudo nano node_exporter_frontend.yml`
    
    ```- name: Setup Node exporter
    hosts: 
    - 3.208.255.202
    become: yes
    tasks:
    - name: Update system
      shell: sudo apt update

    - name: Download node exporter
      shell: "wget https://github.com/prometheus/node_exporter/releases/download/v1.2.2/node_exporter-1.2.2.linux-amd64.tar.gz"
      args:
        executable: /bin/bash

    - name: Extract node exporter
      shell: "tar xvfz node_exporter-1.2.2.linux-amd64.tar.gz"
      args:
        executable: /bin/bash

    - name: Move node exporter to /usr/local/bin
      shell: sudo mv node_exporter-1.2.2.linux-amd64/node_exporter /usr/local/bin
      args:
        executable: /bin/bash

    - name: Daemon-reload
      shell: sudo systemctl daemon-reload
      args:
        executable: /bin/bash

    - name: Enable node exporter
      shell: sudo systemctl enable node_exporter
      args:
        executable: /bin/bash

    - name: Start node exporter
      shell: sudo systemctl start node_exporter
      args:
        executable: /bin/bash
    ```
    * jika sudah langsung saja jalankan.
    
     `ansible-playbook -K node_exporter_frontend.yml`
     
     ![ans13](https://user-images.githubusercontent.com/90166916/141740674-3407c92b-dec6-4c30-aac3-da0a4dbbae02.png)

     ![ans14](https://user-images.githubusercontent.com/90166916/141740687-d0f99033-6db3-42cd-a149-5568309f8043.png)

7. SetUp mysql Installation.
 
    * buat file .yml 
    * `sudo nano mysql.yml`
    * masukan configurasi seperti gambar dibawah.
    
     ![ans15](https://user-images.githubusercontent.com/90166916/141741192-7e5e6b8b-76a0-4f38-856f-86677bb4c83e.png)

    * jika sudah langsung jalankan saja.
    * `ansible-playbook -K mysql.yml` 

     ![ans16](https://user-images.githubusercontent.com/90166916/141741447-e97739c5-8086-4efc-b7f8-e27c8d805cc3.png)

8. Setup Jenkins.

    * buat file .yml
    * `sudo nano jenkins.yml`
    *  pastikan konfigurasi sama seperti gambar di bawah.
    
     ![ans17](https://user-images.githubusercontent.com/90166916/141742146-f5e19eb5-09c5-47a2-b2da-3a37e0d0984f.png)

    * jika sudah langsung di jalankan saja.
    * `ansible-playbook -K jenkins.yml`

     ![ans18](https://user-images.githubusercontent.com/90166916/141742528-45dff2f5-0c5f-47f5-b2ca-fcd315311df5.png)

    * sebagai pembuktian kita buka server kita dan web.browser jenkins kita.

     ![ans19](https://user-images.githubusercontent.com/90166916/141742526-0ac27032-45d8-429c-a843-0d759f8ec609.png)

     ![ans20](https://user-images.githubusercontent.com/90166916/141742518-c4821675-863f-48ba-8b66-bf15a30b452d.png)
























