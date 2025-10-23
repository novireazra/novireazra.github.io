---
title: "STRATEGI TESTING"
date: 2025-08-25 07:30:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/strategi-testing.png
---


# Testing Strategy (Strategi Pengujian)
Ringkasan singkat materi dari **Kelompok 1** mengenai strategi pengujian perangkat lunak (Software Testing Strategy). Dokumen ini merangkum konsep kunci: tujuan testing, Software Testing Life Cycle (STLC), tingkatan dan klasifikasi pengujian, serta langkah-langkah perencanaan dan pelaporan pengujian.

---

## Tujuan Testing
- Menemukan cacat (bug) dalam perangkat lunak.
- Memastikan perangkat lunak bekerja sesuai kebutuhan (verifikasi & validasi).
- Mengurangi risiko kegagalan saat rilis.
- Meningkatkan kepercayaan stakeholder dan kualitas pengalaman pengguna.
- Menjamin aspek non-fungsional seperti performa dan keamanan.

---

## Software Testing Life Cycle (STLC) — Gambaran Umum
STLC adalah alur terstruktur untuk aktivitas pengujian dalam SDLC. Fase utama biasanya meliputi:
1. **Perencanaan (Planning)**  
   - Menentukan scope, strategi, estimasi waktu & biaya, peran & tanggung jawab.
2. **Design (Desain Test)**  
   - Menyusun test case, test data, dan skenario pengujian.
3. **Set-up Environment**  
   - Menyiapkan environment (hardware, software, versi, data uji).
4. **Execution (Eksekusi)**  
   - Menjalankan test case, mencatat actual result, dan melaporkan defect.
5. **Reporting & Analysis**  
   - Membuat test summary, metrik, rekomendasi perbaikan.
6. **Closure**  
   - Menyelesaikan deliverables, sign-off, dan dokumentasi akhir.

---

## Tingkatan Pengujian (By Abstraction / Level)
1. **Unit Testing**  
   - Menguji unit terkecil (fungsi, method, kelas). Biasanya dilakukan developer.
2. **Integration Testing**  
   - Menguji interaksi antar modul/subsystem.
3. **System / End-to-End Testing**  
   - Menguji sistem secara keseluruhan terhadap requirement fungsional & non-fungsional.
4. **Acceptance Testing**  
   - Pengujian oleh pengguna/klien untuk memutuskan penerimaan produk.

---

## Klasifikasi Pengujian (Berdasarkan Tujuan)
- **Functional Testing** — Memverifikasi fungsi sesuai requirement (login, transaksi, dll).
- **Non-Functional Testing** — Meliputi performa, keamanan, reliabilitas, skalabilitas, usability.

---

## Jenis Pengujian Domain (Contoh)
- **Performance Testing** — load, stress, soak.
- **Security Testing** — penanganan ancaman, injection, authentication.
- **Usability Testing** — kemudahan penggunaan untuk end-user.
- **Compatibility / Cross-browser Testing** — multi-browser, multi-device.

---

## Berdasarkan Struktur (Testing Approach)
- **Black-box testing**  
  - Fokus pada input/output & fungsi tanpa melihat kode. Cocok untuk pengujian fungsional dan acceptance.
  - Kelebihan: tidak butuh pengetahuan internal kode; sesuai perspektif user.
  - Kekurangan: tidak jamin semua jalur kode teruji.
- **White-box testing**  
  - Tester mengetahui struktur internal dan menulis tes berdasarkan alur kode (coverage-driven).
  - Kelebihan: dapat menemukan bug tersembunyi di logika internal.
  - Kekurangan: butuh pengetahuan mendalam terhadap kode; memakan waktu.

---

## Aktivitas Perencanaan Testing (Praktis)
- Identifikasi **test items** (fitur/komponen yang diuji).
- Tentukan **features to be tested** & **features not to be tested**.
- Pilih **approach**: manual vs otomatis, black-box vs white-box.
- Tentukan **entry / exit criteria** (pass/fail criteria).
- Siapkan **environment** & kebutuhan data.
- Tetapkan **deliverables**: test plan, test cases, test reports, bug reports.
- Buat jadwal (milestone, retest, regression window).
- Penentuan peran & jalur eskalasi (responsibilities & approvals).

---

## Kriteria Lulus / Gagal (Contoh)
- **Pass Criteria**
  - Semua test case utama lulus.
  - Tidak ada defect kritis yang belum diperbaiki.
- **Fail Criteria**
  - Terdapat defect kritis/major yang menghalangi fungsionalitas inti.
  - Jumlah failure melebihi threshold yang ditetapkan.

---

## Pelaporan & Analisis Testing
Elemen yang biasa dilaporkan:
- Ringkasan eksekusi: jumlah test case (pass/fail/not run).
- Daftar defect: severity, priority, status, assignee.
- Trend chart: defect discovery over time, pass rate trend.
- Rekomendasi perbaikan & risk assessment.
- Remaining tasks sebelum sign-off.

---

## Contoh Template Ringkas Test Case (Markdown table)

| ID     | Deskripsi singkat            | Precondition      | Langkah pengujian (Test Steps)                 | Test Data             | Expected Result                     | Status |
|--------|------------------------------|-------------------|------------------------------------------------|-----------------------|-------------------------------------|--------|
| TC-001 | Verifikasi login sukses      | Aplikasi terbuka  | 1. Masuk ke halaman login. 2. Masukkan creds.  | user=alice / pwd=123  | Bisa masuk ke dashboard             | Pass   |
| TC-002 | Verifikasi login gagal       | Aplikasi terbuka  | 1. Masuk ke halaman login. 2. Masukkan creds.  | user=alice / pwd=000  | Muncul pesan error "invalid creds"  | Fail   |

> Kamu bisa mengembangkan tabel di atas menjadi CSV atau spreadsheet untuk manajemen test lebih lanjut.

---

## Contoh Metrik yang Berguna
- **Test Execution Rate** = (Jumlah Test Case yang dieksekusi / Total Test Case) × 100%
- **Pass Rate** = (Jumlah Test Case Lulus / Total Dieksekusi) × 100%
- **Defect Density** = Jumlah Defect / Size (mis. per 1.000 baris kode atau per modul)
- **Mean Time To Detect (MTTD)** dan **Mean Time To Repair (MTTR)** untuk defect lifecycle

---

## Contoh Checklist Singkat Sebelum Release
- [ ] Semua critical/major defect sudah diperbaiki & diverifikasi.
- [ ] Build yang diuji cocok dengan build release.
- [ ] Smoke test basic flows lulus.
- [ ] Backup & rollback plan tersedia.
- [ ] Approval dari product owner / QA manager diperoleh.

---

## Kesimpulan
Strategi testing yang baik adalah kombinasi dari perencanaan matang (testing plan), desain test case yang benar, eksekusi terukur, serta pelaporan yang jelas. Pilih kombinasi level pengujian dan metode (manual/otomasi, black/white-box) sesuai risiko dan kebutuhan proyek.

---

## Referensi
Materi ringkasan ini berdasarkan presentasi **Kelompok 1 — Testing Strategy**, Fakultas Sistem Informasi.

---
