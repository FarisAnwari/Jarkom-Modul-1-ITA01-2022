# Jarkom-Modul-1-ITA01-2022

Hasil Pengerjaan Soal Shift Praktikum SISTEM OPERASI 2022
Anggota Kelompok:
1. Muhammad Faris Anwari (5027201008)
2. Calvindra Laksmono Kumoro (5027201020)
3. Adinda Putri Audyna (5027201073)

Pembagian Kontribusi:
- Soal 1-3: Calvindra Laksmono Kumoro
- Soal 4-6: Adinda Putri Audyna
- Soal 7-10: Muhammad Faris Anwari

## Soal 1-3
### 1. Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!
Praktikan mencari web server dengan kata kunci `monta` melalui filter berikut:

![hasil filter](/img/1_monta.JPG)

Kemudian praktikan mengfollow HTTP Stream hingga didapati web server yang dimaksud.

![server](/img/1_server.JPG)

---

### 2. Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?
Praktikan memfilter dengan cara yang sama di nomor 1.

![hasil filter](/img/1_monta.JPG)

Lalu praktikan mengklik kanan salah satu entri secara acak, lalu Follow -> HTTP Stream. Hasilnya sebagaimana tergambarkan di bawah.

![http stream](/img/2_stream.JPG)

Praktikan mengganti tampilan data menjadi Raw.

![raw](/img/2_raw.JPG)

Raw file kemudian di-*save as* sebagai .html

![html](/img/2_savehtml.JPG)

Praktikan membuka HTML dan mengklik `4222` di kolom ID dalam bagian Sidang Proposal Tugas Akhir.

![judul TA](/img/2_judulta.JPG)

Sehingga didapatlah judul TA, yakni 

> **Perancangan Sistem Pengendali Panas Otomatis pada Mesin Sangrai Kopi dengan Logika Fuzzy**

---

### 3. Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!
Filter:

```
tcp.dstport == 80 || udp.dstport == 80
```

Hasil:

![hasil filter](/img/3.JPG)

---

## Soal 4-6
### 4. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!
Untuk soal ini, karena packet sudah ada di .pcapng, maka buka Wireshark dan open filenya, lalu terapkan Read Filter (sintaks sama dengan display filter, meskipun pada efeknya mirip capture filter bagi file .pcapng)

```
tcp.srcport == 21 || udp.srcport == 21
```

<img width="419" alt="modul1-4 1" src="https://user-images.githubusercontent.com/58323466/192100154-e8eac9b1-51a2-42ea-bf7c-cd12179efa14.png">

<img width="960" alt="modul1-4 2" src="https://user-images.githubusercontent.com/58323466/192100161-d28ebc17-2ece-4f2e-92a9-0ccc79d742f9.png">

---

### 5. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!
Untuk soal ini, karena packet sudah ada di .pcapng, maka buka Wireshark dan open filenya, lalu terapkan Read Filter (sintaks sama dengan display filter, meskipun pada efeknya mirip capture filter bagi file .pcapng)

```
tcp.srcport == 443 || udp.srcport == 443
```

<img width="419" alt="modul1-5 1" src="https://user-images.githubusercontent.com/58323466/192100270-d657aea5-37ca-4de0-8d34-1ee4bdb7741f.png">

<img width="960" alt="modul1-5 2" src="https://user-images.githubusercontent.com/58323466/192100273-92dcd1ca-05ba-43a0-89ee-2d2e11e931f9.png">

---

### 6. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!
Pertama kita melakukan pengecekan ip pada website lipi.go.id ke dalam terminal dengan menggunakan command `ping lipi.go.id`

<img width="675" alt="modul1-6 1" src="https://user-images.githubusercontent.com/58323466/192100318-0c75df83-744f-4cf1-a9d9-d57bdc8f441e.png">

Lalu didapat ip 203.160.128.158 sehingga

```
ip.dst== 203.160.128.158 || ip.dst== 203.160.128.158
```

<img width="960" alt="modul1-6 2" src="https://user-images.githubusercontent.com/58323466/192100424-6cd4552e-1cd9-4f76-8fe1-bc43a07b52e0.png">

---

## Soal 7-10
### 7. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Sebelumnya praktikan menginput command [ip a] di terminal untuk mengetahui IP praktikan.

![ip a](./img/7_ip.jpg)

Sehingga didapat IP praktikan ialah `192.168.89.130`.

Capture Filter: 
```
src host 192.168.89.130
```

![capture](./img/7_cap.jpg)

Dengan demikian, praktikan berhasil mengambil paket yang berasal dari IP praktikan.

---

Untuk soal 8-10, silahkan baca cerita di bawah ini!

> Di sebuah planet bernama Viltrumite, terdapat Kementerian Komunikasi dan Informatika yang baru saja menetapkan kebijakan baru. Dalam kebijakan baru tersebut, pemerintah dapat mengakses data pribadi masyarakat secara bebas jika memang dibutuhkan, baik dengan maupun tanpa persetujuan pihak yang bersangkutan. Sebagai mahasiswa yang sedang melaksanakan program magang di kementerian tersebut, kalian mendapat tugas berupa penyadapan percakapan mahasiswa yang diduga melakukan tindak kecurangan dalam kegiatan Praktikum Komunikasi Data dan Jaringan Komputer 2022. Selain itu, terdapat sebuah password rahasia (flag) yang diduga merupakan milik sebuah organisasi bawah tanah yang selama ini tidak sejalan dengan pemerintahan Planet Viltrumite. Tunggu apa lagi, segera kerjakan tugas magang tersebut agar kalian bisa mendapatkan pujian serta kenaikan jabatan di kementerian tersebut!

### 8. Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

Praktikan mendapat isi percakapan dengan cara mengfollow TCP stream lalu meng*bruteforce* klik pindah stream hingga mendapati percakapan mencurigakan di stream 12. Ternyata setelah diobservasi lebih lanjut, percakapan antara dua mahasiswa ini melibatkan port 60236 dan 65432.

![convo](/img/8_stream_12.jpg)

Dari percakapan ini, praktikan memeroleh informasi penting perihal kecurangan, bahwa:
- File selundupan merupakan file salt
- File dapat didecrypt dengan metode des3
- Password ialah nama karakter anime kembar lima
- Pengiriman file lewat port 9002

---

### 9. Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.

Praktikan menyimpulkan bahwa nama karakter anime kembar lima ialah `nakano` dari Gotoubun no Hanayome. Kemudian praktikan mencoba mencari paket yang berasal dari port 9002 dengan display filter berikut:

```
tcp.srcport == 9002
```

![filter 9002](/img/9_9002.jpg)

Praktikan lalu mengfollow TCP stream paket-paket tersebut.

![link youtube](/img/9_yutub.jpg)

Rupanya ini merupakan jejak palsu. Praktikan tertipu oleh link-link palsu tersebut, dan diarahkan menuju video meme. Disinilah letak kendala yang praktikan alami. Setelah pertimbangan lebih lanjut, praktikan menggunakan filter:

```
tcp.dstport == 9002
```

![true trail](/img/9_9002real.jpg)

Praktikan mengfollow TCP Stream dan mendapatkan *jackpot*

![file salt](/img/9_salt.jpg)

Praktikan mengubah tipe data menjadi raw dan menyimpannya sebagai `ITA02.des3`, lalu mendecryptnya menggunakan openssl dengan password `nakano`

![decryption](/img/9_decrypt.jpg)

---

### 10. Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

Praktikan membuka file flag.txt dan mendapat password rahasia sebagaimana berikut:

![flag](/img/10_flag.jpg)

---

### Kendala yang Dialami

- Praktikan sempat terhambat dalam mencari file salt yang dikirim di port 9002, hingga praktikan menyadari bahwa bisa saja file dikirim *kepada* port 9002, bukan hanya *dari* port 9002
- Praktikan juga terkendala dalam mengdecrypt file salt, dimana praktikan mengsolve kendala ini dengan mencari syntax openssl yang sesuai di [https://osxdaily.com/2012/01/30/encrypt-and-decrypt-files-with-openssl/](https://osxdaily.com/2012/01/30/encrypt-and-decrypt-files-with-openssl/)
