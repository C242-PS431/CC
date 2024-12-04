# Dokumentasi VPC Network: Freshguard Network

## Informasi Penting
- **Nama Network**: freshguard-network
- **Subnet Creation Mode**: Custom subnets

---

## Subnets

#### Alasan Konfigurasi Subnet
- Subnet `privat` digunakan untuk komunikasi internal antar layanan di jaringan. IP range `192.168.2.0/24` dipilih karena cukup untuk kebutuhan internal dan menjaga keamanan data.
- Subnet `public` dirancang untuk layanan yang memerlukan akses dari luar jaringan. IP range `192.168.1.0/24` dipisahkan agar mempermudah pengelolaan dan meningkatkan isolasi antar subnet.

### Subnet: `privat`
- **Region**: asia-southeast2
- **IP Range**: 192.168.2.0/24

### Subnet: `public`
- **Region**: asia-southeast2
- **IP Range**: 192.168.1.0/24

---

## Firewall Rules

### **Alasan Konfigurasi Firewall:**
- **Aturan HTTPS** dibuat untuk mendukung koneksi aman dengan enkripsi, yang sangat penting untuk melindungi data yang ditransfer antara pengguna dan aplikasi.
- **Aturan HTTP** disediakan untuk kompatibilitas awal sebelum mengarahkan pengguna ke koneksi HTTPS, meskipun komunikasi ini tidak terenkripsi.
- **Aturan SSH** diaktifkan untuk memungkinkan akses jarak jauh ke server melalui koneksi aman (SSH) untuk administrasi dan pemeliharaan server.

### Aturan Firewall:
1. **freshguard-network-allow-https**
   - **Port**: TCP 443
   - **Akses**: Mengizinkan koneksi HTTPS dari semua sumber (`0.0.0.0/0`) untuk komunikasi yang aman.
2. **freshguard-network-allow-http**
   - **Port**: TCP 80
   - **Akses**: Mengizinkan koneksi HTTP dari semua sumber (`0.0.0.0/0`) untuk kebutuhan koneksi awal (non-enkripsi).
3. **allow-ssh**
   - **Port**: TCP 22
   - **Akses**: Mengizinkan koneksi SSH dari semua sumber (`0.0.0.0/0`) untuk keperluan manajemen server jarak jauh.
---

## Kesimpulan
Konfigurasi ini dibuat untuk mengoptimalkan pengelolaan jaringan. Pemisahan subnet `privat` dan `public` memastikan komunikasi internal dan eksternal terisolasi dengan baik, sedangkan firewall rules memberikan fleksibilitas sekaligus keamanan dalam akses layanan.
