# Setup Jenkins Job

1. Configure System in Jenkins
  * install plugin 
  * masuk ke halaman manage jenkins
  * pilih configuration system
  * search publish over ssh

  ![job1](https://user-images.githubusercontent.com/90166916/140806136-13e2591a-7233-4179-b5a2-8c3cd48634c6.png)

  * copy aws key yang digunakan server kalian.
  * lalu beri nama sever.
  * masukan hostname kalian
  * lalu masukan username kalian
  * set time outnya menjadi 0ms

  ![job2](https://user-images.githubusercontent.com/90166916/140806970-646ba82f-710e-4abf-9842-69e637323f4d.png)

  * terakhir test koneksi ssh ker server

2. Create Job

  * masuk ke dashboard lalu tekan create a job
  * lalu masukan nama project kalian.
  * pilih freestyle
  * 
# Set Up Slack

1. masuk ke slack di web browser 
2. lalu buat lah workspace.
3. setelah itu masuk ke api.slack.com
4. cari bagian scopes lalu masukan seperti gambar dibawah.

 ![slack1](https://user-images.githubusercontent.com/90166916/140821505-dd6cbf63-92dc-42c3-a962-49390bf11c81.png)

5. pergi ke atas lalu tekan install to workspace jangan lupa untuk mengcopy Token kalian.

 ![slack3](https://user-images.githubusercontent.com/90166916/140822267-0336c3b2-daaf-4fac-a6ee-39ac6f487769.png)

6. nanti jika ada pilihan langsung tekan saja allow.
7. lalu kembali ke app slack kalian lalu klik kanan di workspace kalian setelah itu tekan open app details.

 ![slack2](https://user-images.githubusercontent.com/90166916/140822273-549d5872-aa44-494c-85e1-65dc2ffba1c7.png)

8. Jika sudah masuk ke jenkins 
9. lalu pergi ke menu manage credentials
10. lalu tekan global
11. lalu add tekan add credential
12. lalu set menjadi set menjadi secret text
13. lalu paste token kalian tadi.

 ![slack4](https://user-images.githubusercontent.com/90166916/140823014-5b1dc655-bc94-4312-ae42-09637676c235.png)

14. jika sudah masuk ke configure system 
15. lalu scroll ke paling bawah.
16. lalu masukan nama workspace kalian.
17. pilih credential yang kalian buat tadi.
18. lalu default chanel #general
19. dan jangan lupa untuk men ceklist 
20. setelah itu tes configure terlebih dahulu.

![slack5](https://user-images.githubusercontent.com/90166916/140823734-54f5eacb-7c4b-4cd9-af40-84c6c013bbdd.png)

21. setelah itu masuk ke app.slack kalian.

![slack5](https://user-images.githubusercontent.com/90166916/140823734-54f5eacb-7c4b-4cd9-af40-84c6c013bbdd.png)

23. 
