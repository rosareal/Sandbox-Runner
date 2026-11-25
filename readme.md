Proyek Kelompok Mata Kuliah **Sistem Operasi (TIK103)**  
Program Studi **D4 Rekayasa Keamanan Siber – Politeknik Negeri Jakarta**

## 👥 Anggota Kelompok & Pembagian Fokus Kerja

| Nama Mahasiswa | Fokus Peran | Tanggung Jawab Utama |
| :--- | :--- | :--- |
| **Tristan Birendra Rozi** | Ketua Kelompok & Arsitek Sistem | Inisialisasi repositori Git, manajemen jadwal, penyusunan `README.md`, & integrasi sistem |
| **Cello Gemayel Aswan** | Pengembang Inti (*Resource & Isolation*) | Implementasi pembatasan sumber daya (`setrlimit`: CPU, RAM, NPROC) & isolasi direktori sementara |
| **Muhammad Farrelivo Kafka Herdian** | Pengembang Inti (*Process & Execution*) | Implementasi eksekusi *child process* (`subprocess`), penanganan *timeout*, & tangkapan output |
| **Rosa Salsabillah Putri Wardoyo** | Penguji (QA) & Dokumentator | Penyusunan skrip uji berbahaya (`tests/`), dokumen proposal (`docs/PROPOSAL.md`), & `CHANGELOG.md` |
EOF

# Sandbox Runner

Skrip wrapper berbasis Bash untuk menjalankan program yang tidak dipercaya
dengan batas waktu, memori, dan jumlah proses, sebagai user khusus berhak minim.

Proyek mata kuliah Sistem Operasi

## Latar Belakang

Menjalankan skrip dari sumber yang tidak jelas menggunakan akun sendiri
berisiko. Program bisa membuat sistem hang (loop tanpa henti, fork bomb)
atau menyentuh berkas pribadi pengguna. Sandbox Runner membatasi apa yang
bisa dilakukan program tersebut.

## Fitur

- [x] Batas waktu eksekusi (must have)
- [ ] Batas memori dan jumlah proses
- [ ] Eksekusi sebagai `sandboxuser` di folder kerja terpisah
- [ ] Log setiap eksekusi
- [ ] Pembersihan folder kerja setelah selesai

## Kebutuhan

- Linux (diuji di [nama distro, misal Ubuntu 24.04]) di dalam mesin virtual
- Bash
- Akses `sudo`

## Cara Menjalankan

Belum tersedia, akan dilengkapi setelah fitur must have selesai.

## Batasan

Sandbox Runner adalah pembatas sumber daya dan hak akses, bukan isolasi
penuh. Program yang dijalankan masih dapat membaca berkas yang terbuka
untuk semua user (misalnya `/etc/passwd`) dan mengakses jaringan.

## Peringatan

Skrip ini membutuhkan `sudo`, menambah user ke sistem, dan pengujiannya
sengaja menjalankan program perusak. Jalankan hanya di mesin virtual.
