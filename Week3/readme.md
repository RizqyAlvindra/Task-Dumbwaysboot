# Tugas DevOps Week3
# Manage Server With Terminal

* Apa itu Terminal  
  Terminal adalah sebuah command prompt dimana kita bisa mengontrol suatu file,membuat folder,lalu membuat dan mengubah suatu akses,dan masih banyak lagi yang bisa kita kerjakan di terminal.
* BASH(bourne again shell)
  Bash adalah suatu bahasa yang berjalan di linux dan mempunyai fungsi sebagai penerjemah antara user dan sistem operasi.
  
  contoh jika ingin meng-install nginx maka tinggal melakukan `sudo apt install nginx` 
  
# Teks Editor Menggunakan Nano
* Teks editor adalah sebuah aplikasi yang berjalan di atas terminal, dan gunanya sendiri untuk memanipulasi data pada suatu file. dan secara default sudah ada pada sistem operasi linux. untuk memeriksanya anda bisa menggunakan perintah ` nano -- Version `
* Cara membuka file dengan nano :
  contoh `nano alvin`

# Macam-Macam shortcut Nano
* `ctrl X` untuk keluar dari editor.
* `ctrl O` untuk mengubah nama file , tetapi juga bisa untuk save tanpa harus mengubah nama file , tekan saja `Enter` tetapi jika menggunakan ini kalian tidak akan keluar dari editor.
* `ctrl W` untuk mencari teks , contoh anda ingin mencari `FROM golang` secara otomatis anda akan di arahkan ke line yang ingin anda cari.
* `alt A` untuk memilih teks dengan cursor.
* `alt 6` untuk melakukan copy teks yang sudah di pilih.
* `ctrl U` untuk melakukan paste teks yang sudah di copy tadi.
* `ctrl K` untuk melakukan cut pada teks yang sudah di pilih.
* `ctrl A` untuk kembali ke awal baris.
* `ctrl E` untuk kembali ke akhir baris. 
# Manipulasi Teks
  sebenarnya kita bisa meng edit file di terminal tanpa menggunakan teks editor nano
* Berikut contoh perintah yang dapat di gunakan.
  1. cat
  2. sed
  3. grep
  4. sort
  5. echo
  
  
 Kita akan bahas satu persatu
* cat adalah suatu perintah yang dapat melihat isi dari suatu file tanpa harus membuka teks editor `nano` serta juga dapat membuat isi file pada output.
  
  Contoh penggunaan: 
  1. `cat alvin` untuk melihat isi file.
  2. `cat > file.alvin` untuk membuat file baru serta memasukan teks.
  3. `cat file.alvin file.alvin2 > file.alvin3` : untuk menggabungkan 2 file serta menyimpan juga ke file ke 3.
* sed(stream editor) adalah suatu perintah yang dapat melakukan manipulasi teks dasar pada file dengan cepat.

  Contoh penggunaan:
  1. `sed -i 's/hello/holla/g' file.alvin3` untuk mengganti kata hello menjadi holla di file.alvin ke 3.
* grep adalah suatu perintah untuk mencari sebuah teks dalam file yang sudah di buat.

  Contoh penggunaan:
  1. `grep semarang file.alvin3` secara otomatis akan mencari kata "semarang" di file.alvin3.
  2. `grep -c semarang file.alvin3` untuk menghitung berapa banyak sih kata "semarang" di file.alvin3.
  3. `grep alvin * ` untuk mencari kata "alvin" di semua file.
 * sort adalah perintah untuk mengurutkan data secara ascending maupun descending. 

  Contoh penggunaan:
  1. `sort file .alvin3` urutan dari yang terkecil hingga terbesar.
  2. `sort -r file.alvin3` urutan dari yang terbesar hingga terkecil.
* echo adalah perintah untuk mencetak pesan dari hasil perintah lain. 

  Contoh penggunaan:
  1. `echo "Semarang it's a Beautifull Place"` untuk mencetak pesan yang ingin kita buat.
  2. `echo "hello there" >> file.alvin3` untuk menambahkan teks di file yang di tentukan.
  3. `echo "goodbye" > file.alvin3` untuk me-replace semua teks yang ada di file.alvin3 dan diganti teksnya menjadi "goodbye".

# Monitoring 
  Monitoring adalah mengamati kinerja sistem secara realtime.
* contoh beberapa perintah yang dapat di gunakan untuk monitoring server.
    1. htop adalah suatu perintah untuk memonitoring system,kita juga dapat melihat berapa sih penggunaan memory dan cpu yang kta pakai.
       
       Cara instalasi htop : `sudo apt install htop -y`
       
       Gambar
    2. lsof(list open file) adalah perintah untuk melihat seluruh isi file aktif yang sedang berjalan di sistem.

       Contoh perintah : 
                         
                         1. `lsof` untuk menampilkan seluruh proses
                         
                         2. `lsof -u alvin` untuk menampilkan proses yang dilakukan oleh si user "alvin"
                         
                         3. `lsof -i:80` untuk menampilkan proses berjalan yang menggunakan port:80
      
    3. Ps (process status) adalah perintah untuk mengetahui proses yang sedang berjalan di sistem.

       Contoh perintah : 
       
       1.`ps -f -u alvin` adalah untuk menampilkan proses pada user "alvin"
       2.`ps -aux` adalah untuk menampilkan semua proses secara lengkap.
    
  
  
  # Network Firewall
  *
       
                      
