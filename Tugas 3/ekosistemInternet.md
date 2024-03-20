<div align="center">
  <h2 style="text-align: center;font-weight: bold">Praktikum 4<br>Ekosistem Internet</h2>
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

## Daftar Isi

[1. Ekosistem Internet](#ekosistem-internet)
[2. Internet](#internet)
[3. IP Addressing & Routing System](#ip-addressing--routing-system)
[4. Naming System](#naming-system)
[5. Domain Name System (DNS)](#domain-name-system-dns)
[6. Standards Bodies](#standards-bodies)
[7. Server Providers](#server-providers)
[8. Registries](#registries)
[9. Other Entities](#other-entities)

---

## Ekosistem Internet

<div align="center">
    <img src="/images/1.1.png" alt="Ekosistem Internet" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 1. Ekosistem Internet</em>
</div><br>

<span style="font-size:14px">
Ekosistem Internet merupakan istilah untuk menggambarkan organisasi dan komunitas yang memimpin operasi serta pengembangan teknologi dan infrastruktur internet global. Hal ini melibatkan berbagai aktor dengan kepemilikan dan kontrol yang tersebar untuk mendukung perkembangan teknologi internet yang cepat dan berkelanjutan.
<br/><br/>
Oraganisasi yang membentuk Ekosistem Internet:

- Badan-badan standar teknis seperti <strong>Internet Engineering Task Force (IETF)</strong> dan <strong>World Wide Web Consortium (W3C)</strong>.
- Organisasi yang mengelola sumber daya untuk pengalamatan global seperti <strong>Internet Corporation for Assigned Names and Numbers (ICANN)</strong>, termasuk pengoperasian fungsi <strong>Internet Assigned Numbers Authority (IANA)</strong>, <strong>Regional Internet Registries (RIR)</strong>, dan <strong>Doman Name Registries and Registrars</strong>.
- Perusahaan yang menyediakan layanan infrastruktur jaringan seperti penyedia <strong>Domain Name Service (DNS)</strong>, <strong>providers</strong>, dan <strong>Internet Exchange Point (IXP)</strong>.
- Individu dan Organisasi yang menggunakan Internet untuk berkomunikasi satu sama lain dan menawarkan layanan.
- Organisasi yang menyediakan pendidikan dan membangun kapasitas untuk mengembangkan dan menggunakan teknologi Internet, seperti organisasi multilateral, lembaga pendidikan, dan lembaga pemerintah
</span>

---

## Internet

<div align="center">
    <img src="/images/2.1.png" alt="Internet" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 2. Internet</em>
</div><br>

<span style="font-size:14px">
Gambar diatas menjunjukkan diagram jaringan komputter yang terdiri dari berbagai kompeonen untuk menghubungkan dan memungkinkan komunikasi antar komputer. Komponen-komponen tersebut diantaranya Server, Komputer, Router, Switch, Modem: Mengubah sinyal analog dari saluran telepon menjadi sinyal digital yang dapat digunakan oleh komputer dan Kabel. Secara teknis internet sebagai routing system dan naming system. Sedangkan secara arsitektur, internet sebagai standarisasi, penyedia layanan, intenet register dan clearing house.
</span>

---

## IP Addressing & Routing System

#### a. Routing
<div align="center">
    <img src="/images/3.1.png" alt="Routing" width="50%" height="auto"><br>
    <em style="font-size:10px">Gambar 3. a) Routing</em>
</div><br>

<span style="font-size:14px">
Adanya alamat yang mengarah ke situs web diikuti dengan data yang akan ditransfer. Kebijakan merupakan kunci untuk memahami tingkat <em>AS (Overlay Network)</em>. <strong>BGP (Border Gateway Protocol)</strong> mengatur kebijakan yang terdistribusi dengan jenis penyedia untuk memaksimalkan pendapatan dan memininalkan biaya.
</span>

#### b. Peering Connections
<div align="center">
    <img src="/images/3.2.png" alt="Peering Connections" width="50%" height="auto"><br>
    <em style="font-size:10px">b) Peering Connections</em>
</div><br>

<span style="font-size:14px">
Untuk memahami kebijakan ini membutuhkan pemangaman mengenai peering models yang mencakup provider atau customer, transit dan settlement free.
</span>

#### c. Edge Provider Routing Policy
<div align="center">
    <img src="/images/3.3.png" alt="Edge Provider Routing Policy" width="50%" height="auto"><br>
    <em style="font-size:10px">c) Edge Provider Routing Policy</em>
</div><br>

<span style="font-size:14px">
Jadilah jalur yang dipilih oleh pelanggan yang terhubung. Pilih jalur lalu lintas yang paling pendek dengan waktu sesingkat mungkin, ini dikenal sebagai <em>hot potato routing</em>.
</span>

#### d. Transit Provider Routing Policy
<div align="center">
    <img src="/images/3.3.png" alt="Transit Provider Routing Policy" width="50%" height="auto"><br>
    <em style="font-size:10px"> d) Transit Provider Routing Policy</em>
</div><br>

<span style="font-size:14px">
Meningkatkan peering untuk mempersingkat jalur AS dan membawa sebanyak mungkin lalu lintas dengan jarak sesingkat mungkin, ini dikenal sebagai <em>hot potato routing</em>.
</span>

#### e. Content Provider Routing Policy

<span style="font-size:14px">
Mengirimkan konten secepat mungkin dengan menyebarkan peer sebanyak mungkin menggunakan distribusi konten ke setiap sudut jaringan dan mengangkut lalu lintas melalui link internal untuk kontrol pengalaman pengguna yang optimal. Hal ini dikenal sebagai <em>cold potato routing</em>.
</span>

---

## Naming System

<div align="center">
    <img src="/images/4.1.png" alt="Naming System" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 4. Naming System</em>
</div><br>

<span style="font-size:14px">
Gambar diatas menunjukkan cara kerja DNS dalam jaringan. ICANN akan mengkoordinasikan system penamaan internet dan Registries akan mengelola <strong>Top Level Domain (TLD)</strong> seperti <em>.com, .org</em> dan <em>.id</em>. Pada bagian Registries menyediakan layanan DNS kepada registrar yang menjual nama domain kepada pengguna. Kemudian DNS yang akan menerjemahkan nama domain ke alamat IP, ini dikenal sebagai <em>Name to location mapping</em>.
</span>

---

## Domain Name System (DNS)

<div align="center">
    <img src="/images/5.png" alt="Domain Name System (DNS)" width="60%" height="auto"><br>
    <em style="font-size:10px">Gambar 5. Domain Name System (DNS)</em>
</div><br>

#### a. DNS Hierarchy Tree

<div align="center">
    <img src="/images/5.1.png" alt="Domain Name System (DNS)" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 5. a) DNS Hierarchy Tree</em>
</div><br>

<span style="font-size:14px">
DNS Hierarchy Tree adalah struktur yang mencakup semua domain di Internet dalam lima level. Dimulai dari Root Level Domain sebagai level teratas yaitu TLD. Kemudian, ada <strong>Second Level Domains (SLD)</strong>, serta Subdomains. Level terakhir adalah Hosts, yang merupakan segmen paling spesifik seperti example.com. Dengan struktur ini, pengguna dapat mengakses situs web menggunakan nama domain tanpa perlu mengingat alamat IP yang rumit.
</span>

#### b.	DNS Components

<div align="center">
    <img src="/images/5.2.png" alt="DNS Components" width="80%" height="auto"><br>
    <em style="font-size:10px">b) DNS Components</em>
</div><br>

<span style="font-size:14px">
DNS memudahkan konversi antara nama domain dan alamat IP. Ini terdiri dari beberapa komponen penting, yaitu Namespace (daftar lengkap domain), Nameserver (server penyimpan informasi domain), Resolver (program yang mengirim permintaan DNS) dan Client (komputer yang mengirim permintaan DNS ke resolver).
</span>

#### c.	Domains

<div align="center">
    <img src="/images/5.3.png" alt="Domains" width="80%" height="auto"><br>
    <em style="font-size:10px">c) Domains</em>
</div><br>

<span style="font-size:14px">
Server root sebagai pusat pengelolaan semua domain di internet, di bawahnya terdapat contoh domain tingkat atas seperti .id dan .com, serta domain tingkat kedua seperti .co.id dan .ac.id. Contoh domain juga mencakup subdomain seperti www.pens.ac.id untuk web pendidikan, www.detik.com dan www.kompas.com untuk web berita. Bagian bawah gambar menekankan penggunaan domain untuk situs web dan subdomain untuk layanan email.
</span>

#### d.	Name Server

<div align="center">
    <img src="/images/5.4.png" alt="Name Server" width="50%" height="auto"><br>
    <em style="font-size:10px">d) Name Server</em>
</div><br>

<span style="font-size:14px">

</span>

#### e.	Authoritative Nameserver

<div align="center">
    <img src="/images/5.5.png" alt="Authoritative Nameserver" width="50%" height="auto"><br>
    <em style="font-size:10px">e) Authoritative Nameserver</em>
</div><br>

<span style="font-size:14px">

</span>

#### f.	Recursive Nameserver

<div align="center">
    <img src="/images/5.6.png" alt="Recursive Nameserver" width="50%" height="auto"><br>
    <em style="font-size:10px">f) Recursive Nameserver</em>
</div><br>

<span style="font-size:14px">

</span>

#### g.	Root Servers

<span style="font-size:14px">

</span>

#### h.	Root Server Deployment at APNIC

<span style="font-size:14px">

</span>

#### i.	Resource Records

<div align="center">
    <img src="/images/5.7.png" alt="Resource Records" width="100%" height="auto"><br>
    <em style="font-size:10px">i) Resource Records</em>
</div><br>

<span style="font-size:14px">

</span>

#### j.	Common Resource Record Types

<div align="center">
    <img src="/images/5.8.png" alt="Common Resource Record Types" width="100%" height="auto"><br>
    <em style="font-size:10px">j) Common Resource Record Types</em>
</div>

#### k.	Example: RRs in a Zone File

<div align="center">
    <img src="/images/5.9.png" alt="Example: RRs in a Zone File" width="100%" height="auto"><br>
    <em style="font-size:10px">k) Example: RRs in a Zone File</em>
</div><br>

<span style="font-size:14px">

</span>

#### l.	DNS Data Flow

<div align="center">
    <img src="/images/5.10.png" alt="DNS Data Flow" width="80%" height="auto"><br>
    <em style="font-size:10px">l) DNS Data Flow</em>
</div><br>

<span style="font-size:14px">

</span>

#### m.	Delegating a Zone

<div align="center">
    <img src="/images/5.11.png" alt="Delegating a Zone" width="100%" height="auto"><br>
    <em style="font-size:10px">m) Delegating a Zone</em>
</div><br>

<span style="font-size:14px">

</span>

#### n.	Glue Record

<div align="center">
    <img src="/images/5.12.png" alt="Glue Record" width="100%" height="auto"><br>
    <em style="font-size:10px">n) Glue Record</em>
</div><br>

<span style="font-size:14px">

</span>

---

## Standards Bodies

<div align="center">
    <img src="/images/6.png" alt="Standards Bodies" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 6. Standards Organizations</em>
</div><br>

<span style="font-size:14px">

</span>

---

## Server Providers

#### a. Content Provider Overview

<span style="font-size:14px">

</span>

#### b. Access Provider Overview

<span style="font-size:14px">

</span>

#### c. Transit Provider overview

<div align="center">
    <img src="/images/7.1.png" alt="Transit Provider overview" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 7. a) Transit Provider overview</em>
</div><br>

<span style="font-size:14px">

</span>

#### d. Internet Exchange Point Overview

<div align="center">
    <img src="/images/7.2.png" alt="Internet Exchange Point Overview" width="100%" height="auto"><br>
    <em style="font-size:10px">b) Internet Exchange Point Overview</em>
</div><br>

<span style="font-size:14px">

</span>

---

## Registries

#### a. Naming Authorities

<span style="font-size:14px">

</span>

#### b. Regional Registry Overview

<div align="center">
    <img src="/images/8.png" alt="Regional Registry Overview" width="100%" height="auto"><br>
    <em style="font-size:10px">Gambar 8. Regional Registry Overview</em>
</div><br>

<span style="font-size:14px">

</span>

#### c. Top Level Registries

<span style="font-size:14px">

</span>

#### d. Second Tier Registries

<span style="font-size:14px">

</span>

---

## Other Entities

#### a. Clearing House

<span style="font-size:14px">

</span>

#### b. Internet Route Registries

<span style="font-size:14px">

</span>

#### c. Network Operators Groups

<span style="font-size:14px">

</span>