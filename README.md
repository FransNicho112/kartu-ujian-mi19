---
title: Generator Kartu Ujian MI Al-Wathoniyah 19
emoji: 🪪
colorFrom: green
colorTo: blue
sdk: static
pinned: false
---

# Generator Kartu Ujian

Pilih daftar siswa (Excel, satu sheet per kelas: 1A … 6B) → unduh file Word berisi kartu ujian dengan
**nama, kelas, dan nomor ujian** terisi otomatis. Semua proses berjalan di browser; file tidak dikirim ke server.

## Cara pakai
Buka `index.html` (klik dua kali pun bisa, tanpa internet) atau alamat situs kalau sudah di-hosting.

## Aturan nomor ujian
`19` (kode sekolah) + tingkat kelas 2 digit + nomor urut 3 digit di kelasnya, mengikuti urutan Excel.
Contoh: siswa ke-7 di kelas 5B → `1905007`. Kelas A dan B sama-sama mulai dari 001 (sesuai kartu lama).
Nama yang sama dalam satu kelas tetap dibuatkan kartu masing-masing (bisa saja dua siswa berbeda).

## Judul kartu (dipilih di halaman web)
Langkah 3: pilih jenis ujian (STS / ASTS / SAS), semester (Ganjil / Genap), dan isi tahun pelajaran dua digit
terakhir (`20__ – 20__`; tahun kedua terisi otomatis = tahun pertama + 1). Semua wajib diisi.
Daftar jenis ujian ada di `JENIS_UJIAN` di `src/kartu.js`; tambahkan di situ kalau sekolah memakai singkatan lain.

## Yang masih diganti manual di Word (Ctrl+H)
Tanggal dan nama ketua panitia. Isi bawaannya ada di `CONFIG` di bagian atas `src/kartu.js`.

## Hosting gratis
- **Hugging Face Static Space**: buat Space baru dengan SDK *Static*, unggah `index.html`, `app.js`, `README.md`.
- **GitHub Pages**: unggah `index.html` dan `app.js` ke repo, aktifkan Pages.

## Mengubah kode
File yang dipakai browser hanya `index.html` dan `app.js`. `app.js` dibangun dari folder `src/`:
```
npm install
npm run build        # menghasilkan app.js
node test.js DAFTAR.xlsx hasil.docx   # uji cepat di terminal
```
