# Natural Indonesian documentation — Anti-AI Slop

This guide contains Indonesian examples on purpose. It supports the [Indonesian skill](../skills/system-analysis-id/SKILL.md). The objective is **natural BA/SA working language**, not strict formal Indonesian and not a literal translation from English.

## How it should sound

Pakai Bahasa Indonesia yang biasa dipakai saat bikin BRD, Jira, MoM, atau technical documentation di tim kerja. Langsung jelasin masalah dan perubahan yang diminta. Enggak perlu kalimat pembuka yang panjang hanya supaya dokumen terdengar formal.

**Technical terms tetap English**, termasuk `API`, `endpoint`, `payload`, `request`, `response`, `validation`, `workflow`, `sequence diagram`, `database`, `query`, `approval`, `role`, `permission`, `submit`, `retry`, `timeout`, `webhook`, `callback`, `mapping`, `error handling`, `log`, `deployment`, `Business Rule`, dan `Acceptance Criteria`.

Kalau nama field di sistem `Customer Name`, jangan diganti menjadi "Nama Pelanggan". Kalau tombolnya `Submit`, tetap tulis `Submit`.

## Writing examples

| Context | Avoid | Prefer |
|---|---|---|
| Problem | Dalam rangka meningkatkan efektivitas pengelolaan data, diperlukan optimalisasi modul Inventory | Di modul Inventory, user belum bisa filter stok berdasarkan gudang. User harus buka detail item satu per satu untuk cek stok |
| Requirement | Sistem perlu mengakomodasi berbagai kebutuhan stakeholder | User dapat memilih warehouse dan sistem menampilkan stok untuk warehouse tersebut |
| Approval | Diperlukan mekanisme persetujuan yang terintegrasi | Saat request di-Submit, sistem menentukan approver berdasarkan role dan mengubah status menjadi Pending Approval |
| Validation | Proses validasi dilakukan secara menyeluruh | Kalau field Department kosong, sistem menolak Submit dan menampilkan error pada field tersebut |
| API | Sistem mengirim muatan permintaan ke titik akhir layanan dan menunggu panggilan balik | Backend mengirim payload ke endpoint external service. Status akhir diterima lewat webhook |
| Jira | Terdapat permasalahan yang berdampak pada pengalaman pengguna | Tombol Cancel menampilkan error ketika dokumen sudah memiliki referensi transaksi |
| MoM | Para pemangku kepentingan berkomitmen untuk memperkuat proses | Tim sepakat menambahkan filter warehouse. Default warehouse masih Need Confirmation |
| UAT | Sistem telah berjalan dengan hasil yang optimal | Saat Warehouse A dipilih, list hanya menampilkan item yang tersedia di Warehouse A |

Examples are hypothetical, not facts about a real project.

## Preferred writing patterns

**As-Is:** "Saat ini user belum bisa [aksi]. Akibatnya, [dampak yang memang terbukti]."

**To-Be:** "Saat user [aksi], sistem [validation/process], lalu [expected result]."

**Business Rule:** "Kalau [kondisi], sistem harus [behavior yang bisa dites]."

**Exception:** "Kalau [error], sistem [response atau status], lalu [recovery jika ada]."

**Need Confirmation:** "[Aturan] belum ditentukan. Dampaknya ada di [bagian proses]."

Jangan paksa pola yang sama di setiap paragraf. Yang penting jelas dan enggak terdengar kayak hasil translate.

## Expressions to avoid unless quoted from a source

- Dalam rangka
- Seiring dengan
- Guna mengakomodasi kebutuhan
- Lintas fungsi
- Antar pemangku kepentingan
- Efisiensi dan efektivitas
- Melalui pendekatan holistik
- Optimalisasi yang komprehensif
- Mewujudkan pengalaman seamless
- Menjamin keberlangsungan proses secara berkelanjutan
- Pada dasarnya
- Secara keseluruhan

## Final review

Sebelum kirim dokumen, cek apakah user bisa langsung memahami siapa yang melakukan action, kapan action bisa dijalankan, validasi apa yang berlaku, status apa yang berubah, dan apa yang terjadi kalau proses gagal.

Jangan mengarang rule hanya supaya flow terlihat lengkap. Pisahkan Existing, Confirmed, Proposed, dan Need Confirmation.

Tulisan boleh singkat, tapi jangan sampai requirement kehilangan precondition, permission, error handling, atau Acceptance Criteria.
