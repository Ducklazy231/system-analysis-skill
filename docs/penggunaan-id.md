# Panduan penggunaan

Gunakan `SKILL.md` sebagai aturan kerja general, bukan sebagai data proyek. Untuk tiap tugas, tetap berikan konteks, keputusan bisnis, dan evidence yang relevan.

## Pemakaian di AI yang berbeda

| Lingkungan | Cara pakai |
|---|---|
| ChatGPT | Upload `SKILL.md` atau sertakan sebagai instruksi dalam project yang relevan. Minta AI membaca sebelum mengerjakan task. |
| Claude | Sertakan `SKILL.md` di project knowledge atau gunakan `CLAUDE.md` sebagai pointer bila environment membaca file itu. |
| Coding agents | Sertakan repository dalam workspace dan gunakan `AGENTS.md` untuk tools yang mendukung. |
| AI lainnya | Lampirkan atau tempel isi `SKILL.md` pada system/project instructions jika produk mendukung. |

Penggunaan bergantung pada fitur masing-masing AI. Jangan berasumsi isi file otomatis dibaca ketika tidak ada mekanisme auto-load.

## Cara memberikan konteks task

Berikan seperlunya:

1. Jenis pekerjaan, misalnya Jira bug, BRD, FRD, analisis API, atau sequence diagram.
2. Deskripsi masalah dan kondisi existing.
3. Evidence seperti screenshot, MoM, log, data, atau dokumen sistem.
4. Keputusan yang sudah disepakati dan hal yang belum diputuskan.
5. Format output, bahasa, tingkat detail, serta pembaca dokumen.

## Contoh prompt dokumentasi

> Gunakan SKILL.md. Susun BRD modul Inventory berdasarkan dokumen berikut. Fokus pada As-Is, To-Be, Business Requirements, Role Permission, Business Rules, Acceptance Criteria, dan Open Questions. Tidak perlu intro generik atau bagian yang tidak relevan. Jangan mengarang role, field, atau proses yang belum dibahas.

## Contoh prompt API

> Gunakan SKILL.md. Analisis integrasi Order Service dengan External Service berdasarkan kontrak API berikut. Jelaskan trigger, payload, response, status, error, retry, idempotency, dan tanggung jawab tiap sistem. Buat sequence diagram Mermaid yang panjangnya cukup untuk dibaca, tanpa mengarang endpoint baru.

## Contoh prompt output Word

> Ubah hasil analisis ini menjadi DOCX yang editable dengan format internal A4, font standar, heading sederhana, tabel rapi, dan tanpa cover dekoratif, header, atau footer tambahan.

## Cara menilai hasil

Periksa apakah setiap requirement memiliki aktor, trigger, kondisi, dan expected result. Periksa apakah status `Confirmed` memiliki dasar, diagram sesuai narasi, dan pertanyaan yang belum disepakati tidak tertutup oleh asumsi.
