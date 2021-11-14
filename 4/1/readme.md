# SetUp Monitoring Server

# 1. Installation Node_exporter
  
  * masuk ke server monitoring kalian.
  * seperti biasa lakukan update dan upgrade terlebih dahulu
  
    `sudo apt update; sudo apt upgrade`
  
  * install node exporter.
  
    ```
    wget https://github.com/prometheus/node_exporter/releases/download/v1.2.2/node_exporter-1.2.2.linux-amd64.tar.gz 
    ```

  * lalu extract file kalian.
  
    `tar xvfz node_exporter-1.2.2.linux-amd64.tar.gz`
  
  * pindahkan file yang sudah kalian extract ke /usr/local/bin.
  
    ```sudo mv node_exporter-1.2.2.linux-amd64/node_exporter /usr/local/bin```
    
  * tambah user node_exporter
  
    `sudo useradd -rs /bin/false node_exporter`
    
  * buat config service di /etc/systemd/system.
  
    `cd /etc/systemd/system`
    
    `sudo nano node_exporter.service`
    
  * setlah itu masukan config berikut.
  
  ``` [Unit]
      Description=Node Exporter
      After=network.target

      [Service]
      User=node_exporter
      Group=node_exporter
      Type=simple
      ExecStart=/usr/local/bin/node_exporter

      [Install]
      WantedBy=multi-user.target
  ```
  * setelah itu lakukan reload.

   `sudo systemctl daemon-reload`
   
  * lalu nyalakan service node_exporter.
  
   `sudo systemctl enable node_exporter`
   
  * lalu jalankan node_exporter.  
  
   `sudo systemctl start node_exporter`
   
  * setelah itu cek status node_exporter.
  
   `sudo systemctl status node_exporter`
   
   ![Screenshot from 2021-11-14 13-52-00](https://user-images.githubusercontent.com/90166916/141670745-a671c0e1-b339-47ab-8504-c2e8f0d0b010.png)

  * jika sudah kalian bisa cek web browser kalian dengan memasukan ip kalian setelah itu masukan port si aplikasi.
    
   http://34.226.252.105:9100/
    
   ![Screenshot from 2021-11-14 14-06-21](https://user-images.githubusercontent.com/90166916/141674662-23ea05a3-b6b7-4833-88f6-7b358435994d.png)

# 2.Instalation Promotheus On Server Monitoring.

  * install prometheus
  
    ```wget https://github.com/prometheus/prometheus/releases/download/v2.31.1/prometheus-2.31.1.linux-amd64.tar.gz```
    
  * extract file kaian.
  
    `tar xvf prometheus-2.31.1.linux-amd64.tar.gz`
    
  * pindah file yang sudah kalian extract tadi ke /usr/local/bin.(prometheus dan promtool)
  
    `sudo mv prometheus-2.31.1.linux-amd64/prometheus /usr/local/bin`
    
    `sudo mv prometheus-2.31.1.linux-amd64/promtool /usr/local/bin`
    
  * tambah user prometheus.
    
    `sudo useradd -rs /bin/false prometheus`
  
  * lalu buat masuk ke directory /etc lalu buat directory prometheus.
  
    `cd /etc`
    
    `sudo mkdir prometheus`
    
  * setelah itu kembali ke local kalian.
  * lalu masuk ke folder prometheus yang sudah kalian download. 
  * lau pindahkan file consoles dan console_libraries ke folder yang barusan kalian buat di /etc.
  
    `sudo mv consoles console_libraries /etc/prometheus/`

  * Jika sudah masuk ke /etc/prometheus lalu buat file prometheus.yml .
  * lalu masukan config seperti dibawah.

    ```
    global:
    scrape_interval: 10s

    scrape_configs:
     - job_name: 'prometheus-metrics'
       scrape_interval: 10s
       static_configs:
     - targets: ['localhost:9100']
     - job_name: 'node_exporter_metrics'
    scrape_interval: 5s
    static_configs:
     - targets: ['34.226.252.105:9100'] #server target
    ```
  * set permission 
  
    ` sudo chown -R prometheus: /etc/prometheus /var/lib/prometheus`
    
  * masuk ke directory /etc/systemd/system lalu buat file prometheus service.
  
    ``` 
      [Unit]
      Description=Prometheus 
      After=network.target

      [Service]
      User=prometheus   
      Group=prometheus   
      Type=simple
      ExecStart=/usr/local/bin/prometheus \
          --config.file /etc/prometheus/prometheus.yml \
          --storage.tsdb.path /var/lib/prometheus/ \
          --web.console.templates=/etc/prometheus/consoles \
          --web.console.libraries=/etc/prometheus/console_libraries

      [Install]
      WantedBy=multi-user.target
      ```
  * jika sudah reload daemon
  
    `sudo systemctl daemon-reload`
    
  * setelah itu nyalakan prometheus dan jalankan.
    
    `sudo systemctl enable prometheus`
    
    `sudo systemctl start prometheus`
  
  * untuk mengecek apakah ada eror atau tidak kalian bisa menggunakan perintah 
    
    `sudo systemctl status prometheus`  
    
    ![Screenshot from 2021-11-14 16-04-18](https://user-images.githubusercontent.com/90166916/141674631-6b499115-00ce-43c8-8f25-2e416d8e8bdf.png)

  * setelah itu buka web browser kalian lalu akses menggunakan ip kalians setelah itu masukan port si aplikasi
    
    http://34.226.252.105:9090/  
    
    ![Screenshot from 2021-11-14 15-37-08](https://user-images.githubusercontent.com/90166916/141674644-ed579b9e-94ad-4e86-8b16-17103057b3ad.png)

    ![Screenshot from 2021-11-14 16-19-22](https://user-images.githubusercontent.com/90166916/141675034-4721c160-7c98-43ad-b732-18aa0c85ed02.png)

# 3. Installation Grafana.

  * masuk ke root.
  
    `sudo su`
    
  * masukan perintah  seperti dibawah untuk mendapatkan package grafana.
  
    `sudo wget -q -O - https://packages.grafana.com/gpg.key | apt-key add -`
    
    ![Screenshot from 2021-11-14 16-44-52](https://user-images.githubusercontent.com/90166916/141675834-5f700bfe-d148-48fe-a84f-8d440b3b3737.png)

  * jika sudah keluar dari root `ctrl+D`
  * setelah itu masukan perintah.
    
    `sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"` 
  
  * jika sudah lakukan instalasi grafana.
  
    `sudo apt install grafana -y`
    
  * setelah itu masuk file /etc/grafana/grafana.ini disini kita edit confignya di bagian user dan anonymous.
  * pastikan sama seperti gambar dibawah.
  
    `sudo nano /etc/grafana/grafana.ini`
    
    ![Screenshot from 2021-11-14 16-34-04](https://user-images.githubusercontent.com/90166916/141676137-a2b970e5-0b8a-41f6-bb88-3958b8a0d019.png)

    ![Screenshot from 2021-11-14 16-34-40](https://user-images.githubusercontent.com/90166916/141676135-0441e492-eeaa-41e2-afa6-934414d1f3ac.png)

  
  * jika sudah hidupkan system grafana.
  * lalu reload grafana.
  * setelah itu jalankan system grafana.
  * lalu cek status grafana.
    
    `sudo systemctl enable grafana-server`
    
    `sudo systemctl reload grafana-server`
    
    `sudo systemctl start grafana-server`

    `sudo systemctl status grafana-server`
    
    ![Screenshot from 2021-11-14 16-54-13](https://user-images.githubusercontent.com/90166916/141676198-74ddd541-94eb-476f-a7ad-efaccf159847.png)
    
    ![Screenshot from 2021-11-14 16-49-06](https://user-images.githubusercontent.com/90166916/141676127-a90d35ed-fbb6-4f9a-9a3b-efba86de32e9.png)

  * Jika sudah kalian bisa buka webbrowser kalian lalu masukan ip kalian setelah itu masukan port si aplikasi.

    http://34.226.252.105:3000/
    
    ![Screenshot from 2021-11-14 16-36-25](https://user-images.githubusercontent.com/90166916/141676132-0a19784d-b2b5-435d-8dcb-73c7bfc0ed14.png)

    
