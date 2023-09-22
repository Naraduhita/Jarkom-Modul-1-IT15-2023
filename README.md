
# Jarkom Modul 1

|      Nama Anggota       |     NRP     |
| ---                     | ---         |
| Oktavia Anggraeni P.    | 5027211001  |
| Brigita Naraduhita P.P. | 5027211055  |

1. Pada soal tersebut diketahui bahwa user melakukan aktivitas salah satunya mengunggah suatu file.
**Cara mengerjakan:**
- Download dan buka file yang telah disediakan bertipe wireshark capture file
- Klikkan find dan ketikkan `ftp || ftp-data` untuk mengambil paket-paket yang terkait dengan protokol FTP (File Transfer Protocol) atau paket data yang dikirim melalui FTP. 
- User melakukan aktivitas mengunggah suatu file. Maka cari perintah bertuliskan `STOR` yang berfungsi untuk mengupload file ke FTP server.
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/ad6b553f-9713-4e17-ae06-810597c068f4" height="150"/>


- Lalu analisis dan cari sequence number (raw), acknowledge number (raw) pada paket tersebut  yang menunjukkan aktivitas.
<img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/f9c5fa48-e76b-4731-8dae-d6f92ea70812" height="300"/>

- Lalu klik paket satu dibawahnya yang paket ACK, ACK menandakan data sebelumnya telah diterima dan penerima siap menerima data berikutnya.
- Lalu analisis dan cari sequence number (raw), acknowledge number (raw) pada paket tersebut  yang menunjukkan response dari aktivitas tersebut.
 <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/e58f3f89-3092-4122-bdc6-8ff0eca8617e" height="300"/>

 
- Lalu buka terminal dan ketikkan `ncat 10.21.78.111 12345` untuk mengakses ke alamat IP 10.21.78.111 pada port 12345 menggunakan netcat.
- Ketikkan nilai yang didapat sesuai soal
  <img src="https://github.com/Naraduhita/Jarkom-Modul-1-IT15-2023/assets/102397053/4f07f2fa-a6ae-4640-8b8e-23e48b27d042" height="300"/>

  
- Lalu flag akan ditampilkan
 `Flag:  Jarkom2023{y0u_r_g00d_4t_4dr3ssing_MoDvEwK76448553}`

 4. Pada soal tersebut diminta untuk menemukan nilai checksum yang didapat dari header pada paket nomor 130.
**Cara mengerjakan:**
- Mendownload dan buka file yang telah disediakan bertipe wireshark capture file
- Lakukan pencarian untuk paket nomor 130 sesuai dengan perintah
- Analisis paket tersebut dan mencari nilai checksum. Di dapatkan: `Checksum: 0x18e5`
- Lalu buka terminal dan ketikkan `ncat 10.21.78.111 13591` untuk mengakses ke alamat IP 10.21.78.111 pada port 13591 menggunakan netcat.
- Ketikkan  nilai checksum `0x18e5` sesuai dengan nilai yang didapatkan.
- Lalu flag akan ditampilkan
`Flag:  Jarkom2023{ch3cksum_is_u5eful_0xj7l4}`

7. Pada soal tersebut diminta untuk menyebutkan jumlah packet yang menuju IP 184.87.193.88
**Cara mengerjakan:**
- Download dan buka file yang telah disediakan bertipe wireshark capture file
- Klikkan `find a packet` dan ketikkan `ip.dst == 184.87.193.88` untuk mengambil semua paket yang memiliki alamat tujuan (destination IP address) 184.87.193.88. 
- Lalu akan menampilkan semua paket yang ditujukan ke alamat IP tersebut.
- Lalu hitung jumlah paket yang sesuai dan didapatkan total `6` paket
- Lalu buka terminal dan ketikkan `nc 10.21.78.111 6565` untuk mengakses ke alamat IP 10.21.78.111 pada port 6565 menggunakan netcat.
- Ketikkan `6` sesuai dengan jumlah paket yang didapatkan.
- Lalu flag akan didapatkan.
`Flag: Jarkom2023{A6J9sXQi0kKgSMM440_4n0th3r_f1lt3ring}`

8. Pada soal tersebut diminta untuk memberikan kueri filter untuk menampilkan protokol paket yang menuju port 80.
**Cara mengerjakan:**
- Download dan buka file yang telah disediakan bertipe wireshark capture file
- Kueri filter pada Wireshark yang dapat digunakan untuk menampilkan paket yang menuju port 80 dengan dua kriteria ialah `tcp.dstport == 80 || udp.dstport == 80`
- `tcp.dstport == 80` digunakan untuk menampilkan semua paket dengan protokol TCP yang menuju port (destination port) 80
- `udp.dstport == 80` digunakan untuk menampilkan semua paket dengan protokol UDP yang menuju port (destination port) 80
- Lalu buka terminal dan ketikkan `ncat 10.21.78.111 7171`  untuk mengakses ke alamat IP 10.21.78.111 pada port  7171 menggunakan netcat.
- Masukkan kueri tersebut dan flag akan didapatkan.
`Flag: Jarkom2023{qu3ryyyyying_134463_PiDzRvCjEiA_15_fun}`

9. Pada soal tersebut diminta kueri filter untuk menampilkan paket yang berasal dari alamat `10.51.40.1` tetapi `tidak`menuju ke alamat `10.39.55.34`
**Cara mengerjakan:**
- Download dan buka file yang telah disediakan bertipe wireshark capture file
- Kueri filter pada Wireshark yang dapat digunakan untuk menampilkan paket yang menuju port 80 dengan dua kriteria ialah `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`
- `p.src == 10.51.40.1` berfungsi untuk menampilkan semua paket yang berasal dari alamat tersebut. 
- `ip.dst != 10.39.55.34` berfungsi untuk menampilkan paket selain yang berasal dari alamat tersebut.
- Lalu buka terminal dan ketikkan `ncat 10.21.78.111 13591` untuk mengakses ke alamat IP 10.21.78.111 pada port 7272 menggunakan netcat.
- Lalu akan didapat flag
`Flag: Jarkom2023{y3s_its_QkNhShOkOiP_qu3ry1ng}`

### kendala
- Pada saat pengerjaan laptop saya (Brigita Naraduhita) belum menginstall linux dan pada windows belum mempersiapkan ncat. ketika mendownload ncat kesulitan karena terkena antivirus.
- Saat pengerjaan, sempat beberapa kali seperti down dan loading cukup lama untuk menampilkan soal.
- Belum begitu paham cara penggunaan wireshark, seperti apakah bisa menghitung paket hasil filter secara otomatis.
