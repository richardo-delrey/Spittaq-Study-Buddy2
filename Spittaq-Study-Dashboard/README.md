# Spittaq Study Dashboard

Dashboard belajar responsif untuk siswa SMP. Proyek ini memakai Node.js tanpa paket tambahan dan menyimpan data backend di file JSON.

Menu Materi Belajar menampilkan materi yang diunggah guru untuk kelas siswa (kelas 7, 8, atau 9). Portal guru menyediakan halaman Kelola Materi dengan unggah, unduh, dan hapus materi. Berkas materi disimpan di `data/materials` bersama backend.

## Struktur proyek

```text
Spittaq-Study-Dashboard/
├── data/
│   └── study-data.json
├── public/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   ├── app.js
│   │   └── fallback-data.js
│   └── index.html
├── package.json
├── server.js
└── start-server.bat
```

## Menjalankan website di Windows

Cara paling mudah: klik dua kali `start-server.bat`, lalu buka <http://localhost:3000>.

Atau, buka terminal pada folder proyek dan jalankan:

```powershell
npm start
```

Jika `npm` tidak dikenali tetapi Node.js tersedia, jalankan `node server.js`. Node.js versi 18 atau lebih baru diperlukan untuk backend.

## Pratinjau tanpa backend

Buka `public/index.html` langsung di browser. Mode lokal mendukung pencarian, filter, kalender, tambah/hapus tugas, dan Buddy AI demo. Perubahan tugas disimpan di browser jika penyimpanan lokal tersedia.

## API

- `GET /api/dashboard` — data dashboard dan ringkasan.
- `GET /api/tasks` — daftar tugas.
- `POST /api/tasks` — tambah tugas.
- `PATCH /api/tasks/:id` — ubah status selesai.
- `DELETE /api/tasks/:id` — hapus tugas.
- `GET /api/subjects` — daftar mata pelajaran.

## Website dan akun

- Study Buddy siswa: <http://localhost:3000/>.
- Portal guru yang berada di folder terpisah: <http://localhost:3000/guru/>.
- Pertahankan folder `Spittaq-Teacher-Portal` sejajar dengan `Spittaq-Study-Dashboard`.
- Buat akun siswa dari halaman masuk Study Buddy dan akun guru dari Portal Guru. Siswa memilih guru tujuan saat mengumpulkan tugas.
- Akun memiliki peran terpisah. Siswa mengelola tugas dan pengumpulannya sendiri; guru melihat kiriman siswa, mengunduh file, memberi status, dan umpan balik.
- Nama pengguna dan hash kata sandi disimpan di `data/accounts.json`; sesi berakhir saat server dimulai ulang.
- Jalankan `npm start` dari folder ini. Untuk membuka server yang sama dari folder portal guru, jalankan `npm start` di folder `Spittaq-Teacher-Portal`.
