
# AWS Create And SetUp Server

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
 * kemudian masuk kebagian security grup disini security grup adalah firewall disini ada 2 cara yaitu membuat baru dan existing.
 * disini security groupname nya ku setting dengan nama`DumbWaysBootWeek1`
 * lalu karena kita nantinya akan membuat reverse proxy untuk si aplikasi kita nanti kita memerlukan.ssh untuk login ke server(port:20) http(nginx port:80) ,https(port:443) jadi kalian tambahkan saja rule seperti berikut.

  ![aws6](https://user-images.githubusercontent.com/90166916/138587130-db45f988-aaa8-486c-ac26-ff090fe616fe.png)

 * lalu disini ada pilihan source. source disini jika kalian setting `0.0.0.0/0` seperti gambar diatas, ini menandakan bisa diakses dari manapun.
 * jika sudah kalian bisa langsung saja tekan `review and lunch`.
 * selanjutnya disini kalian bisa melihat detail dari yang kalian set up tadi. 

  ![aws7](https://user-images.githubusercontent.com/90166916/138587196-3c580fc6-e4e6-461f-aaed-4bfb09dab677.png)

 * jika sudah langsung tekan saja`launch`
 * setelah disini kalian diminta untuk memilih keypair , langsung saja disini pilih `create a new keypair` lalu pilih yang `RSA` setelahnya masukan nama keypair anda dengan nama `dumbways`. lalu tekan `download keypair` jika sudah kalian bisa simpan baik baik keypair anda karena ini untuk login kedalam server.

  ![aws8](https://user-images.githubusercontent.com/90166916/138587683-e7a013c8-f854-41fd-a19f-b806c52c7a86.png)

  ![aws9](https://user-images.githubusercontent.com/90166916/138587664-0ba2656d-d626-4fab-b98a-dbcd601da94f.png)
  
 * jika sudah tekan `launch instance`.
 * tunggu hingga proses build selesai.
 * jika proses telah selesai maka akan seperti tampilan gambar di bawah.

  ![aws10](https://user-images.githubusercontent.com/90166916/138588328-be38e11a-8fff-42a7-9f00-db20612d2ce9.png)
 
 *  jangan lupa untuk diberi nama dengan `gateway`.
 *  sekarang kita harus set ip static menggunakan elastic ip.
 *  kalian pergi ke pilihan `elastic IPs` lalu kalian tekan `alokasi alamat ip elastis` lalu langsung saja tekan `alokasikan`.

   ![aws11](https://user-images.githubusercontent.com/90166916/138589084-8d97f223-f8f0-4201-9a9d-8367befcbf4e.png)

   ![aws12](https://user-images.githubusercontent.com/90166916/138589085-5cbf97a1-25d4-45cc-be4c-802b4ebdcfe6.png)

 *  jika sudah terbuat kalian bisa pergi ke pilihan `Tindakan` lalu kalian bisa pilih kaitkan alamat ip elastis`.

   ![aws13](https://user-images.githubusercontent.com/90166916/138589086-9cac25a0-122d-406f-9b97-e327a9e4bb0f.png)

 *  lalu di bagian instans kalian bisa pilih server yang kalian buat tadi. jika sudah tekan `kaitkan`

   ![aws14](https://user-images.githubusercontent.com/90166916/138589088-ad0eedd8-3c8a-4ca3-8af2-76d2f3399f8b.png)

 *  lalu kalian bisa kembali ke instances dan kalian bisa lihat elastic ip sudah kelihatan di server kalian tadi.
 
   ![aws15](https://user-images.githubusercontent.com/90166916/138589090-d4be758f-3721-4840-afd1-c0378693501c.png)
   
 * Jika sudah selesai kalan bisa buka terminal kalian lalu masuk ke server yang kalian buat tadi.
 * pertama tama masuk ke directory kalian yang ada keypair yang kalan download tadi .
 * lalu langsung saja masuk ke server kalian dengan cara `ssh -i dumbways.pem ubuntu@35.172.97.51` (masukan perintah ssh -i lalu ubuntu@ipserverkalian).

   ![aws16](https://user-images.githubusercontent.com/90166916/138590149-f89687d7-ec72-4bf7-9fc8-42a2b0e97388.png)

 * jika sudah lakukan perintah `sudo apt update` dan `sudo apt upgrade`
 
 # Server app
 
 * pertama tama kalian masuk aws lalu pilih luncurkan virtual machine
 * lalu kalian bisa cari ubuntu
 * selanjutnya kalian pilih yang `t2.micro` 

   ![serverapp2](https://user-images.githubusercontent.com/90166916/138643229-8e000d7c-af4b-443b-b574-ff2869d2751f.png)

 * selanjutnya Configure instance pilih auto-assign public ip ubah menjadi disable.

   ![serverapp3](https://user-images.githubusercontent.com/90166916/138643228-fb602d24-09a6-417f-bb18-62fb0edb0887.png)

 * lalu add storage kalian bisa skip saja karena disini kita pake default

   ![serverapp4](https://user-images.githubusercontent.com/90166916/138643225-d96c6c22-71c0-4070-ac2e-3a0f5811e474.png)

 * tags juga bisa kalian skip

   ![serverapp6](https://user-images.githubusercontent.com/90166916/138643224-6bb4433a-1a30-4038-bd28-fe3e88c65485.png)

 * selanjutnya security groub kalian set rule kalian menjadi `all traffic` dan source nya kalian ganti menjadi `anywhere`

   ![serverapp7](https://user-images.githubusercontent.com/90166916/138643560-c09e1938-22c4-48b9-be03-f3c98691db1a.png)

 * lalu gunakan keypair yang sama seperti sebelumnya
 * terakhir tinggal launch instance.
 * selanjutnya Allocate Elastic IP untuk server apps.

   ![serveraws9](https://user-images.githubusercontent.com/90166916/138643215-24f05a41-560f-4de2-8f28-88c007d4ec60.png)

 * coba akses server `ssh -i dumbways.pem ubuntu@18.233.208.203`


  ![serveraws8](https://user-images.githubusercontent.com/90166916/138643219-dfbe4e6e-7cf0-4a5f-baac-d377c1efc581.png)

 
