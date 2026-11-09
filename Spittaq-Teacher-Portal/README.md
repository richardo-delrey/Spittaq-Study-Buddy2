# Spittaq Teacher Portal

Website guru berada dalam folder terpisah dan memakai backend yang sama dengan Spittaq Study Buddy.

- URL portal guru: <http://localhost:3000/guru/>
- URL Study Buddy siswa: <http://localhost:3000/>
- Untuk menjalankan, klik `start-server.bat`, atau jalankan `npm start` / `node ../Spittaq-Study-Dashboard/server.js` dari folder ini.
- Guru dapat membuat akun masing-masing melalui tombol daftar. Siswa memilih guru penerima pada formulir pengumpulan.
- Akun siswa dibuat dari halaman masuk Study Buddy. Setiap akun siswa hanya melihat tugas dan pengumpulan miliknya.
- Guru melihat semua pengumpulan, mengunduh file, mengubah status, dan memberi umpan balik.
- Guru dapat membuka menu **Kelola Materi Belajar** dari portal, lalu mengunggah materi untuk kelas 7, 8, atau 9. Siswa melihat materi untuk kelas yang tercantum pada profilnya.
- Materi menerima PDF, Word, PowerPoint, dan gambar hingga 10 MB. File tersimpan di `Spittaq-Study-Dashboard/data/materials`.

Kedua website membutuhkan folder `Spittaq-Study-Dashboard` dan `Spittaq-Teacher-Portal` tetap berada sejajar di dalam folder `outputs`.

## Akun dan penyimpanan

Pengguna disimpan di `Spittaq-Study-Dashboard/data/accounts.json`. Kata sandi disimpan sebagai hash scrypt, bukan teks biasa. Sesi akun berlaku selama server aktif; jika server dimulai ulang, pengguna perlu masuk lagi. Untuk menjalankan di internet, tambahkan HTTPS, perlindungan pendaftaran guru, dan pengelolaan sesi produksi.

- Form penilaian memakai penggeser nilai 50–100 dan status centang/silang (sudah dinilai atau belum). Nilai serta umpan balik tersimpan pada riwayat siswa.
