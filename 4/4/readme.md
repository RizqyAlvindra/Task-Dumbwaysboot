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
   * 
6.    
