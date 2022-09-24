# Jarkom-Modul-1-ITA01-2022

Hasil Pengerjaan Soal Shift Praktikum SISTEM OPERASI 2022
Anggota Kelompok:
1. Muhammad Faris Anwari (5027201008)
2. Calvindra Laksmono Kumoro (5027201020)
3. Adinda Putri Audyna (5027201073)

## Soal 1-3

## Soal 4-6

## Soal 7-10
### 7. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

Sebelumnya praktikan menginput command [ip a] di terminal untuk mengetahui IP praktikan.

![ip a](./img/7_ip.jpg)

Sehingga didapat IP praktikan ialah `192.168.89.130`.

Capture Filter: 
> src host 192.168.89.130

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

Praktikan menyimpulkan bahwa nama karakter anime kembar lima ialah `nakano` dari Gotoubun no Hanayome.

---

### 9. Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.

### 10. Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!
