# Cara upload repository ke GitHub

## Melalui website GitHub

1. Buat repository baru di akun GitHub, misalnya `business-system-analysis-skill`.
2. Sebaiknya buat repository kosong, tanpa README otomatis, karena paket sudah berisi README.
3. Extract paket ZIP di komputer.
4. Di halaman repository, pilih **Add file → Upload files**.
5. Upload isi folder `business-system-analysis-skill` dari dalam foldernya, bukan ZIP utuh, supaya `README.md` berada di root repository.
6. Commit perubahan dan pastikan Markdown / Mermaid terbaca.

Untuk repository dengan banyak file, Git atau GitHub Desktop umumnya lebih mudah daripada upload manual.

## Menggunakan Git CLI

Jalankan dari dalam folder `business-system-analysis-skill` setelah membuat repository kosong di GitHub.

```bash
git init
git add .
git commit -m "docs: add BA and SA reusable skill"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/business-system-analysis-skill.git
git push -u origin main
```

Ganti `YOUR_USERNAME` dan nama repository sesuai tujuan. Pastikan autentikasi GitHub sudah dikonfigurasi pada perangkat. Jangan menempel token GitHub di file atau commit.

Jika repository tujuan sudah ada, lakukan clone lalu tambahkan atau gabungkan file ke branch baru. Periksa konflik sebelum push, dan buat Pull Request jika proses tim mengharuskannya.

## Setelah upload

- Pastikan `README.md` tampil pada halaman awal repository.
- Pastikan `SKILL.md` ada di root.
- Buka `docs/sequence-diagrams.md` untuk mengecek preview Mermaid.
- Konfirmasi bahwa tidak ada dokumen rahasia, screenshot internal, credentials, atau data pelanggan yang terikut.
- Pilih visibility Public atau Private sesuai kebijakan pemilik repo dan hak distribusi materi.
- Lisensi publik belum dipilih, jadi jangan mengasumsikan seluruh materi boleh dipakai ulang tanpa izin.
