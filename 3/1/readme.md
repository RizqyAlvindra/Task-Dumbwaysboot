# Install Docker

1. Pertama-tama kalian bisa buat terlebih dahulu server di aws kalian sama persis seperti minggu kemarin teteapi untuk security grupnya kalian bisa ganti menjadi all trafic 0.0.0.0/0 .
2. Jika sudah kalian bisa masuk ke server kalian lalu lakukan perintah update dan upgrade 

    `sudo apt update`
    
    `sudo apt upgrade`

3. Lalu untuk melakukan Instalasi sebenarnya ada banyak cara , disini saya contohkan 2 cara

    `sudo snap install docker`
    
    atau kalian bisa menggunakan perintah
    
    `# wget -O - https://gist.githubusercontent.com/sgnd/8ac5130ec4439985d14d118c77b7b418/raw/c351376fd4d7afbca587f8ed1f2fd57f87e113ce/docker.sh | bash`

4. Disini saya menggunakan yang simple saja.

    ![installdocker](https://user-images.githubusercontent.com/90166916/140634992-a9c30128-6c43-49fc-a11f-72d4b88df2bc.png)

5. lalu untuk instalasi Docker compose kalian bisa menggunakan perintah.

    `sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
    
    `sudo chmod +x /usr/local/bin/docker-compose`
    
    `sudo docker-compose --version`
    
    ![dockercompose--version](https://user-images.githubusercontent.com/90166916/140635092-dacfb12a-0cb6-4186-b713-c6962c041da6.png)


