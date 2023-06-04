<p align="center">
    <img src="https://i.imgur.com/VeEYEkT.png" alt="Hacker roadmap" /><br>
</p>

Repository ini adalah gambaran tentang apa yang perlu Anda pelajari dalam penetration testing dan kumpulan alat-alat hacking, sumber daya, dan referensi untuk berlatih ethical hacking. Sebagian besar alat-alat ini kompatibel dengan UNIX, gratis, dan open source.

## Status

**Proyek ini telah diarsipkan**. Konten mungkin sudah tidak terbaru. Saya dan beberapa teman sedang mengerjakan proyek baru yang akan menggantikan keseluruhan repositori ini. Tujuannya tetap sama: menyediakan sumber daya tentang keamanan informasi profesional bagi pemula, dengan fokus lengkap pada pelatihan, sertifikasi, dan persyaratan pekerjaan. Kami tidak berharap proyek baru ini akan selesai sebelum Q1 2023.

----

## Sebelum Anda memulai

- Jika Anda baru dalam keamanan informasi, lupakan segala hal yang Anda ketahui tentang hacking.
- Jangan mulai menggunakan alat-alat tanpa membaca tentang pen testing dan bagaimana cara kerjanya (lihat bagian [Sumber daya tambahan](#additional-resources)).
- Jangan mengunduh atau menggunakan alat-alat jika Anda belum memeriksa kode-kodenya.
- Jangan gunakan alat-alat ini untuk melakukan hal-hal bodoh seperti menyelidiki/hack tanpa persetujuan pada teman Anda, atau yang lebih buruk, rekruter Anda.
- Baca buku, manual, artikel, jadilah penasaran, dan jangan hanya menjadi [script kiddie](https://www.wikihow.com/Avoid-Becoming-a-Script-Kiddie) saja.
- Saya berharap Anda tidak menggunakan alat-alat ini untuk tujuan illegal, tetapi jika Anda melakukannya, saya berharap Anda tahu apa yang Anda lakukan.
- Berlatih menggunakan [challenges](#challenges), bukan target yang nyata!

# Daftar Isi

- [Pengantar](#introduction)
  - [Apa itu penetration testing?](#what-is-penetration-testing)
  - [Ingin menjadi penetration tester?](#want-to-become-a-penetration-tester)
- [Beberapa kosakata](#some-vocabulary)
- [Perbedaan antara hacking dan ethical hacking](#difference-between-hacking-and-ethical-hacking)
- [Bahasa](#languages)
- [Sistem Manajemen Konten](#content-management-systems)
- [Langkah-langkah dasar pen testing](#basic-steps-of-pen-testing)
- [Alat-alat berdasarkan kategori](#tools-by-category)
  - [:male_detective: Information Gathering](#male_detective-information-gathering)
  - [:lock: Password Attacks](#lock-password-attacks)
    - [:memo: Wordlists](#memo-wordlists)
  - [:globe_with_meridians: Wireless Testing](#globe_with_meridians-wireless-testing)
  - [:wrench: Exploitation Tools](#wrench-exploitation-tools)
  - [:busts_in_silhouette: Sniffing & Spoofing](#busts_in_silhouette-sniffing--spoofing)
  - [:rocket: Web Hacking](#rocket

-web-hacking)
  - [:tada: Post Exploitation](#tada-post-exploitation)
  - [:package: Frameworks](#package-frameworks)
- [Sumber daya tambahan](#additional-resources)
  - [Buku / Manual](#books--manuals)
  - [Diskusi](#discussions)
  - [Informasi Keamanan](#security-advisories)
  - [Challenges](#challenges)
- [Lisensi](#license)

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

**Tim biru**: Tim biru adalah kelompok individu yang melakukan analisis terhadap sistem informasi untuk memastikan keamanannya, mengidentifikasi kelemahan keamanan, memverifikasi efektivitas setiap langkah keamanan, dan memastikan semua langkah keamanan akan tetap efektif setelah implementasi. Sebagai hasilnya, tim biru dikembangkan untuk merancang langkah-langkah pertahanan terhadap aktivitas tim merah. Dalam latihan infosec, anggota Tim Biru berperan sebagai pembela. [Wikipedia](https://en.wikipedia.org/wiki/Blue_team_(computer_security))

**Penetration tester**: Seorang ethical hacker yang menjalankan keamanan, menguji aplikasi dan sistem untuk mencegah intrusi atau menemukan kerentanan.

**Peneliti keamanan**: Seseorang yang menjalankan pen testing dan menjelajahi web untuk menemukan situs phishing/palsu, server terinfeksi, bug atau kerentanan. Mereka dapat bekerja untuk perusahaan sebagai konsultan keamanan dan kemungkinan besar sebagai anggota Tim Biru.

**Reverse engineering**: Reverse engineering, juga disebut back engineering, adalah proses di mana suatu objek buatan manusia didekonstruksi untuk mengungkapkan desain, arsitektur, atau untuk mengekstrak pengetahuan dari objek tersebut. Mirip dengan penelitian ilmiah, satu-satunya perbedaan adalah bahwa penelitian ilmiah berhubungan dengan fenomena alam. [Wikipedia](https://en.wikipedia.org/wiki/

Reverse_engineering)

**Social engineering**: Dalam konteks keamanan informasi, istilah ini mengacu pada manipulasi psikologis terhadap orang-orang untuk melakukan tindakan atau mengungkapkan informasi rahasia. Jenis penipuan kepercayaan untuk tujuan pengumpulan informasi, penipuan, atau akses sistem, berbeda dari "kon" tradisional karena sering menjadi salah satu langkah dalam skema penipuan yang lebih kompleks. Istilah "social engineering" sebagai tindakan manipulasi psikologis terhadap manusia juga terkait dengan ilmu sosial, tetapi penggunaannya telah menjadi umum di kalangan profesional keamanan komputer dan informasi. [Wikipedia](https://en.wikipedia.org/wiki/Social_engineering_(security))

**Analisis ancaman**: Seorang penelusur ancaman, juga disebut sebagai analis ancaman keamanan siber, adalah profesional keamanan atau penyedia layanan manajemen (MSP) yang secara proaktif menggunakan teknik manual atau berbantuan mesin untuk mendeteksi insiden keamanan yang mungkin terlewat oleh sistem otomatis. Threat hunter bertujuan untuk mengungkapkan insiden yang sebaliknya tidak akan diketahui oleh perusahaan, memberikan kepala petugas keamanan informasi (CISO) dan kepala petugas informasi (CIO) dengan lapisan pertahanan tambahan terhadap ancaman yang bertahan lama (APTs) yang canggih. [SearchCIO](https://searchcio.techtarget.com/definition/threat-hunter-cybersecurity-threat-analyst)

([Daftar Isi](#table-of-contents))

# Difference between hacking and ethical hacking

A black hat is practicing penetration testing, but unlike a white hat, this is not ethical hacking. Ethical hacking is about finding vulnerabilities and improve the security of a system. An ethical hacker is the ultimate security professional. Ethical hackers know how to find and exploit vulnerabilities and weaknesses in various systems, just like a malicious hacker (a black hat hacker). In fact, they both use the same skills; however, an ethical hacker uses those skills in a legitimate, lawful manner to try to find vulnerabilities and fix them before the bad guys can get there and try to break in. An ethical hacker is basically a white hat hacker.

([Table of Contents](#table-of-contents))

# Languages

Learning programming is the very first way to start learning about security. There's a lot of languages, most people start with Python, it's the easiest and the most popular one. PHP and Go are the less popular to write security-related stuff, but any of these can still be used in such context. Bash and Powershell are mostly about scripting and writing simple CLI applications.

Since not all languages work the same way, you need to look at how they work and what you want to learn. For example, C++ and Java compile, PHP and Python do not, they are interpreted languages. This definitely changes what you should use them for. Each language also has its own design patterns.

### Scripting

- Bash
- Powershell

### Software & mobile apps

- Java
- Swift
- C / C++ / C#

### General purpose

- Python
- Ruby
- Perl
- PHP
- Go

([Table of Contents](#table-of-contents))

# Content Management Systems

- Wordpress
- Joomla
- Drupal
- SPIP

These are the most used Content Management Systems (CMS). See a complete list [here](https://en.wikipedia.org/wiki/List_of_content_management_systems).

([Table of Contents](#table-of-contents))

# Basic steps of pen testing

<p align="center">
    <img src="https://www.tutorialspoint.com/penetration_testing/images/penetration_testing_method.jpg">
</p>

*Source: [tutorialspoint](https://www.tutorialspoint.com/penetration_testing/index.htm)*

[Read more about pen testing methodology](https://www.tutorialspoint.com/penetration_testing/penetration_testing_method.htm)

([Table of Contents](#table-of-contents))

# Tools by category

A more complete list of tools can be found on [Kali Linux official website](https://tools.kali.org/tools-listing).

#### :male_detective: Information Gathering

Information Gathering tools allows you to collect host metadata about services and users. Check informations about a domain, IP address, phone number or an email address.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [theHarvester](https://github.com/laramies/theHarvester)      | **Python** | `Linux/Windows/macOS` | E-mails, subdomains and names Harvester. |
| [CTFR](https://github.com/UnaPibaGeek/ctfr)      | **Python** | `Linux/Windows/macOS` | Abusing Certificate Transparency logs for getting HTTPS websites subdomains. |
| [Sn1per](https://github.com/1N3/Sn1per)      | **bash** | `Linux/macOS` | Automated Pentest Recon Scanner. |
| [RED Hawk](https://github.com/Tuhinshubhra/RED_HAWK)      | **PHP** | `Linux/Windows/macOS` | All in one tool for Information Gathering, Vulnerability Scanning and Crawling. A must have tool for all penetration testers. |
| [Infoga](https://github.com/m4ll0k/Infoga)      | **Python** | `Linux/Windows/macOS` | Email Information Gathering. |
| [KnockMail](https://github.com/4w4k3/KnockMail)      | **Python** | `Linux/Windows/macOS` | Check if email address exists. |
| [a2sv](https://github.com/hahwul/a2sv)      | **Python** | `Linux/Windows/macOS` | Auto Scanning to SSL Vulnerability. |
| [Wfuzz](https://github.com/xmendez/wfuzz)      | **Python** | `Linux/Windows/macOS` | Web application fuzzer. |
| [Nmap](https://github.com/nmap/nmap)      | **C/C++** | `Linux/Windows/macOS` | A very common tool. Network host, vuln and port detector. |
| [PhoneInfoga](https://github.com/sundowndev/PhoneInfoga)      | **Go** | `Linux/macOS` | An OSINT framework for phone numbers. |

#### :lock: Password Attacks

Crack passwords and create wordlists.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [John the Ripper](https://github.com/magnumripper/JohnTheRipper)      | **C** | `Linux/Windows/macOS` | John the Ripper is a fast password cracker. |
| [hashcat](https://github.com/hashcat/hashcat)      | **C** | `Linux/Windows/macOS` | World's fastest and most advanced password recovery utility. |
| [Hydra](https://github.com/vanhauser-thc/thc-hydra)      | **C** | `Linux/Windows/macOS` | Parallelized login cracker which supports numerous protocols to attack. |
| [ophcrack](https://gitlab.com/objectifsecurite/ophcrack)      | **C++** | `Linux/Windows/macOS` | Windows password cracker based on rainbow tables. |
| [Ncrack](https://github.com/nmap/ncrack)      | **C** | `Linux/Windows/macOS` | High-speed network authentication cracking tool. |
| [WGen](https://github.com/agusmakmun/Python-Wordlist-Generator)      | **Python** | `Linux/Windows/macOS` | Create awesome wordlists with Python. |
| [SSH Auditor](https://github.com/ncsa/ssh-auditor)      | **Go** | `Linux/macOS` | The best way to scan for weak ssh passwords on your network. |

###### :memo: Wordlists

| Tool        | Description    |
| ----------- |----------------|
| [Probable Wordlist](https://github.com/berzerk0/Probable-Wordlists)      | Wordlists sorted by probability originally created for password generation and testing. |

#### :globe_with_meridians: Wireless Testing

Used for intrusion detection and wifi attacks.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [Aircrack](https://github.com/aircrack-ng/aircrack-ng)      | **C** | `Linux/Windows/macOS` | WiFi security auditing tools suite. |
| [bettercap](https://github.com/bettercap/bettercap)      | **Go** | `Linux/Windows/macOS/Android` | bettercap is the Swiss army knife for network attacks and monitoring. |
| [WiFi Pumpkin](https://github.com/P0cL4bs/WiFi-Pumpkin)      | **Python** | `Linux/Windows/macOS/Android` | Framework for Rogue Wi-Fi Access Point Attack. |
| [Airgeddon](https://github.com/v1s1t0r1sh3r3/airgeddon)      | **Shell** | `Linux/Windows/macOS` | This is a multi-use bash script for Linux systems to audit wireless networks. |
| [Airbash](https://github.com/tehw0lf/airbash)      | **C** | `Linux/Windows/macOS` | A POSIX-compliant, fully automated WPA PSK handshake capture script aimed at penetration testing. |

#### :wrench: Exploitation Tools

Acesss systems and data with service-oriented exploits.

| Tool                                                    | Language   | Support               | Description                                                  |
| ------------------------------------------------------- | ---------- | --------------------- | ------------------------------------------------------------ |
| [SQLmap](https://github.com/sqlmapproject/sqlmap)       | **Python** | `Linux/Windows/macOS` | Automatic SQL injection and database takeover tool.          |
| [XSStrike](https://github.com/UltimateHackers/XSStrike) | **Python** | `Linux/Windows/macOS` | Advanced XSS detection and exploitation suite.               |
| [Commix](https://github.com/commixproject/commix)       | **Python** | `Linux/Windows/macOS` | Automated All-in-One OS command injection and exploitation tool.￼ |
| [Nuclei](https://github.com/projectdiscovery/nuclei)    | **Go**     | `Linux/Windows/macOS` | Fast and customisable vulnerability scanner based on simple YAML based DSL. |

#### :busts_in_silhouette: Sniffing & Spoofing

Listen to network traffic or fake a network entity.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [Wireshark](https://www.wireshark.org)      | **C/C++** | `Linux/Windows/macOS` | Wireshark is a network protocol analyzer. |
| [WiFi Pumpkin](https://github.com/P0cL4bs/WiFi-Pumpkin)      | **Python** | `Linux/Windows/macOS/Android` | Framework for Rogue Wi-Fi Access Point Attack. |
| [Zarp](https://github.com/hatRiot/zarp)      | **Python** | `Linux/Windows/macOS` | A free network attack framework. |

#### :rocket: Web Hacking

Exploit popular CMSs that are hosted online.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [WPScan](https://github.com/wpscanteam/wpscan)      | **Ruby** | `Linux/Windows/macOS` | WPScan is a black box WordPress vulnerability scanner. |
| [Droopescan](https://github.com/droope/droopescan)      | **Python** | `Linux/Windows/macOS` | A plugin-based scanner to identify issues with several CMSs, mainly Drupal & Silverstripe. |
| [Joomscan](https://github.com/rezasp/joomscan)      | **Perl** | `Linux/Windows/macOS` | Joomla Vulnerability Scanner. |
| [Drupwn](https://github.com/immunIT/drupwn)      | **Python** | `Linux/Windows/macOS` | Drupal Security Scanner to perform enumerations on Drupal-based web applications. |
| [CMSeek](https://github.com/Tuhinshubhra/CMSeek)      | **Python** | `Linux/Windows/macOS` | CMS Detection and Exploitation suite - Scan WordPress, Joomla, Drupal and 130 other CMSs. |

#### :tada: Post Exploitation

Exploits for after you have already gained access.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [TheFatRat](https://github.com/Screetsec/TheFatRat)      | **C** | `Linux/Windows/macOS` | Easy tool to generate backdoor and easy tool to post exploitation attack like browser attack, dll. |

#### :package: Frameworks

Frameworks are packs of pen testing tools with custom shell navigation and documentation.

| Tool        | Language           | Support  | Description    |
| ----------- |-------------------------|----------|----------------|
| [Operative Framework](https://github.com/graniet/operative-framework)      | **Python** | `Linux/Windows/macOS` | Framework based on fingerprint action, this tool is used to get information on a website or a enterprise target with multiple modules. |
| [Metasploit](https://github.com/rapid7/metasploit-framework)      | **Ruby** | `Linux/Windows/macOS` | A penetration testing framework for ethical hackers. |
| [cSploit](https://github.com/cSploit/android)      | **Java** | `Android` | The most complete and advanced IT security professional toolkit on Android. |
| [radare2](https://github.com/radare/radare2)      | **C** | `Linux/Windows/macOS/Android` | Unix-like reverse engineering framework and commandline tools. |
| [Wifiphisher](https://github.com/wifiphisher/wifiphisher)      | **Python** | `Linux` | The Rogue Access Point Framework. |
| [Beef](https://github.com/beefproject/beef)      | **Javascript** | `Linux/Windows/macOS` | The Browser Exploitation Framework. It is a penetration testing tool that focuses on the web browser. |
| [Mobile Security Framework (MobSF)](https://github.com/MobSF/Mobile-Security-Framework-MobSF)      | **Python** | `Linux/Windows/macOS` | Mobile Security Framework (MobSF) is an automated, all-in-one mobile application (Android/iOS/Windows) pen-testing, malware analysis and security assessment framework capable of performing static and dynamic analysis. |
| [Burp Suite](https://portswigger.net/burp)      | **Java** | `Linux/Windows/macOS` | Burp Suite is a leading range of cybersecurity tools, brought to you by PortSwigger. **This tool is not free and open source** |

([Table of Contents](#table-of-contents))

# Additional resources

- [Devbreak on Twitter](https://twitter.com/DevbreakFR)
- [The Life of a Security Researcher](https://www.alienvault.com/blogs/security-essentials/the-life-of-a-security-researcher)
- [Find an awesome hacking spots in your country](https://github.com/diasdavid/awesome-hacking-spots)
- [Awesome-Hacking Lists](https://github.com/Hack-with-Github/Awesome-Hacking/blob/master/README.md)
- [Crack Station](http://crackstation.net/)
- [Exploit Database](http://www.exploit-db.com/)
- [Hackavision](http://www.hackavision.com/)
- [Hackmethod](https://www.hackmethod.com/)
- [Packet Storm Security](http://packetstormsecurity.org/)
- [SecLists](http://seclists.org/)
- [SecTools](http://sectools.org/)
- [Smash the Stack](http://smashthestack.org/)
- [Don't use VPN services](https://gist.github.com/joepie91/5a9909939e6ce7d09e29)
- [How to Avoid Becoming a Script Kiddie](https://www.wikihow.com/Avoid-Becoming-a-Script-Kiddie)
- [2017 Top 10 Application Security Risks](https://www.owasp.org/index.php/Top_10-2017_Top_10)
- [Starting in cybersecurity ?](https://blog.0day.rocks/starting-in-cybersecurity-5b02d827fb54)

## Books / Manuals

**Warning :** I haven't read them all so do not consider I am recommending as I liked them. They just seem to provide useful resources.

- [Penetration Testing: A Hands-On Introduction to Hacking](https://www.amazon.com/Penetration-Testing-Hands-Introduction-Hacking/dp/1593275641) (2014)
- [Kali Linux Revealed](https://www.amazon.com/Kali-Linux-Revealed-Penetration-Distribution/dp/0997615605) - [PDF](https://kali.training/downloads/Kali-Linux-Revealed-1st-edition.pdf) (2017)
- [Blue Team Field Manual (BTFM)](https://www.amazon.com/Blue-Team-Field-Manual-BTFM/dp/154101636X) (2017)
- [Cybersecurity - Attack and Defense Strategies](https://www.amazon.com/Cybersecurity-Defense-Strategies-Infrastructure-security/dp/1788475291) (2018)
- [NMAP Network Scanning : Official Discovery](https://www.amazon.com/Nmap-Network-Scanning-Official-Discovery/dp/0979958717) (2009)
- [Social Engineering : The Art of Human Hacking](https://www.amazon.com/Social-Engineering-Art-Human-Hacking/dp/0470639539) (2010)
- [Incognito Toolkit: Tools, Apps, and Creative Methods for Remaining Anonymous](https://www.amazon.com/Incognito-Toolkit-Communicating-Publishing-Researching/dp/0985049146) (2013)

## Discussions
- [Reddit/HowToHack](https://www.reddit.com/r/HowToHack/) Learn and ask about hacking, security and pen testing.
- [Reddit/hacking](https://www.reddit.com/r/hacking) Discuss about hacking and web security.
- [ax0nes](https://ax0nes.com/) Hacking, security, and software development forum.
- [0Day.rocks on discord](https://discord.gg/WmYzJfD) Discord server about the 0day.rocks blog for technical and general InfoSec/Cyber discussions & latest news.
- [Reddit/AskNetsec](https://www.reddit.com/r/AskNetsec/) Discuss about network security, ask professionals for advices about jobs and stuff.

## Security Advisories

- [CVE](http://cve.mitre.org/)
- [CWE](http://cwe.mitre.org/)
- [NVD](http://web.nvd.nist.gov/)

## Challenges

- [Vulnhub](https://www.vulnhub.com/) - Has a lot of VMs to play with. Some are beginner friendly, some aren't.
- [Itsecgames](http://www.itsecgames.com/) - bWAPP or buggy web app is a deliberately insecure web application.
- [Dvwa](http://www.dvwa.co.uk/) - Damn Vulnerable Web Application is another deliberately insecure web application to practice your skills on.
- [Hackthissite](https://www.hackthissite.org/) - A site which provides challenges, CTFs, and more to improve your hacking skills.
- [Defend the Web](https://defendtheweb.net/) - Defend the Web is an interactive security platform where you can learn and challenge your skills.
- [Root-me](https://www.root-me.org/) - Another website which hosts challenges to test your hacking skills.
- [HackTheBox](https://www.hackthebox.eu/) - An online platform to test and advance your skills in penetration testing and cyber security.
- [Overthewire](http://overthewire.org/wargames/) - Learn and practice security concepts in the form of fun-filled games.
- [Ctftime](https://ctftime.org/) - The de facto website for everything CTF related. 
- [TryHackMe](https://tryhackme.com/) - TryHackMe is a free online platform for learning cyber security, using hands-on exercises and labs.
- [PicoCTF](https://picoctf.org/) - Provides you with fun CTF challenges of varying levels of difficulty to practice on.

([Table of Contents](#table-of-contents))

# License

This repository is under MIT license.

([Table of Contents](#table-of-contents))
