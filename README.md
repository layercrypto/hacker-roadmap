<p align="center">
    <img src="https://i.imgur.com/VeEYEkT.png" alt="Hacker roadmap" /><br>
</p>

Repository ini adalah gambaran tentang apa yang perlu Anda pelajari dalam penetration testing dan kumpulan alat-alat hacking, sumber daya, dan referensi untuk berlatih ethical hacking. Sebagian besar alat-alat ini kompatibel dengan UNIX, gratis, dan open source.

## Status

**Proyek ini telah diarsipkan**. Konten mungkin sudah tidak terbaru. Saya dan beberapa teman sedang mengerjakan proyek baru yang akan menggantikan keseluruhan repositori ini. Tujuannya tetap sama: menyediakan sumber daya tentang keamanan informasi profesional bagi pemula, dengan fokus lengkap pada pelatihan, sertifikasi, dan persyaratan pekerjaan. Kami tidak berharap proyek baru ini akan selesai sebelum Q1 2023.

---

## Sebelum Anda memulai

-   Jika Anda baru dalam keamanan informasi, lupakan segala hal yang Anda ketahui tentang hacking.
-   Jangan mulai menggunakan alat-alat tanpa membaca tentang pen testing dan bagaimana cara kerjanya (lihat bagian [Sumber daya tambahan](#additional-resources)).
-   Jangan mengunduh atau menggunakan alat-alat jika Anda belum memeriksa kode-kodenya.
-   Jangan gunakan alat-alat ini untuk melakukan hal-hal bodoh seperti menyelidiki/hack tanpa persetujuan pada teman Anda, atau yang lebih buruk, rekruter Anda.
-   Baca buku, manual, artikel, jadilah penasaran, dan jangan hanya menjadi [script kiddie](https://www.wikihow.com/Avoid-Becoming-a-Script-Kiddie) saja.
-   Saya berharap Anda tidak menggunakan alat-alat ini untuk tujuan illegal, tetapi jika Anda melakukannya, saya berharap Anda tahu apa yang Anda lakukan.
-   Berlatih menggunakan [challenges](#challenges), bukan target yang nyata!

# Daftar Isi

-   [Pengantar](#introduction)
    -   [Apa itu penetration testing?](#what-is-penetration-testing)
    -   [Ingin menjadi penetration tester?](#want-to-become-a-penetration-tester)
-   [Beberapa kosakata](#some-vocabulary)
-   [Perbedaan antara hacking dan ethical hacking](#difference-between-hacking-and-ethical-hacking)
-   [Bahasa](#languages)
-   [Sistem Manajemen Konten](#content-management-systems)
-   [Langkah-langkah dasar pen testing](#basic-steps-of-pen-testing)
-   [Alat-alat berdasarkan kategori](#tools-by-category)
    -   [:male_detective: Information Gathering](#male_detective-information-gathering)
    -   [:lock: Password Attacks](#lock-password-attacks)
        -   [:memo: Wordlists](#memo-wordlists)
    -   [:globe_with_meridians: Wireless Testing](#globe_with_meridians-wireless-testing)
    -   [:wrench: Exploitation Tools](#wrench-exploitation-tools)
    -   [:busts_in_silhouette: Sniffing & Spoofing](#busts_in_silhouette-sniffing--spoofing)
    -   [:rocket: Web Hacking](#rocket

-web-hacking)

-   [:tada: Post Exploitation](#tada-post-exploitation)
-   [:package: Frameworks](#package-frameworks)
-   [Sumber daya tambahan](#additional-resources)
    -   [Buku / Manual](#books--manuals)
    -   [Diskusi](#discussions)
    -   [Informasi Keamanan](#security-advisories)
    -   [Challenges](#challenges)
-   [Lisensi](#license)

(TOC dibuat dengan [nGitHubTOC](https://imthenachoman.github.io/nGitHubTOC/))

# Pengantar

## Apa itu penetration testing?

Penetration testing adalah jenis pengujian keamanan yang digunakan untuk menguji keamanan suatu aplikasi. Tujuannya adalah untuk menemukan risiko keamanan yang mungkin ada dalam suatu sistem.

Jika suatu sistem tidak aman, maka seorang penyerang mungkin dapat mengganggu atau mengambil alih kontrol sistem tersebut tanpa izin. Risiko keamanan biasanya merupakan kesalahan yang tidak disengaja yang terjadi saat mengembangkan dan mengimplementasikan perangkat lunak. Misalnya, kesalahan konfigurasi, kesalahan desain, dan bug perangkat lunak, dll. [Pelajari lebih lanjut](https://www.tutorialspoint.com/penetration_testing/penetration_testing_quick_guide.htm)

## Ingin menjadi seorang penetration tester?

Mengetahui tentang risiko di internet dan bagaimana cara mencegahnya sangat berguna, terutama sebagai seorang pengembang. Web hacking dan penetration testing adalah versi 2.0 dari pertahanan diri! Tetapi apakah hanya mengetahui tentang alat-alat dan cara menggunakannya sudah cukup untuk menjadi seorang pen tester? Tentu saja tidak. Seorang penetration tester yang sebenarnya harus dapat bekerja secara cermat dan mendeteksi kelemahan dari suatu aplikasi. Mereka harus dapat mengidentifikasi teknologi di baliknya dan menguji setiap pintu yang mungkin terbuka bagi para hacker.

Repository ini bertujuan pertama-tama untuk membangun metode refleksi dalam penetration testing dan menjelaskan bagaimana cara mengamankan suatu aplikasi. Dan kedua, untuk mengumpulkan semua jenis alat atau sumber daya yang dibutuhkan oleh pen testers. **Pastikan Anda mengetahui dasar-dasar bahasa pemrograman dan keamanan internet sebelum mempelajari pen testing.**

Selain itu, penting untuk menginformasikan diri Anda tentang hukum dan apa yang diizinkan atau tidak diizinkan. Menurut negara Anda, hukum komputer tidak sama. Pertama, periksa hukum tentang privasi dan pengawasan: [Negara-negara Nine Eyes](https://en.wikipedia.org/wiki/Five_Eyes#Other_international_cooperatives), [Five Eyes](https://en.wikipedia.org/wiki/Five_Eyes), dan Fourteen Eyes. Selalu periksa apakah apa yang Anda lakukan legal. Bahkan ketika tidak bersifat menyerang, pengumpulan informasi juga dapat ilegal!

([Daftar Isi](#table-of-contents))

# Beberapa kosakata

**Infosec**: Keamanan informasi, yang merupakan praktik untuk mencegah akses, penggunaan, pengungkapan, gangguan, modifikasi, inspeksi, pencatatan, atau penghancuran informasi yang tidak sah. Informasi atau data tersebut dapat berbentuk elektronik atau fisik. Infosec juga dapat merujuk pada seseorang yang menjalankan keamanan etis. [Wikipedia](https://en.wikipedia.org/wiki/Information_security)

**Opsec**: Keamanan operasional, yang merupakan proses yang mengidentifikasi informasi kritis untuk menentukan apakah tindakan yang dilakukan dapat diamati oleh intelijen musuh, menentukan apakah informasi yang

diperoleh oleh lawan dapat diinterpretasikan sebagai berguna bagi mereka, dan kemudian melaksanakan tindakan yang dipilih untuk menghilangkan atau mengurangi eksploitasi informasi kritis dari pihak lawan. [Wikipedia](https://en.wikipedia.org/wiki/Operations_security)

**Black/grey/white hat hacker**: Seseorang yang menggunakan bug atau eksploitasi untuk meretas sistem atau aplikasi. Tujuan dan metode mereka berbeda tergantung apakah mereka adalah black hat, grey hat, atau white hat hacker. Black hat adalah seseorang yang jahat yang tidak menunggu izin untuk meretas sistem atau aplikasi. White hat biasanya adalah seorang peneliti keamanan yang menjalankan ethical hacking. Grey hat berada di tengah-tengah antara kedua jenis hacker ini, mereka mungkin ingin berbuat jahat jika itu bisa memberikan manfaat (penyusupan data, uang, whistleblowing, dll).

**Tim merah**: Menurut Wikipedia, tim merah adalah kelompok independen yang menantang suatu organisasi untuk meningkatkan efektivitasnya dengan mengasumsikan peran atau sudut pandang lawan. Hal ini terutama efektif dalam organisasi dengan budaya kuat dan cara yang tetap dalam menghadapi masalah. Komunitas intelijen Amerika Serikat (militer dan sipil) memiliki tim merah yang mengeksplorasi masa depan alternatif dan menulis artikel seolah-olah mereka adalah pemimpin dunia asing. Sedikit doktrin formal atau publikasi tentang Tim Merah di militer. Dalam latihan infosec, Tim Merah berperan sebagai penyerang. [Wikipedia](https://en.wikipedia.org/wiki/Red_team)

**Tim biru**: Tim biru adalah kelompok individu yang melakukan analisis terhadap sistem informasi untuk memastikan keamanannya, mengidentifikasi kelemahan keamanan, memverifikasi efektivitas setiap langkah keamanan, dan memastikan semua langkah keamanan akan tetap efektif setelah implementasi. Sebagai hasilnya, tim biru dikembangkan untuk merancang langkah-langkah pertahanan terhadap aktivitas tim merah. Dalam latihan infosec, anggota Tim Biru berperan sebagai pembela. [Wikipedia](<https://en.wikipedia.org/wiki/Blue_team_(computer_security)>)

**Penetration tester**: Seorang ethical hacker yang menjalankan keamanan, menguji aplikasi dan sistem untuk mencegah intrusi atau menemukan kerentanan.

**Peneliti keamanan**: Seseorang yang menjalankan pen testing dan menjelajahi web untuk menemukan situs phishing/palsu, server terinfeksi, bug atau kerentanan. Mereka dapat bekerja untuk perusahaan sebagai konsultan keamanan dan kemungkinan besar sebagai anggota Tim Biru.

**Reverse engineering**: Reverse engineering, juga disebut back engineering, adalah proses di mana suatu objek buatan manusia didekonstruksi untuk mengungkapkan desain, arsitektur, atau untuk mengekstrak pengetahuan dari objek tersebut. Mirip dengan penelitian ilmiah, satu-satunya perbedaan adalah bahwa penelitian ilmiah berhubungan dengan fenomena alam. [Wikipedia](https://en.wikipedia.org/wiki/

Reverse_engineering)

**Social engineering**: Dalam konteks keamanan informasi, istilah ini mengacu pada manipulasi psikologis terhadap orang-orang untuk melakukan tindakan atau mengungkapkan informasi rahasia. Jenis penipuan kepercayaan untuk tujuan pengumpulan informasi, penipuan, atau akses sistem, berbeda dari "kon" tradisional karena sering menjadi salah satu langkah dalam skema penipuan yang lebih kompleks. Istilah "social engineering" sebagai tindakan manipulasi psikologis terhadap manusia juga terkait dengan ilmu sosial, tetapi penggunaannya telah menjadi umum di kalangan profesional keamanan komputer dan informasi. [Wikipedia](<https://en.wikipedia.org/wiki/Social_engineering_(security)>)

**Analisis ancaman**: Seorang penelusur ancaman, juga disebut sebagai analis ancaman keamanan siber, adalah profesional keamanan atau penyedia layanan manajemen (MSP) yang secara proaktif menggunakan teknik manual atau berbantuan mesin untuk mendeteksi insiden keamanan yang mungkin terlewat oleh sistem otomatis. Threat hunter bertujuan untuk mengungkapkan insiden yang sebaliknya tidak akan diketahui oleh perusahaan, memberikan kepala petugas keamanan informasi (CISO) dan kepala petugas informasi (CIO) dengan lapisan pertahanan tambahan terhadap ancaman yang bertahan lama (APTs) yang canggih. [SearchCIO](https://searchcio.techtarget.com/definition/threat-hunter-cybersecurity-threat-analyst)

([Daftar Isi](#table-of-contents))

# Perbedaan antara hacking dan ethical hacking

Seorang black hat hacker melakukan penetration testing, tetapi tidak seperti white hat hacker, ini tidak termasuk dalam ethical hacking. Ethical hacking bertujuan untuk menemukan kerentanan dan meningkatkan keamanan suatu sistem. Seorang ethical hacker adalah seorang profesional keamanan yang ulung. Ethical hacker tahu bagaimana menemukan dan mengeksploitasi kerentanan dan kelemahan dalam berbagai sistem, sama seperti hacker jahat (black hat hacker). Pada dasarnya, mereka menggunakan keterampilan yang sama; namun, ethical hacker menggunakan keterampilan tersebut secara sah dan legal untuk mencari kerentanan dan memperbaikinya sebelum para pelaku jahat mencoba memanfaatkannya. Seorang ethical hacker pada dasarnya adalah seorang white hat hacker.

([Table of Contents](#table-of-contents))

# Bahasa Pemrograman

Belajar pemrograman adalah langkah awal yang sangat penting untuk mempelajari keamanan. Ada banyak bahasa pemrograman, dan kebanyakan orang memulai dengan Python karena itu adalah bahasa yang paling mudah dan populer. PHP dan Go kurang populer untuk menulis hal-hal yang berkaitan dengan keamanan, tetapi kedua bahasa tersebut masih dapat digunakan dalam konteks tersebut. Bash dan Powershell lebih banyak digunakan untuk scripting dan penulisan aplikasi CLI sederhana.

Karena tidak semua bahasa bekerja dengan cara yang sama, Anda perlu memahami cara kerjanya dan apa yang ingin Anda pelajari. Misalnya, C++ dan Java dikompilasi, sedangkan PHP dan Python bukan, karena mereka adalah bahasa yang diinterpretasikan. Ini tentu saja memengaruhi penggunaan bahasa tersebut. Setiap bahasa juga memiliki pola desainnya sendiri.

### Scripting

-   Bash
-   Powershell

### Perangkat lunak & aplikasi seluler

-   Java
-   Swift
-   C / C++ / C#

### Tujuan umum

-   Python
-   Ruby
-   Perl
-   PHP
-   Go

([Table of Contents](#table-of-contents))

# Sistem Manajemen Konten

-   Wordpress
-   Joomla
-   Drupal
-   SPIP

Ini adalah Sistem Manajemen Konten (CMS) yang paling banyak digunakan. Lihat daftar lengkapnya [di sini](https://en.wikipedia.org/wiki/List_of_content_management_systems).

([Table of Contents](#table-of-contents))

# Langkah Dasar dalam Penetration Testing

<p align="center">
    <img src="https://www.tutorialspoint.com/penetration_testing/images/penetration_testing_method.jpg">
</p>

_Source: [tutorialspoint](https://www.tutorialspoint.com/penetration_testing/index.htm)_

[Read more about pen testing methodology](https://www.tutorialspoint.com/penetration_testing/penetration_testing_method.htm)

([Table of Contents](#table-of-contents))

# Tools by category

A more complete list of tools can be found on [Kali Linux official website](https://tools.kali.org/tools-listing).

#### :male_detective: Information Gathering

Information Gathering tools allows you to collect host metadata about services and users. Check informations about a domain, IP address, phone number or an email address.

| Tool                                                     | Language   | Support               | Description                                                                                                                   |
| -------------------------------------------------------- | ---------- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [theHarvester](https://github.com/laramies/theHarvester) | **Python** | `Linux/Windows/macOS` | E-mails, subdomains and names Harvester.                                                                                      |
| [CTFR](https://github.com/UnaPibaGeek/ctfr)              | **Python** | `Linux/Windows/macOS` | Abusing Certificate Transparency logs for getting HTTPS websites subdomains.                                                  |
| [Sn1per](https://github.com/1N3/Sn1per)                  | **bash**   | `Linux/macOS`         | Automated Pentest Recon Scanner.                                                                                              |
| [RED Hawk](https://github.com/Tuhinshubhra/RED_HAWK)     | **PHP**    | `Linux/Windows/macOS` | All in one tool for Information Gathering, Vulnerability Scanning and Crawling. A must have tool for all penetration testers. |
| [Infoga](https://github.com/m4ll0k/Infoga)               | **Python** | `Linux/Windows/macOS` | Email Information Gathering.                                                                                                  |
| [KnockMail](https://github.com/4w4k3/KnockMail)          | **Python** | `Linux/Windows/macOS` | Check if email address exists.                                                                                                |
| [a2sv](https://github.com/hahwul/a2sv)                   | **Python** | `Linux/Windows/macOS` | Auto Scanning to SSL Vulnerability.                                                                                           |
| [Wfuzz](https://github.com/xmendez/wfuzz)                | **Python** | `Linux/Windows/macOS` | Web application fuzzer.                                                                                                       |
| [Nmap](https://github.com/nmap/nmap)                     | **C/C++**  | `Linux/Windows/macOS` | A very common tool. Network host, vuln and port detector.                                                                     |
| [PhoneInfoga](https://github.com/sundowndev/PhoneInfoga) | **Go**     | `Linux/macOS`         | An OSINT framework for phone numbers.                                                                                         |

#### :lock: Serangan Kata Sandi

Mengcrack kata sandi dan membuat daftar kata.

| Alat                                                             | Bahasa     | Dukungan              | Deskripsi                                                                |
| ---------------------------------------------------------------- | ---------- | --------------------- | ------------------------------------------------------------------------ |
| [John the Ripper](https://github.com/magnumripper/JohnTheRipper) | **C**      | `Linux/Windows/macOS` | John the Ripper adalah alat pengcrack kata sandi yang cepat.             |
| [hashcat](https://github.com/hashcat/hashcat)                    | **C**      | `Linux/Windows/macOS` | Utilitas pemulihan kata sandi tercepat dan paling canggih di dunia.      |
| [Hydra](https://github.com/vanhauser-thc/thc-hydra)              | **C**      | `Linux/Windows/macOS` | Alat pengcrack login yang diparalelkan yang mendukung berbagai protokol. |
| [ophcrack](https://gitlab.com/objectifsecurite/ophcrack)         | **C++**    | `Linux/Windows/macOS` | Pengcrack kata sandi Windows berbasis tabel pelangi.                     |
| [Ncrack](https://github.com/nmap/ncrack)                         | **C**      | `Linux/Windows/macOS` | Alat pengcrack autentikasi jaringan berkecepatan tinggi.                 |
| [WGen](https://github.com/agusmakmun/Python-Wordlist-Generator)  | **Python** | `Linux/Windows/macOS` | Membuat daftar kata yang mengagumkan dengan Python.                      |
| [SSH Auditor](https://github.com/ncsa/ssh-auditor)               | **Go**     | `Linux/macOS`         | Cara terbaik untuk memindai kata sandi SSH yang lemah di jaringan Anda.  |

###### :memo: Daftar Kata

| Alat                                                                | Deskripsi                                                                                                         |
| ------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| [Probable Wordlist](https://github.com/berzerk0/Probable-Wordlists) | Daftar kata yang diurutkan berdasarkan probabilitas yang awalnya dibuat untuk pembuatan dan pengujian kata sandi. |

#### :globe_with_meridians: Pengujian Nirkabel

Digunakan untuk deteksi intrusi dan serangan WiFi.

| Alat                                                    | Bahasa     | Dukungan                      | Deskripsi                                                                                                     |
| ------------------------------------------------------- | ---------- | ----------------------------- | ------------------------------------------------------------------------------------------------------------- |
| [Aircrack](https://github.com/aircrack-ng/aircrack-ng)  | **C**      | `Linux/Windows/macOS`         | Suite alat audit keamanan WiFi.                                                                               |
| [bettercap](https://github.com/bettercap/bettercap)     | **Go**     | `Linux/Windows/macOS/Android` | bettercap adalah Swiss army knife untuk serangan dan pemantauan jaringan.                                     |
| [WiFi Pumpkin](https://github.com/P0cL4bs/WiFi-Pumpkin) | **Python** | `Linux/Windows/macOS/Android` | Framework untuk Serangan Titik Akses Wi-Fi Rogue.                                                             |
| [Airgeddon](https://github.com/v1s1t0r1sh3r3/airgeddon) | **Shell**  | `Linux/Windows/macOS`         | Ini adalah skrip bash multi-guna untuk sistem Linux untuk mengaudit jaringan nirkabel.                        |
| [Airbash](https://github.com/tehw0lf/airbash)           | **C**      | `Linux/Windows/macOS`         | Skrip tangkapan genggaman WPA PSK yang sepenuhnya otomatis dan sesuai dengan POSIX untuk pengujian penetrasi. |

#### :wrench: Alat Eksploitasi

Mengakses sistem dan data dengan eksploitasi berbasis layanan.

| Alat                                                    | Bahasa     | Dukungan              | Deskripsi                                                                      |
| ------------------------------------------------------- | ---------- | --------------------- | ------------------------------------------------------------------------------ |
| [SQLmap](https://github.com/sqlmapproject/sqlmap)       | **Python** | `Linux/Windows/macOS` | Alat otomatis untuk injeksi SQL dan pengambilalihan database.                  |
| [XSStrike](https://github.com/UltimateHackers/XSStrike) | **Python** | `Linux/Windows/macOS` | Suite deteksi dan eksploitasi XSS canggih.                                     |
| [Commix](https://github.com/commixproject/commix)       | **Python** | `Linux/Windows/macOS` | Alat injeksi perintah OS all-in-one yang otomatis.￼                            |
| [Nuclei](https://github.com/projectdiscovery/nuclei)    | **Go**     | `Linux/Windows/macOS` | Pemindai kerentanan cepat dan dapat disesuaikan berdasarkan DSL berbasis YAML. |

#### :busts_in_silhouette: Sniffing & Spoofing

Mendengarkan lalu lintas jaringan atau memalsukan entitas jaringan.

| Alat                                                    | Bahasa     | Dukungan                      | Deskripsi                                         |
| ------------------------------------------------------- | ---------- | ----------------------------- | ------------------------------------------------- |
| [Wireshark](https://www.wireshark.org)                  | **C/C++**  | `Linux/Windows/macOS`         | Wireshark adalah analisis protokol jaringan.      |
| [WiFi Pumpkin](https://github.com/P0cL4bs/WiFi-Pumpkin) | **Python** | `Linux/Windows/macOS/Android` | Framework untuk Serangan Titik Akses Wi-Fi Rogue. |
| [Zarp](https://github.com/hatRiot/zarp)                 | **Python** | `Linux/Windows/macOS`         | Kerangka kerja serangan jaringan gratis.          |

#### :rocket: Web Hacking

Memanfaatkan CMS populer yang dihosting secara online.

| Alat                                               | Bahasa     | Dukungan              | Deskripsi                                                                                                  |
| -------------------------------------------------- | ---------- | --------------------- | ---------------------------------------------------------------------------------------------------------- |
| [WPScan](https://github.com/wpscanteam/wpscan)     | **Ruby**   | `Linux/Windows/macOS` | WPScan adalah pemindai kerentanan WordPress berbasis kotak hitam.                                          |
| [Droopescan](https://github.com/droope/droopescan) | **Python** | `Linux/Windows/macOS` | Pemindai berbasis plugin untuk mengidentifikasi masalah pada beberapa CMS, terutama Drupal & Silverstripe. |
| [Joomscan](https://github.com/rezasp/joomscan)     | **Perl**   | `Linux/Windows/macOS` | Pemindai Kerentanan Joomla.                                                                                |
| [Drupwn](https://github.com/immunIT/drupwn)        | **Python** | `Linux/Windows/macOS` | Pemindai Keamanan Drupal untuk melakukan enumerasi pada aplikasi web berbasis Drupal.                      |
| [CMSeek](https://github.com/Tuhinshubhra/CMSeek)   | **Python** | `Linux/Windows/macOS` | Paket Alat Deteksi dan Eksploitasi CMS - Pindai WordPress, Joomla, Drupal, dan 130 CMS lainnya.            |

#### :tada: Eksploitasi Pasca

Eksploitasi setelah Anda mendapatkan akses.

| Alat                                                | Bahasa | Dukungan              | Deskripsi                                                                                                                   |
| --------------------------------------------------- | ------ | --------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| [TheFatRat](https://github.com/Screetsec/TheFatRat) | **C**  | `Linux/Windows/macOS` | Alat mudah untuk menghasilkan pintu belakang dan alat mudah untuk serangan pasca eksploitasi seperti serangan browser, dll. |

#### :package: Framework

Framework adalah kumpulan alat uji penetrasi dengan navigasi shell khusus dan dokumentasi.

| Alat                                                                                          | Bahasa         | Dukungan                      | Deskripsi                                                                                                                                                                                                      |
| --------------------------------------------------------------------------------------------- | -------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Operative Framework](https://github.com/graniet/operative-framework)                         | **Python**     | `Linux/Windows/macOS`         | Kerangka kerja berdasarkan tindakan sidik jari, alat ini digunakan untuk mendapatkan informasi tentang sebuah situs web atau target perusahaan dengan beberapa modul.                                          |
| [Metasploit](https://github.com/rapid7/metasploit-framework)                                  | **Ruby**       | `Linux/Windows/macOS`         | Kerangka kerja pengujian penetrasi untuk peretas etis.                                                                                                                                                         |
| [cSploit](https://github.com/cSploit/android)                                                 | **Java**       | `Android`                     | Toolkit profesional keamanan TI yang paling lengkap dan canggih di Android.                                                                                                                                    |
| [radare2](https://github.com/radare/radare2)                                                  | **C**          | `Linux/Windows/macOS/Android` | Kerangka kerja teknik balik seperti Unix dan alat baris perintah.                                                                                                                                              |
| [Wifiphisher](https://github.com/wifiphisher/wifiphisher)                                     | **Python**     | `Linux`                       | Kerangka Kerja Titik Akses Nakal.                                                                                                                                                                              |
| [Beef](https://github.com/beefproject/beef)                                                   | **Javascript** | `Linux/Windows/macOS`         | Kerangka Kerja Eksploitasi Browser. Ini adalah alat pengujian penetrasi yang berfokus pada peramban web.                                                                                                       |
| [Mobile Security Framework (MobSF)](https://github.com/MobSF/Mobile-Security-Framework-MobSF) | **Python**     | `Linux/Windows/macOS`         | Mobile Security Framework (MobSF) adalah kerangka kerja pengetesan aplikasi seluler (Android/iOS/Windows) otomatis, analisis malware, dan penilaian keamanan yang mampu melakukan analisis statis dan dinamis. |
| [Burp Suite](https://portswigger.net/burp)                                                    | **Java**       | `Linux/Windows/macOS`         | Burp Suite adalah rangkaian alat keamanan siber terkemuka, dibawa oleh PortSwigger. **Alat ini tidak gratis dan sumber terbuka**                                                                               |

([Daftar Isi](#daftar-isi))

# Sumber Daya Tambahan

-   [Devbreak di Twitter](https://twitter.com/DevbreakFR)
-   [Hidup Seorang Peneliti Keamanan](https://www.alienvault.com/blogs/security-essentials/the-life-of-a-security-researcher)
-   [Temukan tempat hacking keren di negara Anda](https://github.com/diasdavid/awesome-hacking-spots)
-   [Daftar Sumber Daya Menakjubkan untuk Hacking](https://github.com/Hack-with-Github/Awesome-Hacking/blob/master/README.md)
-   [Crack Station](http://crackstation.net/)
-   [Exploit Database](http://www.exploit-db.com/)
-   [Hackavision](http://www.hackavision.com/)
-   [Hackmethod](https://www.hackmethod.com/)
-   [Packet Storm Security](http://packetstormsecurity.org/)
-   [SecLists](http://seclists.org/)
-   [SecTools](http://sectools.org/)
-   [Smash the Stack](http://smashthestack.org/)
-   [Jangan gunakan layanan VPN](https://gist.github.com/joepie91/5a9909939e6ce7d09e29)
-   [Cara Menghindari Menjadi Script Kiddie](https://www.wikihow.com/Avoid-Becoming-a-Script-Kiddie)
-   [10 Ancaman Keamanan Aplikasi Teratas 2017](https://www.owasp.org/index.php/Top_10-2017_Top_10)
-   [Memulai di bidang keamanan cyber?](https://blog.0day.rocks/starting-in-cybersecurity-5b02d827fb54)

## Buku / Manual

**Peringatan:** Saya belum membaca semuanya, jadi jangan menganggap saya merekomendasikan karena saya menyukainya. Mereka hanya tampaknya menyediakan sumber daya yang berguna.

-   [Penetration Testing: A Hands-On Introduction to Hacking](https://www.amazon.com/Penetration-Testing-Hands-Introduction-Hacking/dp/1593275641) (2014)
-   [Kali Linux Revealed](https://www.amazon.com/Kali-Linux-Revealed-Penetration-Distribution/dp/0997615605) - [PDF](https://kali.training/downloads/Kali-Linux-Revealed-1st-edition.pdf) (2017)
-   [Blue Team Field Manual (BTFM)](https://www.amazon.com/Blue-Team-Field-Manual-BTFM/dp/154101636X) (2017)
-   [Cybersecurity - Attack and Defense Strategies](https://www.amazon.com/Cybersecurity-Defense-Strategies-Infrastructure-security/dp/1788475291) (2018)
-   [NMAP Network Scanning: Official Discovery](https://www.amazon.com/Nmap-Network-Scanning-Official-Discovery/dp/0979958717) (2009)
-   [Social Engineering: The Art of Human Hacking](https://www.amazon.com/Social-Engineering-Art-Human-Hacking/dp/0470639539) (2010)
-   [Incognito Toolkit: Tools, Apps, and Creative Methods for Remaining Anonymous](https://www.amazon.com/Incognito-Toolkit-Communicating-Publishing-Researching/dp/0985049146) (2013)

## Diskusi



-   [Reddit/HowToHack](https://www.reddit.com/r/HowToHack/) Pelajari dan tanyakan tentang hacking, keamanan, dan pengujian penetrasi.
-   [Reddit/hacking](https://www.reddit.com/r/hacking) Diskusikan tentang hacking dan keamanan web.
-   [ax0nes](https://ax0nes.com/) Forum hacking, keamanan, dan pengembangan perangkat lunak.
-   [0Day.rocks di Discord](https://discord.gg/WmYzJfD) Server Discord tentang blog 0day.rocks untuk diskusi InfoSec/Cyber teknis dan umum serta berita terbaru.
-   [Reddit/AskNetsec](https://www.reddit.com/r/AskNetsec/) Diskusikan tentang keamanan jaringan, tanyakan kepada para profesional tentang saran pekerjaan dan hal-hal lainnya.

## Peringatan Keamanan

-   [CVE](http://cve.mitre.org/)
-   [CWE](http://cwe.mitre.org/)
-   [NVD](http://web.nvd.nist.gov/)

## Tantangan

-   [Vulnhub](https://www.vulnhub.com/) - Memiliki banyak mesin virtual untuk dimainkan. Beberapa cocok untuk pemula, beberapa tidak.
-   [Itsecgames](http://www.itsecgames.com/) - bWAPP atau aplikasi web yang bermasalah adalah aplikasi web yang disengaja tidak aman.
-   [Dvwa](http://www.dvwa.co.uk/) - Damn Vulnerable Web Application adalah aplikasi web yang disengaja tidak aman lainnya untuk berlatih keterampilan Anda.
-   [Hackthissite](https://www.hackthissite.org/) - Situs yang menyediakan tantangan, CTF, dan lainnya untuk meningkatkan keterampilan hacking Anda.
-   [Defend the Web](https://defendtheweb.net/) - Defend the Web adalah platform keamanan interaktif tempat Anda dapat belajar dan menguji keterampilan Anda.
-   [Root-me](https://www.root-me.org/) - Situs web lain yang menyelenggarakan tantangan untuk menguji keterampilan hacking Anda.
-   [HackTheBox](https://www.hackthebox.eu/) - Platform online untuk menguji dan meningkatkan keterampilan Anda dalam pengujian penetrasi dan keamanan siber.
-   [Overthewire](http://overthewire.org/wargames/) - Pelajari dan latih konsep keamanan dalam bentuk permainan yang seru.
-   [Ctftime](https://ctftime.org/) - Situs web resmi untuk segala sesuatu yang berhubungan dengan CTF.
-   [TryHackMe](https://tryhackme.com/) - TryHackMe adalah platform online gratis untuk belajar keamanan siber, dengan latihan dan laboratorium langsung.
-   [PicoCTF](https://picoctf.org/) - Menyediakan tantangan CTF yang menyenangkan dengan tingkat kesulitan yang bervariasi untuk dipraktikkan.

([Daftar Isi](#daftar-isi))

# Lisensi

Repository ini dilisensikan di bawah lisensi MIT.

([Daftar Isi](#daftar-isi))
