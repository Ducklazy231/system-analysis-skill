# Standar sequence diagram

`SKILL.md` bagian 8 memuat aturan lengkap dan tiga contoh end-to-end. Dokumen ini menjelaskan bagaimana membaca dan mengubah source Mermaid dalam repository.

## Kapan dipakai

Sequence diagram dipakai saat kita perlu melihat **siapa mengirim request, komponen apa yang memprosesnya, kapan data disimpan, serta kapan dan kepada siapa response dikirim**. Gunakan flowchart atau swimlane jika fokusnya urutan proses bisnis dan pembagian peran, bukan pertukaran pesan antarkomponen.

## Notasi Mermaid

| Notasi | Makna | Contoh penggunaan |
|---|---|---|
| `actor` | Manusia / peran | User, Staff, Approver |
| `participant` | Komponen / sistem | Frontend, Backend, Database |
| `->>` | Request atau message | Frontend mengirim submit request |
| `-->>` | Response, acknowledgment, callback message | Backend mengembalikan hasil |
| `alt` / `else` | Kondisi dan jalur alternatif | Approved atau Rejected |
| `opt` | Langkah opsional | Resend notification bila disepakati |
| `loop` | Perulangan yang punya batas/rule | Retry dengan ketentuan yang jelas |
| `Note over` | Konteks singkat | Callback terjadi asynchronous |

## Contoh A — Submit form

Source: [`sequence-submit-form.mmd`](../examples/diagrams/sequence-submit-form.mmd)

Alur ilustratif: User mengirim form, Backend melakukan validasi dan permission check, lalu menyimpan data. Untuk input salah, sistem menampilkan detail error. Jika database gagal, jangan klaim request tersimpan. Jika berhasil, tampilkan ID pengajuan.

## Contoh B — Approval

Source: [`sequence-approval.mmd`](../examples/diagrams/sequence-approval.mmd)

Alur ilustratif: Staff mengajukan request. Approver membuka detail, memilih Approve atau Reject. Aplikasi memeriksa permission dan status terbaru, serta meminta rejection reason saat menolak. Perubahan state harus disimpan sebelum response sukses diberikan.

## Contoh C — External API dan webhook

Source: [`sequence-external-webhook.mmd`](../examples/diagrams/sequence-external-webhook.mmd)

Tahap pertama: Backend membuat operation ID, memanggil External Service, dan memberi response sementara kepada Frontend. Response `202 Accepted` pada contoh **bukan** berarti business process selesai.

Tahap kedua: External Service mengirim webhook ke Webhook Handler. Handler memverifikasi signature dan event ID sebelum mengubah status operation. Callback yang sama dapat diterima lebih dari sekali, sehingga event duplikat harus ditangani dengan benar. HTTP response webhook hanya menandakan penerimaan callback sesuai kontrak, bukan menggantikan request awal.

## Cek diagram sebelum dipakai

- Participant sesuai arsitektur yang diketahui.
- Semua message berarah masuk akal. Frontend tidak langsung mengakses internal database kecuali memang dirancang begitu.
- Happy path dan error path penting terlihat.
- Data read/write menghasilkan perubahan status yang konsisten.
- `Request accepted` tidak disamakan dengan `business completed`.
- Webhook asynchronous berada di flow yang berbeda dari response sinkron.
- Detail endpoint, status HTTP, authentication, retry, dan idempotency dilabeli ilustrasi jika belum dikonfirmasi.
- Diagram bisa dibaca pada ukuran normal. Pecah diagram bila terlalu panjang.

## Cara menggunakan source di GitHub

GitHub mendukung render code block Mermaid dalam Markdown. Untuk preview cepat, salin isi `.mmd` ke code block `mermaid` pada file README atau dokumentasi modul. Simpan source `.mmd` agar tim bisa mengedit diagram tanpa menggambar ulang.

## Preview Mermaid lengkap

Seluruh flow berikut merupakan ilustrasi. Sesuaikan nama sistem, status, dan HTTP codes dengan requirement yang terverifikasi.

### 1. Submit form — validasi dan data tersimpan

```mermaid
sequenceDiagram
    autonumber
    actor U as User
    participant FE as Frontend
    participant API as Backend API
    participant DB as Database

    U->>FE: Isi form dan klik Submit
    rect rgb(239, 246, 255)
        FE->>API: POST /requests + payload
        API->>API: Validasi input dan permission
    end
    alt Data tidak valid
        API-->>FE: 422 + detail validasi
        FE-->>U: Tampilkan error pada field terkait
    else Data valid
        API->>DB: Insert pengajuan dengan status Draft
        alt Penyimpanan gagal
            DB-->>API: Database error
            API-->>FE: 500 + request reference
            FE-->>U: Tampilkan pesan gagal dan opsi ulang
        else Penyimpanan berhasil
            DB-->>API: Request ID
            rect rgb(240, 253, 244)
                API-->>FE: 201 Created + Request ID
                FE-->>U: Tampilkan nomor pengajuan
            end
        end
    end
```

### 2. Approval — approve, reject, permission

```mermaid
sequenceDiagram
    autonumber
    actor Staff as Staff
    participant App as Application
    participant DB as Database
    actor Appr as Approver

    Staff->>App: Submit request
    App->>App: Validasi data dan syarat pengajuan
    alt Data belum memenuhi syarat
        App-->>Staff: Tampilkan alasan pengajuan ditolak sistem
    else Data valid
        App->>DB: Simpan status Pending Approval
        DB-->>App: Request ID
        App-->>Staff: Submission berhasil
        Appr->>App: Buka detail request
        App->>DB: Ambil detail dan status terbaru
        DB-->>App: Detail request
        App-->>Appr: Tampilkan request
        Appr->>App: Approve atau Reject
        App->>App: Validasi permission dan status
        alt Tidak punya akses atau status berubah
            App-->>Appr: Action ditolak dan alasan ditampilkan
        else Approve
            App->>DB: Update status Approved dan approver
            DB-->>App: Update berhasil
            App-->>Appr: Tampilkan status Approved
        else Reject
            App->>App: Validasi rejection reason
            alt Alasan kosong
                App-->>Appr: Wajib isi rejection reason
            else Alasan tersedia
                App->>DB: Update status Rejected dan alasan
                DB-->>App: Update berhasil
                App-->>Appr: Tampilkan status Rejected
            end
        end
    end
```

### 3. Integrasi eksternal — request dan webhook asynchronous

```mermaid
sequenceDiagram
    autonumber
    actor U as User
    participant FE as Frontend
    participant BE as Backend
    participant DB as Database
    participant EXT as External Service
    participant WH as Webhook Handler

    U->>FE: Konfirmasi operasi
    FE->>BE: POST /operations
    BE->>DB: Simpan operasi status Pending
    DB-->>BE: Internal Operation ID
    rect rgb(239, 246, 255)
        BE->>EXT: POST operation + idempotency key
        alt Request diterima
            EXT-->>BE: 202 Accepted + External Reference
            BE->>DB: Simpan external reference
            BE-->>FE: 202 Pending + Operation ID
        else Timeout atau hasil belum pasti
            BE->>DB: Set status Verification Required
            BE-->>FE: Status masih menunggu verifikasi
        end
    end
    FE-->>U: Tampilkan status proses, bukan hasil final

    Note over EXT,WH: Tahap berikut berjalan asynchronous
    EXT->>WH: POST webhook status operasi
    WH->>WH: Verifikasi signature dan event ID
    alt Signature tidak valid
        WH-->>EXT: 401 Unauthorized
    else Event sudah diproses
        WH-->>EXT: 200 Acknowledged
    else Event valid dan baru
        WH->>DB: Simpan event dan update status secara atomik
        alt Update database gagal
            DB-->>WH: Error penyimpanan
            WH-->>EXT: Response gagal agar dapat di-retry
        else Update berhasil
            DB-->>WH: Status final tersimpan
            rect rgb(240, 253, 244)
                WH-->>EXT: 200 Acknowledged
            end
        end
    end
```
