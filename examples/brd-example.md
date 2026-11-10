# Contoh BRD singkat — Filter Stok per Gudang

> **Status:** Seluruh isi merupakan contoh hipotetis. Tidak menjelaskan sistem perusahaan tertentu.

## Problem

Pada contoh sistem Inventory ini, daftar stok belum memiliki filter lokasi gudang. Staff perlu membuka setiap detail barang untuk memeriksa stok di gudang tertentu.

## Objective

Staff dapat melihat stok sesuai gudang yang dipilih tanpa membuka detail satu per satu.

## Scope

**In scope:** filter berdasarkan gudang, daftar stok, indikator hasil kosong.

**Out of scope:** perpindahan stok antar-gudang, perubahan quantity, proses approval.

## As-Is dan To-Be

| As-Is (ilustratif) | To-Be (usulan) |
|---|---|
| Daftar stok menampilkan semua gudang tanpa filter | Staff memilih gudang pada daftar stok |
| Staff membuka detail barang untuk melihat ketersediaan per gudang | Sistem menampilkan barang yang terkait gudang pilihan |

## Requirement

| ID | Actor | Requirement | Expected Result | Status |
|---|---|---|---|---|
| INV-001 | Staff | User dapat memilih gudang dari daftar yang diizinkan | Gudang yang dipilih menjadi filter aktif | Proposed |
| INV-002 | System | Setelah gudang dipilih, sistem memfilter daftar stok berdasarkan gudang itu | Barang dari gudang lain tidak ditampilkan | Proposed |
| INV-003 | System | Jika gudang tidak memiliki hasil, tampilkan empty state yang informatif | User melihat bahwa tidak ada data yang cocok | Proposed |

## Acceptance Criteria

- Given Staff memiliki akses gudang A dan memilih gudang A, when daftar stok dimuat, then hanya barang dengan stok pada gudang A yang tampil.
- Given tidak ada barang pada gudang pilihan, when filter diterapkan, then sistem menampilkan empty state, bukan error umum.

## Open questions

| Question | Impact | Status |
|---|---|---|
| Apakah opsi gudang dibatasi berdasarkan role? | Permission dan data visibility | Need Confirmation |
| Apakah default filter menunjukkan semua gudang atau gudang user? | Behavior awal screen | Need Confirmation |

Contoh ini menunjukkan struktur, bukan alasan untuk menganggap aturan di atas sudah disetujui pada proyek nyata.
