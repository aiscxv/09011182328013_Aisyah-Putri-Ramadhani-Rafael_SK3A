# Laporan Tugas Remote Linux Server dengan Linux Desktop
# Profil Mahasiswa
- Nama: Aisyah Putri Ramadhani Rafael
- Nim: 09011182328013
- Kelas: SK3A
- Mata Kuliah: Sistem Operasi
- Dosen Pengampu: Adi Hermansyah, S.Kom., M.T.
# 1. Instalasi Ubuntu Server
Sebelum memulai remote linux, langkah pertama yang harus dilakukan adalah menginstal Ubuntu Server pada VirtualBox. Ubuntu Server dapat didownload di link berikut: (https://releases.ubuntu.com/noble/)
![Screenshot 2024-10-30 202159](https://github.com/user-attachments/assets/fb21de3d-f512-4c3b-b82d-64e1798855de)
# 2. Persiapan SSH di Ubuntu Server
# 2.1. Instalasi OpenSSH Server di Linux Server
instalasi dapat dilakukan dengan menjalankan perintah berikut:
```sudo apt install openssh-server```
![Screenshot 2024-10-30 183832](https://github.com/user-attachments/assets/0a473d5e-286d-433d-8d46-a067d970fba1)
# 2.2. Mengaktifkan dan Melihat Status Layanan SSH
Layanan SSH perlu diaktifkan agar bisa berjalan otomatis setiap kali server dinyalakan. Silahkan gunakan perintah berikut.
```sudo systemctl enable ssh, sudo system systemctl start ssh```
![Screenshot 2024-10-30 184122](https://github.com/user-attachments/assets/1e81cb59-6e00-4f56-a205-4678a5bdc402)
# 2.3. Melihat Status Layanan SSH
untuk memastikan bahwa layananSSH berfungsi dengan baik, jalankan perintah berikut:
```sudo systemctl status ssh```
- Linux Server:
![Screenshot 2024-10-30 184154](https://github.com/user-attachments/assets/ffff56d1-f077-4d83-8ceb-8eadc127be5a)
- Linux desktop:
![Screenshot 2024-10-30 184957](https://github.com/user-attachments/assets/09e1ad0c-76ef-4287-82d7-128fc0212394)
# 3. Mengubah Port SSH Menjadi 40
Port default SSH yang sebelumnya adalah 22, kita ubah menjadi port 40
# 3.1. Mengedit Konfigurasi SSH
Silahkan buka file konfigurasi sshd_config dan ubahlah port menjadi 40:
```sudo nano /etc/ssh/sshd_config```
Untuk baris #port 22 dapat kita ubah menjadi port 40, kemudian simpan dan keluar.
- Linux Desktop:
![Screenshot 2024-10-30 185331](https://github.com/user-attachments/assets/cbda9026-ca62-4dd0-a9d3-9ef050126e4e)
- Linux Server:
![Screenshot 2024-10-30 184402](https://github.com/user-attachments/assets/48e7eeed-38dc-446a-b7d4-08a694a86eb7)
# 3.2. Restart Layanan SSH
untuk restart layanan SSH, gunakan perintah berikut:
```sudo systemctl restart ssh```
- Linux Desktop:
![Screenshot 2024-10-30 185358](https://github.com/user-attachments/assets/ec104e47-e980-4f23-9efb-d62b4ea94a5c)
- Linux Server:
![Screenshot 2024-10-30 185526](https://github.com/user-attachments/assets/e447cf97-745a-4ab8-993a-444a8aded006)
# 4. Mencoba dan Melihat Remote Sebelum dan Sesudah Mengubah Port
# 4.1 Remote Sebelum Mengubah Port
Mari kita lihat percobaan sebelum mengubah port, dengan remote port default 22
```ssh username@server_ip```
- Linux Desktop:
![Screenshot 2024-10-30 185626](https://github.com/user-attachments/assets/c5fa470d-d7bc-4519-8770-ff6451c8bb62)
- Linux Server:
![Screenshot 2024-10-30 185526](https://github.com/user-attachments/assets/8d465896-c601-4941-a98b-9c10b904580f)
# 4.2. Remote Setelah Mengubah Port
Setelah mengubah port menjadi 40, maka untuk melihat hasilnya gunakan perintah berikut:
```ssh username@server_ip -p 40```
- Linux Desktop:
![Screenshot 2024-10-30 200826](https://github.com/user-attachments/assets/dda00b00-33e9-4dcf-a188-41bdfbb3cf2d)
- Linux Server:
![Screenshot 2024-10-30 200405](https://github.com/user-attachments/assets/bee648df-a9dd-4bb0-bc64-221112df6edf)
# Kesimpulan
Dalam laporan praktikum ini, berhasil dilakukan remote ke server Linux menggunakan desktop Linux melalui SSH. Langkah pertama adalah menginstal OpenSSH di server dan memastikan layanan SSH berjalan dengan baik. Selanjutnya, port default SSH diubah menjadi port 40 untuk meningkatkan keamanan koneksi. Proses ini melibatkan perubahan pengaturan di file konfigurasi sshd_config dan memastikan bahwa firewall mengizinkan koneksi di port baru. Praktikum ini menunjukkan betapa pentingnya pengaturan yang benar untuk menjaga keamanan dan kelancaran sistem server.

















