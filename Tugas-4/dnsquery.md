<div align="center">
  <h2 style="text-align: center;font-weight: bold">Praktikum 4<br>DNS Query</h2>
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

### Bagaimana Cara kerja dari iterative dan recursive dari DNS Query, ada 8 step, dari PC anda! misal akses detik.com

<span style="font-size:14px">
Berikut adalah 8 langkah cara kerja iterative dan recursive DNS query saat Anda mengakses detik.com dari PC Anda:

#### 1. Permintaan DNS (DNS Query)
Anda mengetikkan "detik.com" di browser web. PC Anda (resolver DNS) mengirimkan permintaan DNS (recursive query) ke server DNS lokal (ISP).

#### 2. Server DNS Lokal (ISP)
Server DNS lokal memeriksa cache-nya. Jika alamat IP detik.com ditemukan di cache, server DNS lokal langsung memberikan respons ke PC Anda (langkah 8). Jika alamat IP detik.com tidak ditemukan di cache, server DNS lokal memulai proses iterative query (langkah 3).

#### 3. Root Nameserver
Server DNS lokal mengirimkan permintaan DNS ke root nameserver. Root nameserver memberikan daftar server TLD (Top-Level Domain) yang bertanggung jawab untuk domain ". com".

#### 4. TLD Nameserver (.com)
Server DNS lokal mengirimkan permintaan DNS ke server TLD ".com". Server TLD ".com" memberikan daftar nameserver authoritative untuk domain "detik.com".

#### 5. Authoritative Nameserver (detik.com)
Server DNS lokal mengirimkan permintaan DNS ke authoritative nameserver untuk "detik.com". Authoritative nameserver memberikan alamat IP detik.com ke server DNS lokal.

#### 6. Respons ke PC Anda
Server DNS lokal menerima alamat IP detik.com dari authoritative nameserver. Server DNS lokal memberikan alamat IP detik.com ke PC Anda.

#### 7. Cache DNS Lokal
Server DNS lokal menyimpan alamat IP detik.com di cache-nya untuk mempercepat permintaan di masa depan.

#### 8. Koneksi ke Website
PC Anda menggunakan alamat IP detik.com untuk terhubung ke website detik.com.
</span>