---
title: "TESTING PLAN"
date: 2025-09-01 07:30:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/testing-plan.png
---

## Introduction
**Test Plan** adalah dokumen yang menjelaskan bagaimana pengujian perangkat lunak akan dilaksanakan: ruang lingkup, strategi, sumber daya, jadwal, kriteria keberhasilan, dan deliverable. Dokumen ini menjadi acuan bagi tim QA, developer, dan pemangku kepentingan.

---

## Plan Identifier
- **ID Dokumen**: TP-<project>-v1.0  
- **Versi**: 1.0  
- **Tanggal**: 2025-10-20

---

## References
Daftar dokumen acuan: requirement specification, software design document, user stories, standar coding, SLA, dan dokumen terkait lain.

---

## Test Items
Daftar modul/fitur yang termasuk dalam ruang lingkup pengujian (contoh):
- Auth: Login, Logout, Password Reset
- Profile: View/Update profile
- Product: CRUD product
- Checkout: Cart, Payment Gateway integration
- API endpoints public/private

---

## Features to be Tested
Contoh fitur yang diuji:
- Fungsi otentikasi (login/logout)
- Validasi input form
- Alur checkout end-to-end
- Integrasi API pembayaran
- Responsivitas tampilan utama

---

## Features Not to be Tested
Fitur yang dikecualikan dan alasannya (contoh):
- Modul laporan legacy (dikecualikan karena tidak akan dirilis pada milestone ini)
- Integrasi pihak ketiga yang masih dalam PoC

---

## Software Risk Issues
Identifikasi risiko teknis dan fungsional:
- Requirement ambiguitas pada fitur X
- Ketergantungan pada API eksternal (potensi downtime)
- Modul baru dengan coverage rendah
- Potensi masalah performa pada puncak beban

Mitigasi: prioritas smoke test pada integrasi kritikal, monitoring, fallback plan.

---

## Approach (Pendekatan Pengujian)
- **Level**: Unit → Integration → System → Acceptance  
- **Metode**: Kombinasi manual + otomatisasi (CI pipeline)  
- **Tipe**: Black-box untuk acceptance & system; White-box untuk unit & coverage  
- **Alat**: (contoh) JUnit / PyTest, Selenium/Cypress untuk E2E, Postman / Newman untuk API, JMeter untuk performance, Jira untuk defect tracking

---

## Entry & Exit Criteria
**Entry Criteria** (untuk mulai eksekusi):
- Build kandidat tersedia dan dapat di-deploy ke environment test.
- Test cases utama telah ditulis dan ditinjau.
- Data uji tersedia.

**Exit Criteria** (untuk menutup testing cycle):
- Semua test case prioritas lulus atau ditangguhkan dengan alasan tertulis.
- Tidak ada defect critical/major terbuka tanpa rencana mitigasi.
- Test summary dan sign-off dari QA lead & product owner.

---

## Suspension Criteria & Resumption Requirements
**Suspension**: Pengujian dihentikan sementara jika build corrupt, data environment tidak konsisten, atau ditemukan defect blocking yang menghalangi pengujian lebih lanjut.  
**Resumption**: Pengujian dilanjutkan setelah issue di-fix dan build baru diverifikasi (smoke test) serta test data dikonfirmasi.

---

## Test Deliverables
Dokumen & artefak yang dihasilkan:
- Test Plan (ini)
- Test Cases dan Test Scripts
- Test Data
- Hasil Eksekusi (Test Execution Report)
- Defect / Bug Reports
- Test Summary Report & Recommendation
- Automation scripts (repository)

---

## Remaining Test Tasks
Daftar tugas yang belum selesai (contoh format):
- Penulisan test case untuk modul X
- Implementasi test automation untuk payment flow
- Setup load testing scenario

---

## Environment & Tools
Spesifikasi environment tes:
- Hardware / VM / Container images
- OS & versi (ex: Ubuntu 22.04, Windows 10)
- Database & versi
- API endpoints (staging)
- Tools: CI (GitHub Actions/GitLab CI), test frameworks (PyTest/JUnit), test runner, test management

---

## Responsibilities (Peran & Tanggung Jawab)
- **Test Manager**: Koordinasi plan & approval  
- **QA Engineers**: Menulis/mengeksekusi test case, laporan bug  
- **Developers**: Memperbaiki defect, membuat build  
- **DevOps**: Menyediakan environment & build pipeline  
- **Product Owner / Stakeholder**: Approval release

---

## Staffing and Training Needs
Kebutuhan personel & pelatihan singkat (jika perlu):
- Onboarding untuk tool baru (contoh: Cypress workshop)
- Cross-training antara QA & dev untuk automation

---

## Schedule (Milestone)
Contoh garis waktu singkat:
- Test Plan review: 2025-10-21
- Penulisan test case: 2025-10-22 → 2025-10-25
- Setup environment & data: 2025-10-24
- Eksekusi test: 2025-10-26 → 2025-11-02
- Regression & retest: 2025-11-03 → 2025-11-06
- Test closure & sign-off: 2025-11-07

(Ubah tanggal sesuai kebutuhan proyekmu)

---

## Glossary
Beberapa istilah penting:
- **Test Item**: Komponen / modul yang diuji  
- **Test Case**: Deskripsi langkah pengujian dan hasil yang diharapkan  
- **Pass/Fail Criteria**: Kriteria lulus/gagal test case  
- **Build**: Versi aplikasi yang diuji

---

## Approvals
Tanda tangan / konfirmasi dari stakeholder utama:
- QA Lead: ___________________  Date: ______  
- Product Owner: ___________________  Date: ______  
- Development Lead: ___________________  Date: ______

---

## Contoh Template Singkat Test Case (Markdown table)

| ID     | Modul       | Deskripsi singkat               | Preconditions     | Langkah (Test Steps)                                | Expected Result                 | Priority |
|--------|-------------|---------------------------------|-------------------|-----------------------------------------------------|----------------------------------|----------|
| TC-001 | Auth        | Login berhasil dengan credential valid | User terdaftar | 1. Buka halaman login 2. Masukkan user+pwd 3. Klik Login | Redirect ke dashboard & status 200 | High     |
| TC-002 | Checkout    | Pembayaran sukses (sandbox)     | Produk ada di cart | 1. Checkout 2. Pilih metode sandbox 3. Submit payment | Status transaksi = success       | Critical |

---

## Metrik yang Disarankan
- **Test Execution Rate** (% executed)  
- **Pass Rate** (% passed)  
- **Defect Density** (defect / module)  
- **MTTD / MTTR** (mean time to detect / repair)  
- **Coverage** (test case coverage atau code coverage untuk unit tests)

---

## Kesimpulan & Rekomendasi
Test Plan yang baik mengikat ruang lingkup, strategi, kebutuhan sumber daya, dan kriteria evaluasi secara jelas. Gunakan dokumen ini sebagai living document: perbarui ketika requirement berubah, dan jadikan alat komunikasi utama antara QA, dev, dan stakeholder.

---

## Referensi
Materi ini diringkas dari presentasi **Kelompok 3 — Test Plan** (Fakultas Sistem Informasi).

---