<div align="center">
  <h3 style="text-align: center;font-weight: bold">Praktikum 5<br>Konfigurasi Roundcuber</h3>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h5 style="text-align: center;">Disusun Oleh :</h5>
  <p style="text-align: center;">
    <strong>Gandi Rukmaning Ayu (3122500016)</strong>
  </p>
<h4 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika</h4>
<h5>2023/2024</h5>
</div>

---

## 1. Buat Database yang akan digunakan oleh Roundcube
- Masuk ke MySQL
```mysql -u root -p```
- Buat Database
```CREATE DATABASE roundcubemail;```
- Buat User
```CREATE USER 'roundcube'@'localhost' IDENTIFIED BY 'password';```
- Berikan Hak Akses
```grant all privileges on roundcube.* to roundcube@'localhost' identified by 'password'; ```
<img src="img/r1.png" alt="" width="100%" height="auto">

## 2. Install Roundcube
```sudo apt-get install -y roundcube roundcube-mysql```
<img src="img/r2-1.png" alt="" width="100%" height="auto">
<img src="img/r2-2.png" alt="" width="100%" height="auto">

## 3. Konfigurasi Roundcube
- Masuk ke direktori konfigurasi
```cd /usr/share/dbconfig-common/data/roundcube/install/```
<img src="img/r3-1.png" alt="" width="100%" height="auto">

- import database
```mysql -u roundcube -D roundcube -p < mysql``` kemudian masukkan password yang telah dibuat sebelumnya
<img src="img/r3-2.png" alt="" width="100%" height="auto">

- Konfigurasi database
```sudo nano /etc/roundcube/debian-db.php```
<img src="img/r3-3.png" alt="" width="100%" height="auto">
sesuaikan credential database dengan yang telah dibuat sebelumnya
- Konfigurasi Roundcube
```sudo nano /etc/roundcube/config.inc.php```
    - ubah line 27 ``` $config['imap_host'] = ["tls://mail.kelompok3.local:143"];```
    - ubah line 31 ``` $config['smtp_host'] = 'tls://mail.kelompok3.local:587'; ```
    - ubah line 39 ``` $config['smtp_pass'] = '%p'; ``` 
    - ubah line 46 ``` $config['product_name'] = 'Server Mail PENS'; ```
    - tambah pada baris paling akhir
    ```
    $config['smtp_auth_type'] = 'LOGIN';
    // specify SMTP HELO host
    $config['smtp_helo_host'] = 'mail.kelompok3.local';

    // specify domain name
    $config['mail_domain'] = 'mail.kelompok3.local';

    // specify UserAgent
    $config['useragent'] = 'Server World Webmail';
    // specify SMTP and IMAP connection option
    $config['imap_conn_options'] = array(
        'ssl'         => array(
            'verify_peer' => true,
            'CN_match' => 'kelompok3.local',
            'allow_self_signed' => true,
            'ciphers' => 'HIGH:!SSLv2:!SSLv3',
        ),
    );
    $config['smtp_conn_options'] = array(
    'ssl'   => array(
            'verify_peer' => true,
            'CN_match' => 'kelompok3.local',
            'allow_self_signed' => true,
            'ciphers' => 'HIGH:!SSLv2:!SSLv3',
        ),
    );
    ```
  <img src="img/r3-4.png" alt="" width="100%" height="auto">
  <img src="img/r3-5.png" alt="" width="100%" height="auto">
  <img src="img/r3-6.png" alt="" width="100%" height="auto">
  <img src="img/r3-7.png" alt="" width="100%" height="auto">

    - konfigurasi webserver untuk roundcube ```sudo nano  /etc/apache2/conf-enabled/roundcube.conf```
    uncomment baris ke 3
    ```Alias /roundcube /var/lib/roundcube/public_html```
  <img src="img/r3-8.png" alt="" width="100%" height="auto">
  <img src="img/r3-9.png" alt="" width="100%" height="auto">