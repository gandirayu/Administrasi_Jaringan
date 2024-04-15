<div align="center">
  <h2 style="text-align: center;font-weight: bold">Praktikum 4<br>Instalasi DNS</h2>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h4 style="text-align: center;">Disusun Oleh :</h4>
  <p style="text-align: center;">
    <strong>Gandi Rukmaning Ayu (3122500016)</strong>
  </p>
<h4 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h4>
  <hr>
</div>

---

<span style="font-size:14px">
Berikut adalah langkah-lang untuk instalasi DNS sever menggunakan BIND9 pada Debian 12:
</span>

<span style="font-size:14px">

### 1. Install BIND 9
Perintah: `sudo apt install bind9 bind9-doc `

<div align="center">
    <img src="img/dns-1.png" alt="Install BIND9" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 1. Install BIND9</em>
</div><br>
</span>

<span style="font-size:14px">

### 2. Buka file named.conf
Perintah: `sudo nano /etc/bind/named.conf`

<div align="center">
    <img src="img/dns-2.png" alt="Buka file named.conf" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 2. Buka file named.conf</em>
</div><br>
</span>

<span style="font-size:14px">

### 3. Edit file named.conf

<div align="center">
    <img src="img/dns-3.png" alt="Edit file named.conf" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 3. Edit file named.conf</em>
</div><br>
File ini menentukan akses dari jaringan internal, seperti localhost dan jaringan 192.168.0.0/16. Selain itu, untuk mengelola server dari localhost ke port 953 dan melakukan konfigurasi tambahan dari beberapa file lain yang berisi pengaturan seperti option, local, dan default zone.
</span>

<span style="font-size:14px">

### 4. Buka file named.conf.options
Perintah: `sudo nano /etc/bind/named.conf.options`

<div align="center">
    <img src="img/dns-4.png" alt="Buka file named.conf.options" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 4. Buka file named.conf.options</em>
</div><br>
</span>

<span style="font-size:14px">

### 5. Edit file named.conf.options

<div align="center">
    <img src="img/dns-5.png" alt="Edit file named.conf.options" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 5. Edit file named.conf.options</em>
</div><br>
Pada bagian "Forwarding" mengatur server untuk meneruskan permintaan DNS ke server eksternal (1.1.1.1) jika tidak dapat menyelesaikannya sendiri. Sedangkan, bagian "Listen-on" menentukan alamat IP mana server akan mendengarkan permintaan DNS, yaitu 127.0.0.1 dan 192.168.3.1.
</span>

### 6. Buka file named.conf.local
Perintah: `sudo nano /etc/bind/named.conf.options`

<div align="center">
    <img src="img/dns-6.png" alt="Buka file named.conf.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 6. Buka file named.conf.local</em>
</div><br>
</span>

<span style="font-size:14px">

### 7. Edit file named.conf.local

<div align="center">
    <img src="img/dns-7.png" alt="Edit file named.conf.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 7. Edit file named.conf.local</em>
</div><br>
File `named.conf.local` mengatur zona-zona DNS lokal. Dalam konfigurasi ini, ada dua zona yang didefinisikan: "kelompok3.local" dan "3.168.192.in-addr.arpa". Server ditetapkan sebagai master untuk kedua zona tersebut. Informasi DNS disimpan dalam file database yang sesuai, dan konfigurasi juga memungkinkan pembaruan dinamis menggunakan kunci yang sesuai.
</span>

<span style="font-size:14px">

### 8. Memeriksa kesalahan sintaks file named.conf
Perintah: `sudo named-checkconf /etc/bind/named.conf`

<div align="center">
    <img src="img/dns-8.png" alt="Memeriksa kesalahan sintaks file named.conf" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 8. Memeriksa kesalahan sintaks file named.conf</em>
</div><br>
</span>

<span style="font-size:14px">

### 9. Buka file db.kelompok3.local
Perintah: `sudo nano /var/lib/bind/db.kelompok3.local`

<div align="center">
    <img src="img/dns-9.png" alt="Buka file db.kelompok3.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 9. Buka file db.kelompok3.local</em>
</div><br>
</span>

<span style="font-size:14px">

### 10. Edit file db.kelompok3.local

<div align="center">
    <img src="img/dns-10.png" alt="Edit file db.kelompok3.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 10. Edit file db.kelompok3.local</em>
</div><br>
File `db.kelompok3.local` adalah database zona untuk domain "kelompok3.local" dalam server DNS BIND. Dalam konfigurasi ini, terdapat catatan SOA yang menunjukkan server otoritatif dan parameter zona, catatan NS yang menetapkan server name untuk zona, serta catatan MX untuk mail server. Selain itu, terdapat catatan A yang menghubungkan nama `ns` ke alamat IP `192.168.3.1`, dan dua catatan CNAME yang membuat alias `www` dan `mail` menuju `ns`.
</span>

<span style="font-size:14px">

### 11. Buka file db.kelompok3.local.inv
Perintah: `sudo nano /var/lib/bind/db.kelompok3.local.inv`

<div align="center">
    <img src="img/dns-11.png" alt="Buka file db.kelompok3.local.inv" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 11. Buka file db.kelompok3.local.inv</em>
</div><br>
</span>

<span style="font-size:14px">

### 12. Edit file db.kelompok3.local.inv

<div align="center">
    <img src="img/dns-12.png" alt="Edit file db.kelompok3.local.inv" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 12. Edit file db.kelompok3.local.inv</em>
</div><br>
File `db.kelompok3.local.inv` adalah file zona reverse lookup untuk domain "kelompok3.local". Dalam konfigurasi ini, terdapat catatan SOA dan NS yang menunjukkan server otoritatif untuk zona ini adalah `ns.kelompok3.local`. Selain itu, terdapat catatan PTR yang mengaitkan alamat IP dengan nama host `ns.kelompok3.local`.
</span>

<span style="font-size:14px">

### 13. Memeriksa kesalahan sintaks file db.kelompok3.local
Perintah: `sudo named-checkzone kelompok3.local db.kelompok3.local`

<div align="center">
    <img src="img/dns-13.png" alt="Memeriksa kesalahan sintaks file db.kelompok3.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 13. Memeriksa kesalahan sintaks file db.kelompok3.local</em>
</div><br>
</span>

<span style="font-size:14px">

### 14. Memeriksa kesalahan sintaks file db.kelompok3.local.inv
Perintah: `sudo named-checkzone 3.168.192.inaddr-arpa db.kelompok3.local.inv`

<div align="center">
    <img src="img/dns-14.png" alt="Memeriksa kesalahan sintaks file db.kelompok3.local.inv" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 14. Memeriksa kesalahan sintaks file db.kelompok3.local.inv</em>
</div><br>
</span>

<span style="font-size:14px">

### 15. Buka file resolv.conf
Perintah: `sudo nano /etc/resolv.conf`

<div align="center">
    <img src="img/dns-15.png" alt="Buka file resolv.conf" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 15. Buka file resolv.conf</em>
</div><br>
</span>

<span style="font-size:14px">

### 16. Edit file resolv.conf

<div align="center">
    <img src="img/dns-16.png" alt="Edit file resolv.conf" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 16. Edit file resolv.conf</em>
</div><br>
File `db.kelompok3.local.inv` adalah file zona reverse lookup untuk domain "kelompok3.local". Dalam konfigurasi ini, terdapat catatan SOA dan NS yang menunjukkan server otoritatif untuk zona ini adalah `ns.kelompok3.local`. Selain itu, terdapat catatan PTR yang mengaitkan alamat IP dengan nama host `ns.kelompok3.local`.
</span>

<span style="font-size:14px">

### 17. Merestart BIND DNS
Perintah: `sudo systemctl restart named`

<div align="center">
    <img src="img/dns-17.png" alt="Merestart BIND DNS" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 17. Merestart BIND DNS</em>
</div><br>
</span>

<span style="font-size:14px">

### 18. Memeriksa status BIND DNS
Perintah: `sudo systemctl status named`

<div align="center">
    <img src="img/dns-18.png" alt="Memeriksa status BIND DNS" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 18. Memeriksa status BIND DNS</em>
</div><br>
</span>

<span style="font-size:14px">

### 19. Melakukan query DNS domain kelompok11.local
Perintah: `dig kelompok3.local`

<div align="center">
    <img src="img/dns-19.png" alt="Melakukan query DNS domain kelompok3.local" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 19. Melakukan query DNS domain kelompok3.local</em>
</div><br>
</span>

<span style="font-size:14px">

### 20. Melakukan reverse DNS lookup alamat IP 192.168.3.1
Perintah: `dig -x 192.168.3.1`

<div align="center">
    <img src="img/dns-20.png" alt="Melakukan reverse DNS lookup alamat IP 192.168.3.1" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 20. Melakukan reverse DNS lookup alamat IP 192.168.3.1</em>
</div><br>
</span>

<span style="font-size:14px">

### 21. Mencari server DNS domain
Perintah: `nslookup ns`

<div align="center">
    <img src="img/dns-21.png" alt="Mencari server DNS domain" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 21. Mencari server DNS domain</em>
</div><br>
</span>