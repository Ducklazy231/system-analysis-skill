# Anti-AI Slop untuk dokumentasi Bahasa Indonesia

Pedoman ini memperluas bagian 3A di [`SKILL.md`](../SKILL.md). Tujuannya bukan membuat bahasa terlalu santai, tetapi menghapus kalimat yang terdengar resmi tanpa memberi informasi.

## Prinsip

- Sebut masalah atau perubahan langsung pada kalimat pertama jika konteks sudah jelas.
- Sebut aktor, menu, field, status, trigger, dan hasil yang benar-benar diketahui.
- Jangan mengganti istilah sistem yang dipakai tim hanya agar terlihat lebih baku.
- Jangan memakai `optimalisasi`, `seamless`, `komprehensif`, atau `efisiensi` sebagai pengganti deskripsi perilaku.
- Hindari klaim seperti `telah disetujui stakeholder` jika keputusan tersebut tidak terbukti.
- Gunakan English untuk istilah teknis yang lazim seperti API, validation, approval, payload, status, webhook, dan rollback.
- `Harus` untuk kewajiban yang sudah diputuskan, `dapat` untuk kemampuan, dan `diusulkan` untuk rekomendasi.
- Jangan otomatis menambahkan kesimpulan, manfaat, atau pengantar untuk satu Jira ticket.

## Contoh revisi

| Konteks | Terlalu generik | Lebih jelas |
|---|---|---|
| Problem | Diperlukan optimalisasi modul Inventory demi efektivitas operasional | Pada contoh ini, daftar stok belum bisa difilter per gudang. User harus membuka setiap barang untuk melihat stok di gudang tertentu |
| Requirement | Sistem harus memiliki fitur yang user-friendly | User dapat memilih gudang dan sistem menampilkan barang yang tersedia pada gudang tersebut |
| Approval | Perlu peningkatan mekanisme approval yang terintegrasi | Saat request di-submit, sistem menetapkan status Pending Approval dan menentukan approver berdasarkan rule yang berlaku |
| Validation | Sistem memvalidasi data secara optimal | Sistem menolak penyimpanan jika Department belum dipilih |
| Jira | Ada kendala yang menghambat pengalaman pengguna | Tombol Cancel menampilkan error saat dokumen memiliki referensi transaksi |
| API | Data diproses seamless dengan sistem eksternal | Backend mengirim request ke layanan eksternal, lalu menyimpan reference ID dari response |
| MoM | Semua stakeholder berkomitmen mendukung solusi ini | Tim menyepakati kebutuhan filter gudang. Aturan default gudang belum ditentukan |
| UAT | Sistem berjalan sesuai ekspektasi | Filter gudang A hanya menampilkan barang yang terdaftar pada gudang A |

**Semua contoh bersifat hipotetis.** Jangan menulis kondisi contoh sebagai fakta dari proyek lain.

## Pola penulisan yang bisa diterapkan

**As-Is:** `[Aktor/modul] saat ini [kondisi yang terverifikasi]. Dampaknya [masalah yang diketahui].`

**To-Be:** `Saat [trigger], [aktor] melakukan [aksi]. Sistem [validasi/proses] dan [hasil].`

**Business Rule:** `Jika [kondisi], sistem harus [perilaku yang dapat diuji].`

**Need Confirmation:** `Belum ditentukan [keputusan]. Dampak: [proses/fitur yang menunggu keputusan].`

Pola ini membantu penulisan, bukan template wajib yang harus diulang pada setiap paragraf.

## Pemeriksaan akhir

1. Apakah pembuka bisa dihapus tanpa menghilangkan informasi?
2. Apakah kata sifat promosi menggantikan detail sistem yang seharusnya dijelaskan?
3. Apakah ada dua kalimat yang menyampaikan arti sama?
4. Apakah aktor, kondisi, status, dan expected result cukup jelas untuk developer dan QA?
5. Apakah istilah teknis dan label UI konsisten?
6. Apakah setiap klaim `Confirmed` punya sumber?
7. Apakah dokumen sesuai panjang yang diminta, bukan dipanjang-panjangkan?
