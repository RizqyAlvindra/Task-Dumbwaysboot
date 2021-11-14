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
