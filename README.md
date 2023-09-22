
# Jarkom Modul 1

|      Nama Anggota       |     NRP     |
| ---                     | ---         |
| Oktavia Anggraeni P.    | 5027211001  |
| Brigita Naraduhita P.P. | 5027211055  |

### 1. Pada soal tersebut diketahui bahwa user melakukan aktivitas salah satunya mengunggah suatu file.

**Cara mengerjakan:**
   - Download dan buka file yang telah disediakan bertipe wireshark capture file
   - Klikkan find dan ketikkan `ftp || ftp-data` untuk mengambil paket-paket yang terkait dengan protokol FTP (File Transfer Protocol) atau paket data yang dikirim melalui FTP. 
   - User melakukan aktivitas mengunggah suatu file. Maka cari perintah bertuliskan `STOR` yang berfungsi untuk mengupload file ke FTP server.
<p align="center">
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/ad6b553f-9713-4e17-ae06-810597c068f4" height="150"/>
</p>

   - Lalu analisis dan cari sequence number (raw), acknowledge number (raw) pada paket tersebut  yang menunjukkan aktivitas.
<p align="center">
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/f9c5fa48-e76b-4731-8dae-d6f92ea70812" height="300"/>
</p>

   - Lalu klik paket satu dibawahnya yang paket ACK, ACK menandakan data sebelumnya telah diterima dan penerima siap menerima data berikutnya.
   - Lalu analisis dan cari sequence number (raw), acknowledge number (raw) pada paket tersebut  yang menunjukkan response dari aktivitas tersebut.
 <p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/e58f3f89-3092-4122-bdc6-8ff0eca8617e" height="300"/>
</p>

   - Lalu buka terminal dan ketikkan `ncat 10.21.78.111 12345` untuk mengakses ke alamat IP 10.21.78.111 pada port 12345 menggunakan netcat.
   - Ketikkan nilai yang didapat sesuai soal
     <p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/4f07f2fa-a6ae-4640-8b8e-23e48b27d042" height="300"/>
</p>

   - Lalu flag akan ditampilkan
 `Flag:  Jarkom2023{y0u_r_g00d_4t_4dr3ssing_MoDvEwK76448553}`


### 2. Pada soal ini ditanyakan mengenai web server yang digunakan pada portal praktikum Jaringan Komputer

**Cara mengerjakan:**
  - Download dan buka file bertipe wireshark capture file atau .pcapng yang ada pada soal
  - Lakukan follow TCP stream pada salah satu paket dengan metode HTTP, misalnya yang memiliki ststus 200 OK
  - Selain menggunakan TCP stream, paket HTTP juga dapat dicek menggunakan follow HTTP stream
  - Ditemukan server bernama gunicorn
  <p align="center">
     <img src="https://i.ibb.co/KxYkkBL/soal2-wireshark.png">
  </p>
  
  - Buka terminal misalnya menggunakan linux, masuk ke server dengan mengetikkan `nc 10.21.78.111 13579`
  - Isikan jawaban dengan gunicorn, sesuai dengan yang ditemukan pada wireshark sebelumnya 
  <p align="center">
     <img src="https://i.ibb.co/C80LTCt/soal2-ubuntu.png">
  </p>
  - Lalu flag akan ditampilkan
  
  `Flag: Jarkom2023{9unic0rn_1s_081Cy7OWxq3c9jV_c00l}`


### 3. Pada soal ini terdapat keterangan bahwa soal ini terkait analisis jaringan

**Cara mengerjakan:**
- Download dan buka file bertipe wireshark capture file atau .pcap yang ada pada soal
- Buka terminal misalnya menggunakan linux, masuk ke server pada soal dengan mengetikkan `nc 10.21.78.111 13590`
<p align="center">
  <img src="https://i.ibb.co/whCD3ph/soal3-ubuntu.png"> 
</p>

- Setelah masuk ke server tersebut tampak pertanyaan mengenai berapa paket yang tercapture dengan IP soruce maupun destination 239.255.255.250 dengan port 3702
- Lakukan filter IP destination dan temukan IP address yang sesuai, yaitu 239.255.255.250
- Saat melakukan filter dapat ditambahkan filter 3702 dalam kategori string
<p align="center">
   <img src="https://i.ibb.co/NLSxMRq/soal3-wireshark.png">   
</p>

- Setelah dilakukan filter sesuai ketentuan IP 239.255.255.250 dan port 37, maka ditemukan jumlahnya ada 21 dan dapat diinputkan pada terminal
- Selanjutnya ditanyakan mengenai protokol layer transport, tampak dengan jelas pada wireshark bahwa protokol yang digunakan adalah UDP
- Jawaban UDP dapat diinputkan pada terminal
- Lalu flag akan ditampilkan

`Flag: Jarkom2023{4nalyz3_is_9118_DzBhQkSjBiD_gr3at}`


### 4. Pada soal tersebut diminta untuk menemukan nilai checksum yang didapat dari header pada paket nomor 130.

**Cara mengerjakan:**
   - Mendownload dan buka file yang telah disediakan bertipe wireshark capture file
   - Lakukan pencarian untuk paket nomor 130 sesuai dengan perintah
   - Analisis paket tersebut dan mencari nilai checksum. Di dapatkan: `Checksum: 0x18e5`
   <p align="center">
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/c06147ef-bb46-432d-a657-387f91ebb2ea" height="150"/>
</p>

   - Lalu buka terminal dan ketikkan `ncat 10.21.78.111 13591` untuk mengakses ke alamat IP 10.21.78.111 pada port 13591 menggunakan netcat.
   - Ketikkan  nilai checksum `0x18e5` sesuai dengan nilai yang didapatkan.
<p align="center">
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/91c1f55e-f469-4342-9323-a8ec38eaf006" height="150"/>
</p>

   - Lalu flag akan ditampilkan
`Flag:  Jarkom2023{ch3cksum_is_u5eful_0xj7l4}`


### 5. Pada soal terdapat 2 buah file, yaitu file bertipe wireshark capture file atau .pcap dan file .zip

**Cara mengerjakan:**
- Unduh file .pcap dan .zip yang telah disediakan
- Buka file .pcap dengan wireshark
- Lakukan follow TCP stream dan di dalamnya tampak ada password untuk membuka file zip
<p align="center">
   <img src="https://i.ibb.co/HV6XZhX/soal5-pass.png"">
</p>

- Lakukan decode untuk mendapatkan password file zip. Decode bisa menggunakan berbagai web, misalnya base64decode.org, sesuai tipe password yang tertulis
<p align="center">
   <img src="https://i.ibb.co/tcJLn0f/soal5-decode.png">
</p>
- Buka file connect.txt yang terletak dalam file .zip yang telah diunduh. Untuk membukanya, gunakan password yang telah ditemukan
- Dalam file connect.txt tampak cara untuk masuk ke server
- Buka terminal misalnya menggunakan linux, masuk ke server soal dengan mengetikkan `nc 10.21.78.111 11111`
- Dalam soal terdapat soal mengenai paket yang berhasil di capture, port yang digunakan pada service SMTP, serta IP mana yang menggunakan public IP
<p align="center">
   <img src="https://i.ibb.co/jL4mL3v/soal5-wireshark.png">
</p>
- Untuk menjawab satu persatu dapat dilihat kembali pada file .pcap yang telah dibuka tadi, pada bagian protokol SMTP terdapat length 60 yang merupakan jawaban untuk paket yang berhasil dicapture
- Selanjutnya untuk port yang digunakan pada service SMTP, saya mencoba pada bagian bawahnya yang bertanda panah 1470->25, dan ternyata benar 25 jawabannya
- Jawaban terakhir juga terdapat pada gambar wireshark di atas. IP yang menggunakan public IP merupakan IP yang sama yang berhasil mengcapture paket, yaitu 74.53.140.153
- Berikut merupakan tampilan terminal ubuntu saat dijalankan
<p align="center">
   <img src="https://i.ibb.co/q17sN9K/soal5-nc.png">
</p>

- Lalu flag akan ditampilkan
`Flag: Jarkom2023{k0w4lski_7454_vhvSFuCECCw_4nalys1s}`


### 7. Pada soal tersebut diminta untuk menyebutkan jumlah packet yang menuju IP 184.87.193.88

**Cara mengerjakan:**
   - Download dan buka file yang telah disediakan bertipe wireshark capture file
   - Klikkan `find a packet` dan ketikkan `ip.dst == 184.87.193.88` untuk mengambil semua paket yang memiliki alamat tujuan (destination IP address) 184.87.193.88. 
   - Lalu akan menampilkan semua paket yang ditujukan ke alamat IP tersebut.
   - Lalu hitung jumlah paket yang sesuai dan didapatkan total `6` paket
<p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/65b11161-945f-41f5-8531-b04eb01bdce0" height="300"/>
</p>

   - Lalu buka terminal dan ketikkan `nc 10.21.78.111 6565` untuk mengakses ke alamat IP 10.21.78.111 pada port 6565 menggunakan netcat.
   - Ketikkan `6` sesuai dengan jumlah paket yang didapatkan.
<p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/c21b5ab7-a3df-4126-ae11-98f55cfc31ed" height="300"/>
</p>

   - Lalu flag akan didapatkan.
`Flag: Jarkom2023{A6J9sXQi0kKgSMM440_4n0th3r_f1lt3ring}`

### 8. Pada soal tersebut diminta untuk memberikan kueri filter untuk menampilkan protokol paket yang menuju port 80.

**Cara mengerjakan:**
   - Download dan buka file yang telah disediakan bertipe wireshark capture file
   - Kueri filter pada Wireshark yang dapat digunakan untuk menampilkan paket yang menuju port 80 dengan dua kriteria ialah `tcp.dstport == 80 || udp.dstport == 80`
 <p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/8ecfce2e-31df-48d6-aff3-b10c197127cf" height="100"/>
</p>

   - `tcp.dstport == 80` digunakan untuk menampilkan semua paket dengan protokol TCP yang menuju port (destination port) 80
   - `udp.dstport == 80` digunakan untuk menampilkan semua paket dengan protokol UDP yang menuju port (destination port) 80
   - Lalu buka terminal dan ketikkan `ncat 10.21.78.111 7171`  untuk mengakses ke alamat IP 10.21.78.111 pada port  7171 menggunakan netcat.
 <p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/0851d49d-a1db-4cee-b8ac-4bed7be48839"/>
</p>

   - Masukkan kueri tersebut dan flag akan didapatkan.
`Flag: Jarkom2023{qu3ryyyyying_134463_PiDzRvCjEiA_15_fun}`

### 9. Pada soal tersebut diminta kueri filter untuk menampilkan paket yang berasal dari alamat `10.51.40.1` tetapi `tidak`menuju ke alamat `10.39.55.34`
   
**Cara mengerjakan:**
   - Download dan buka file yang telah disediakan bertipe wireshark capture file
   - Kueri filter pada Wireshark yang dapat digunakan untuk menampilkan paket yang menuju port 80 dengan dua kriteria ialah `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`
   - `p.src == 10.51.40.1` berfungsi untuk menampilkan semua paket yang berasal dari alamat tersebut. 
   - `ip.dst != 10.39.55.34` berfungsi untuk menampilkan paket selain yang berasal dari alamat tersebut.
<p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/87917d00-df33-4d8b-9e3c-a5734576c3da"/>
</p>

   - Lalu buka terminal dan ketikkan `ncat 10.21.78.111 13591` untuk mengakses ke alamat IP 10.21.78.111 pada port 7272 menggunakan netcat.
<p align="center">
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/7803639d-30fd-48ce-93e2-0765d6c84365"/>
</p>

   - Lalu akan didapat flag
`Flag: Jarkom2023{y3s_its_QkNhShOkOiP_qu3ry1ng}`

### 10. Pada soal ini ditanyakan mengenai kredensial yang benar ketika user mencoba login menggunakan Telnet

**Cara mengerjakan:**
- Download dan buka file bertipe wireshark capture file atau .pcapng yang ada pada soal
- Lakukan follow TCP stream, di dalamnya terdapat berbagai variasi string dengan format username:password
<p align="center">
  <img src="https://i.ibb.co/BPhrmNX/soal10-variasipass.png">
</p>

- Buka terminal misalnya menggunakan linux, masuk ke server pada soal dengan mengetikkan `nc 10.21.78.111 7373`
- Karena terdapat banyak variasi, inputkan satu-persatu variasi string username:password pada file wireshark.
- Ternyata username:password yang sesuai adalah dhafin:kesayangannyak0k0
<p align="center">
  <img src="https://i.ibb.co/Ns7sTR3/soal10-nc.png">
</p>

- Lalu flag akan muncul
`Flag: Jarkom2023{t3lnet_is_ABCy8xA4y2x3B9yA2_N0tSecu2e}`


### kendala
- Pada saat pengerjaan laptop saya (Brigita Naraduhita) belum menginstall linux dan pada windows belum mempersiapkan ncat. ketika mendownload ncat kesulitan karena terkena antivirus.
- Saat pengerjaan, sempat beberapa kali seperti down dan loading cukup lama untuk menampilkan soal.
- Belum begitu paham cara penggunaan wireshark, seperti apakah bisa menghitung paket hasil filter secara otomatis.
