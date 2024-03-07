<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 3<br>Cleaning The System</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Kelompok 3</h3>
  <p style="text-align: center;">
    <strong>Ade Hafis Rabbani (3122500001)</strong><br>
    <strong>Nadila Aulya Salsabila Mirdianti (3122500002)</strong><br>
    <strong>Gandi Rukmaning Ayu (3122500016)</strong>
  </p>
  
  <h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr>
</div>

## Daftar Isi

1. Disk Space Information
2. Cleaning The Package
3. Emptying The Trash Bin
4. Purging Application Caches
5. Purging The Thumbnails


## Cleaning The System
Meskipun hard disk semakin besar kapasitasnya, kita mungkin masih memerlukan ruang kosong. Ada beberapa skrip otomatis untuk membersihkan disk, tapi lebih baik periksa ruang yang tersedia terlebih dahulu menggunakan perintah **rm**.

### 1. Disk Space Information
Hal pertama yang harus dilakukan adalah mengetahui ruang yang digunakan oleh disk. Beberapa tools tersedia, dimulai dari terminal:
#### a. Disk space in terminal mode
Ringkasan penggunaan ruang disk untuk setiap pemsangan sistem (disk dan partisi) dengan perintah
_df -h_
  
![Gambar 8.6.1-1](images/8.6.1-1.png)

#### b. List your repertories sorted by decreasing size
Lihat direktori anda yang berukuran besar dengan perintah du dan sort (satuan yang digunakan adalah megabyte):
_du -ms * | sort -nr_
  
![Gambar 8.6.1-2](images/8.6.1-2.png)

#### c. Ncdu
Tools untuk melakukan analisis ruang disk dalam mode console. Gunakan perintah ncdu untuk menjalankan di terminal.
_sudo apt update && sudo apt install ncdu_
  
![Gambar 8.6.1-3](images/8.6.1-3.png)
![Gambar 8.6.1-4](images/8.6.1-4.png)

**_Ncdu dijalankan di folder pribadi pengguna_**

#### d. Baobab
Analisis ruang disk dalam mode grafis yang terintegrasi dengan Gnome, tetapi tersedia di environments lain.
_sudo apt update && sudo apt install baobab_
  
![Gambar 8.6.1-5](images/8.6.1-5.png)
![Gambar 8.6.1.-6](images/8.6.1.-6.png)

**_Baobab: Analisis ruang disk pada Gnome_**

### 2. Cleaning The Package
**Apt/aptitude/dpkg** adalah pengelola paket Debian. Ketika menginstall sebuah paket, file **archive- source/deb**-nya akan disimpan pada sistem di folder **/var/cache/apt/arsip/** untuk memungkinkan penginstalan ulang tanpa koneksi internet.
_sudo apt clean_
  
![Gambar 8.6.2-1](images/8.6.2-1.png)

Setelah cache dari paket-paket yang terinstal dibersihkan, kita juga dapat menghapus paket-paket yang tidak berguna dari sistem dan juga file-file konfigurasi. Ingatlah untuk memeriksa dengan teliti daftar paket yang akan dihapus sebelum dijalankan.
_sudo apt autoremove –purge_
  
![Gambar 8.6.2-2](images/8.6.2-2.png)

Jika telah mengupgrade sistem, ada kemungkinan beberapa paket tidak lagi tersedia pada repositori yang baru dikarenakan paket-paket tersebut sudah usang. Untuk membuat daftar dan menghapus paket-paket ini, gunakan apt dan ingatlah untuk memeriksa daftar paket yang akan dihapus.
_sudo apt list ‘?obsolete’
sudo apt remove ‘?obsolete’_
  
![Gambar 8.6.2-3](images/8.6.2-3.png)

Terakhir, untuk membuat daftar dan membersihkan file konfigurasi yang tetap ada meskipun aplikasi telah dihapus.
_dpkg –list | awk ‘/^rc/ {print $2}’
sudo apt purge $(dpkg –list | awk ‘/^rc/ {print $2}’)_
  
![Gambar 8.6.2-4](images/8.6.2-4.png)

Kita dapat menginstal tool deborphan yang berisi daftar paket-paket yatim piatu (paket-paket yang tidak bergantung pada paket lain) pada sistem. Ingatlah untuk memeriksa dengan seksama daftar paket yang akan dihapus.
_sudo apt install deborphan, echo $(deborphan)
sudo apt autoremove –purge $(deborphan)_
  
![Gambar 8.6.2-5](images/8.6.2-5.png)

### 3. Emptying The Trash Bin
Tiga sampah yang berbeda dan harus dipertimbangkan:
#### a. Sampah Pengguna:
**~/.local/share/Trash/**. Kita dapat mengosongkannya dengan manajer file sistem atau terminal.
_rm -Rf  ~/.local/share/Trash/*_

#### b. Sampah Administrator:
**/root/.local/share/Trash/**. Untuk mengosongkannya dengan cara yang benar, gunakan terminal dalam mode administrator.
_rm -Rf /root/.local/share/Trash/*_

#### c. Sampah Eksternal:
terletak di disk eksternal dan biasanya bernama **'/media/y- our_id/your_disk/.Trash_1000'**, di mana your_id sesuai dengan nama login.

![Gambar 8.6.3](images/8.6.3.png)


### 4. Purging Application Caches
Beberapa aplikasi yang menggunakan folder cache untuk menyimpan gambar, video, dan berbagai informasi lainnya agar dapat berjalan lebih cepat. Biasanya data ini tidak menghabiskan terlalu banyak ruang disk, namun jika kita mendeteksi bahwa sebuah folder menjadi terlalu besar, jangan ragu untuk menghapusnya.
 _rm -Rf ~/.cache/*_
   
![Gambar 8.6.4](images/8.6.4.png)

Setiap aplikasi memiliki caranya sendiri untuk mengelola cache-nya. ada yang menghapusnya secara sistematis ketika ditutup, ada yang menyimpan datanya di folder /tmp, yang akan dihapus saat sesi logout, ada juga yang menyimpan semua informasinya di folder tertentu.

### 5. Purging The Thumbnails
Setiap kali membuka folder yang berisi gambar atau video, thumbnail dibuat untuk mewakili file grafis ini. Thumbnail ini disimpan dalam folder tertentu untuk digunakan kembali, daripada dipaksa untuk menghitung ulang setiap kali Anda mengakses file semacam ini. Masalahnya akan muncul ketika menghapus file grafis, karena thumbnail-nya disimpan dalam sistem, dan ini menyebabkan sejumlah ruang disk terbuang untuk menyimpan thumbnail yang sudah tidak terpakai. Untuk menghapusnya, cukup dengan menghapus folder yang bersangkutan.
_rm -Rf ~/.thumbnails_
   
![Gambar 8.6.5](images/8.6.5.png)

Folder ini akan dibuat lagi, pada saat sistem perlu menyimpan thumbnail yang baru dibuat.
