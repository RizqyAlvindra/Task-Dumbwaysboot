# Instalasi VMware Ubuntu server and Setup Network

* Installasi VMware.
  * pertama-tama kalian bisa download VMware di link berikut. `https://www.vmware.com/products/workstation-player.html`
  * lalu kalian bisa extract file yang sudah kalian download tadi di folder yang anda inginkan.
  * jika sudah kalian bisa masuk ke terminal. dan masuk ke directory yang ada file vmware yang tadi kalian sudah download.
  * lalu masukan perintah `sudo sh VMware-Player-Full-16.2.0-18760230.x86_64.bundle` untuk melakukan instalasi.
  * jika sudah makan vmware sudah siap digunakan.
* Install ubuntu server di VMware.

  Ikuti Langkah-Langkah seperti Gambar dibawah ini:
  
1. Buka VMware kalian yang sudah kalian install tadi
  
  ![vm1](https://user-images.githubusercontent.com/90166916/138383710-809786f9-e328-4ac0-9099-afb7e6886da9.png)

2. Lalu download Iso ubuntu server di website ubuntu `https://ubuntu.com/download/server` jangan lupa untuk memilih yang manual.
3. jika sudah masuk ke VMware lalu tekan `Create a new virtual machine`
4. jika sudah masuk ke tampilan seperti gambar dibawah silahkan pilih `use ISO image` lalu masukan ISO image yang tadi kalian download.  

  ![vm2](https://user-images.githubusercontent.com/90166916/138385570-b59d67f1-a55f-45f2-919a-3f582cccabe5.png)

5. lalu masukan personalize linux seperti yang kalian inginkan.
  
  ![vm3](https://user-images.githubusercontent.com/90166916/138385577-29a28cc6-2324-46c6-9281-d9d976b788d7.png)

6. jika masukan file vmware server ubuntu ini mau kalian simpan dimana.

  ![vm4,1](https://user-images.githubusercontent.com/90166916/138385585-a413a6c7-a5ce-4985-8bf6-d46eb0e7573b.png)

7. lalu masukan seberapa disksize yang kalian inginkan.  
  
  ![vm4](https://user-images.githubusercontent.com/90166916/138385581-7a5d4930-8bf4-43a5-b335-32098231a273.png)

8. jika sudah selesai tekan customize hardware dan masukan pastikan sama seperti gambar dibawah.  
  
  ![vm5](https://user-images.githubusercontent.com/90166916/138385592-2c4dee87-5cd8-45a8-a46f-460613f0db2b.png)

  ![vm6](https://user-images.githubusercontent.com/90166916/138385595-8dcc22bd-e72c-4286-9c06-f04526322d94.png)
  
  ![vm7](https://user-images.githubusercontent.com/90166916/138385597-692cceea-4691-447a-899a-2441751b9b77.png)

  ![vm8](https://user-images.githubusercontent.com/90166916/138385598-1dc27914-b840-4394-899c-475ea6edeaee.png)

9. Jika semua step diatas telah selesai kalian bisa tekan `close` lalu tekan `finish`
10. jika sudah masuk ke Virtual Machine yang sudah kalian buat lalu tekan `power on`
  
  ![vm9](https://user-images.githubusercontent.com/90166916/138385603-f934bfb6-2f1e-4f86-9275-4ce96ae17441.png)

11. lalu tunggu sebentar hingga muncul pilihan bahasa. 

  ![vm10](https://user-images.githubusercontent.com/90166916/138385607-f48798d3-ade8-415e-aaa3-1e0a8ca12855.png)

12. jika sudah keluar pastikan kalian memilih pilihan yang sama seperti gambar dibawah.

  ![vm11](https://user-images.githubusercontent.com/90166916/138385611-1c5042ed-edb8-428a-904f-034b370bbd54.png)

  ![vm12](https://user-images.githubusercontent.com/90166916/138385613-34f3d0f2-4bf6-441f-bb0a-7907025d87b5.png)
  
13. jika sudah masuk tahapan Network Conections , pilih `IPv4 Method manual (DHCP)`
  
  ![vmip](https://user-images.githubusercontent.com/90166916/138385638-9582607a-d998-4fb9-94db-d8611e31bd8e.png)

   Jika sudah Tekan Save lalu pergi ke tahapan selanjutnya.
   
  ![vm14](https://user-images.githubusercontent.com/90166916/138385621-a0fae18d-541b-4547-a107-5d86bf2730d0.png)

  ![vm15](https://user-images.githubusercontent.com/90166916/138385622-644d999e-c56a-496f-8f8f-7e3173bca61b.png)
  
  ![vm16](https://user-images.githubusercontent.com/90166916/138385625-25752c15-fff6-461a-a1e8-7b473da7a78c.png)
   
  ![vm17](https://user-images.githubusercontent.com/90166916/138385627-e3fa24e7-385b-473b-9b68-7cef45c45813.png)
  
  ![vm18](https://user-images.githubusercontent.com/90166916/138385628-158ade92-35c0-4df3-98fe-f551cd89bde8.png)
  
  ![vm19](https://user-images.githubusercontent.com/90166916/138385631-dc51f98b-dd65-4c88-8f03-9bf39b979ee8.png)
  
 14. jangan lupa untuk memilih `install OpenSSh server` dengan menggunakan `Space`
  ![vm20](https://user-images.githubusercontent.com/90166916/138385632-bd5f03d4-758d-427a-8508-5306677600dd.png)
  
 15. Jika sudah kalian bisa tunggu sampai instalasi selesai.
 16. jika sudah selesai kalian bisa langsung tekan `Reboot now` lalu tunggu sampai instalasi server selesai.
 17. Jika sudah selesai masukan saja langsung server name kalian dan pass yang tadi kalian sudah buat.

  ![vmserver1](https://user-images.githubusercontent.com/90166916/138387882-8a16244a-bbb1-4d47-8ea8-c5d71563ebd8.png)

 18. lalu lakukan perintah `ping google.com` untuk mencoba apakah terhubung dengan internet atau tidak.
 19. Jika ada tulisan `ping google.com: temporary failure in name resolution` berati gagal kalian tidak bisa terhubung.
 20. Disini kita harus mengganti ip address yang tadi sudah kita buat.
 21. Gunakan perintah `cd /etc` `cd /netplan` lalu masuk ke file `sudo nano 00-installer-config.yaml`
 22. jika sudah masukkan ip kalian masing-masing , lalu bagaimana cara untuk melihat ip kalian?
 23. Cara melihatnya adalah dengan menggunakan perintah `ifconfig` di terminal kalian.
  
  ![vmconf](https://user-images.githubusercontent.com/90166916/138400427-ff2d09a6-c6e4-4775-8fee-351a9ed69e11.png)
 
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
