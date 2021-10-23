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
 
 24. lalu masukan ip kalian masing masing dan angka gateway terakhir 255 di ganti dengan 1.


  ![vmwarenewip](https://user-images.githubusercontent.com/90166916/138385640-fb9cc6cc-decb-4ce8-9ffb-2fb0d6fe633f.png)

 25. jika sudah kalian ganti kalian bisa gunakan perintah `netplan apply` untuk mengkonfirmasi ip yang sudah kalian ubah tadi.
 26. lalu tes dengan menggunakan perintah `ping google.com` , jika bisa maka akan keluar perintah seperti dibawah.
 
  ![vmdone](https://user-images.githubusercontent.com/90166916/138401755-051248e0-b2b6-4a6d-a146-cb7804cea6d0.png)

 27. sekarang kita coba masuk menggunakan ssh lewat terminal `ssh alvin@192.168.1.120` (untuk keluar dari server kalian bisa menggunakan perintah `logout`.

  ![vmdone2](https://user-images.githubusercontent.com/90166916/138401733-c8afb8fb-8918-43c6-973d-8a138d4c405c.png)

 28. jika kalian belum bisa connect maka anda harus kembali ke `cd /etc/netplan` `sudo nano 00-installer-config.yaml` untuk mengganti ip kalian karena mungkin ip kalian sudah ada yang menggunakan jadi tidak bakalan bisa menggunakan ip tersebut jadi kalian bisa setting terserah kalian dan jika saat di ping masih tidak bisa connect maka ulangi lagi tahapan ini`.  
  
  
# Frontend and Reverse Proxy server aplikasi dumbsound

  Sebelumnya apa sih reverse proxy itu ?
  
  Jadi Reverse Proxy merupakan sebuah fitur/modul di dalam sebuah webserver, yang berfungsi untuk melakukan port forwarding suatu request, dari public request menuju ke dalam sistem.
  
  Ditugas mingguan kali ini kita mendapatkan tugas untuk mendeploy aplikasi dumbsound di server yang telah kita buat tadi.
  
1. Frontend dumbsound  
  
 * pertama tama kalian bisa buka terminal kalian lalu kalian bisa masuk ke server yang tadi sudah kalian buat. contoh punya saya disini adalah `ssh alvin@192.168.1.120` lalu masukan password kalian.

   ![dwply1](https://user-images.githubusercontent.com/90166916/138571585-6e5572c5-9779-4925-beac-419e91bc2a94.png)
   
   ![dwply2](https://user-images.githubusercontent.com/90166916/138571587-33fb290d-2450-472d-ab6d-0d26e00ced3d.png)


 * lalu kalian bisa menggunakan perintah `git clone https://github.com/sgnd/dumbplay-frontend.git` untuk mengclone aplikasi yang nanti akan kita kerjakan.
 * jika sudah kalian bisa meng install node js menggunakan perintah `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash` 
 * lalu masukan masukan perintah `exec bash`
 * jika sudah terinstall kalian bisa cek menggunakan perintah `nvm -v` 
 * kemudian kita install node.js `nvm install 14`.
 * untuk cek version kita bisa menggunakan perintah `node -v` lalu untuk mengecek npm bisa menggunakan perintah `npm -v`.

   ![Screenshot from 2021-10-24 04-08-26](https://user-images.githubusercontent.com/90166916/138571654-01b9edde-8d0d-4352-8f89-0c372bf43ece.png)

 * jika sudah kalian bisa masuk ke directory yang tadi kita clone `cd dumbplay-frontend`
 * lalu masukan perintah `npm install`

   ![dwply3](https://user-images.githubusercontent.com/90166916/138571588-b252daaa-4c55-43e6-b040-9f6af30787e8.png)

 * setelahnya `npm start`

   ![dwply4](https://user-images.githubusercontent.com/90166916/138571589-9558164d-9f54-46ba-b7ea-05dd564d5726.png)

   ![dwply5](https://user-images.githubusercontent.com/90166916/138571590-7ed7cb3a-cc1c-4f7d-b246-81ca5c9e5894.png)

 * jika sudah kalian bisa cek di web browser kalian lalu masukan ip kalian setelah itu masukan port si aplikasi `192.168.1.120:3000`
  
   ![dwfrntend](https://user-images.githubusercontent.com/90166916/138571757-c50f1f26-7008-4d91-a4af-ecb51c2f7a98.png)

2. Reverse Proxy 

 *  pertama-tama kalian bisa install terlebih dahulu nginx `sudo apt install nginx`
 *  jika sudah kalian bisa cek menggunakan perintah `sudo systemctl status nginx` 

   ![dwproxy1](https://user-images.githubusercontent.com/90166916/138572660-86f2185d-1268-49e7-a9ec-59583c5376f6.png)

 *  lalu kalian bisa masuk ke directory /etc/nginx `cd /etc/nginx` 
 *  jika sudah kalian bisa buat directory dengan menggunakan perintah `mkdir dwplay`
 *  setelah itu kalian bisa masuk terlebih dahulu ke dalam file nginx.conf `sudo nano nginx.conf`, lalu masukan di bagian blog include lalu masukan lokasi directory yang kalian buat tadi `include /etc/nginx/dwplay/*;(* bintang : digunakan untuk bisa mendeteksi semua file )

   ![dwproxy2](https://user-images.githubusercontent.com/90166916/138572659-19c5bee4-fb48-4747-a757-a300dd1973c2.png)

   ![dwproxy3](https://user-images.githubusercontent.com/90166916/138572657-224b60b1-04a8-4c8f-896f-c67a732649fe.png)

 *  selanjutnya masuk ke directory yang kalian buat tadi `cd dwplay` dan buat sebuah file dengan nama dwplay.xyz `sudo nano dwplay.xyz`
 *  lalu disini kita buat script reverse proxy.
 *  masukan saja seperti script berikut : 

   ![dwproxy6](https://user-images.githubusercontent.com/90166916/138572954-a6411d02-b7fb-433f-9e5c-dbb22644d312.png)

 *  jika sudah bisa keluar dari teks editor menggunakan `ctrl X` lalu tekan `Y` dan `Enter`.
 *  lalu kaliab bisa reload nginx kalian `sudo systemctl reload nginx`

   ![dwproxy7](https://user-images.githubusercontent.com/90166916/138573031-781ff868-54c0-4e6b-83de-1786595f9952.png)

 *  Jika sudah kalian bisa pindah ke local kalian lalu masuk ke  file /etc/hosts `sudo nano /etc/hosts` , setelah itu masukkan ip server kalian dan nama file .xyz yang tadi kalian buat `192.168.1.120  dwplay.xyz`

   ![dwproxy7,1](https://user-images.githubusercontent.com/90166916/138573167-72d58097-a080-4fc2-8efb-6791e45bb845.png)

   ![dwproxy8](https://user-images.githubusercontent.com/90166916/138573129-33627bd0-8e55-4a73-a078-ac01421a1cb5.png)

 *  setelah itu kita coba ping untuk melihat apakah sudah connect atau belum. `ping dwplay.xyz`

   ![dwproxy9](https://user-images.githubusercontent.com/90166916/138573292-587eaea4-f45a-4ab6-ab25-c4050959e936.png)

 *  jika sudah kita bisa kembali server lalu masuk ke directory yang tadi kalian clone `cd dumbplay-frontend`
 *  jika sudah langsung jalankan si aplikasi saja dengan perintah `npm start`

   ![dwproxy10](https://user-images.githubusercontent.com/90166916/138573407-22e6a8ad-9d0e-47b7-a28c-01ff81748977.png)

   ![dwproxy11](https://user-images.githubusercontent.com/90166916/138573408-7afa79ca-d7ba-442f-98d9-204696fd4f08.png)

 *  lalu kalian bisa buka web browser kalian dan search nama domain yang tadi kalian sudah buat `dwplay.xyz`
  
   ![dwplayreverseproxy](https://user-images.githubusercontent.com/90166916/138573405-517917f9-b57b-482e-9f16-34cdf6476863.png)

  
# AWS 
 1. Create server and set up server
 2. Server for application
 3. Reverse proxy
 4. Custom domain
 5. Ssl configuration


1. Create server and set up server
 
 * pertama kalian bisa buka aws educate kalian.
 * lalu tekan saja `go to classroom`
 * lalu tekan `continue`
 * jika sudah kalian akan di arahkan ke `https://labs.vocareum.com/main/main.php?m=editor&nav=1&asnid=505547&stepid=505548`
 * jika sudah langsung saja tekan `aws console` untuk masuk ke AWS.
 * lalu tekan saja pilihan luncurkan virtual machine.

   ![aws1](https://user-images.githubusercontent.com/90166916/138573828-67ad6911-9b68-48ba-a4ea-f49cb74c2a5e.png)
 
 * setelah itu cari ubuntu.

   ![aws2](https://user-images.githubusercontent.com/90166916/138573865-3690a812-ddec-41cb-8e96-23e7bf424068.png)
 
 * jika sudah kalian bisa pilih `ubuntu server 20.4LTS` lalu tekan saja select.
 * lalu kalian bisa memilih yang `t2.micro` jika sudah tekan `next: configure instance details`
 
   ![aws3](https://user-images.githubusercontent.com/90166916/138573923-9448a1d7-35b1-4e6a-9e4f-e1abf7aa8c9a.png)

 * selanjutnya pastikan pilihan `number of instance` dan `auto-assign Public ip` sudah sama seperti gambar di bawah.

  ![aws4](https://user-images.githubusercontent.com/90166916/138574015-01237b1b-1e52-4049-99a2-67fae098b085.png)

 * jika sudah tekan saja `next:add storage:`
 * dibagian add storage ini kalian bisa mengatur storage yang kalian butuhkan sendiri tetapi secara default kalian akan diberi storage sebanyak 8gb. disini kita akan menggunakan defaultnya saja, jadi tekan saja next.

  ![aws5](https://user-images.githubusercontent.com/90166916/138574131-81ac2904-c726-4381-a347-75ac5adb3575.png)

 * selanjutnya ada bagian tags disini kalian bisa skip saja `next`
 * sedikit penjelasan disini  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
