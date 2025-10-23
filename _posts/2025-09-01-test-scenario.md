---
title: "TEST SCENARIO, TEST CASE, AND BUG REPORT"
date: 2025-09-01 08:00:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/test-scenario.png
---

## Definisi Singkat
### Test Scenario
Ringkasan skenario pengujian — *what* yang harus diuji. Contoh: “Periksa fungsi slider input berat dan tinggi badan.”

### Test Case
Langkah-langkah terperinci untuk menjalankan pengujian (precondition, test steps, test data, expected result, actual result, status).

### Bug Report
Laporan formal kesalahan yang menjelaskan: judul bug, langkah reproduksi, hasil aktual vs hasil yang diharapkan, severity, priority, dan informasi tambahan (build, environment, reporter).

---
## Template Sederhana — Test Scenario

| Field | Keterangan |
|---|---|
| ID Scenario | Nomor unik skenario (mis. TS001) |
| Deskripsi | Ringkasan skenario pengujian |
| Modul/Fitur | Modul atau fitur yang diuji |
| Catatan Tambahan | Pra-kondisi singkat atau dependensi |

---

## Template Sederhana — Test Case

| Field | Keterangan |
|---|---|
| ID Test Case | Nomor unik (mis. TC-001) |
| Deskripsi | Ringkasan singkat pengujian |
| Precondition | Kondisi awal sebelum pengujian |
| Test Steps | Langkah demi langkah pengujian |
| Test Data | Data yang digunakan |
| Expected Result | Hasil yang diharapkan |
| Actual Result | Hasil aktual (diisi saat eksekusi) |
| Status | Pass / Fail / Blocked |
| Remark | Catatan (screenshot, log) |

---

## Contoh: Test Scenario & Test Case untuk Aplikasi BMI
### Test Scenarios (contoh)
- **TS001** — Periksa fungsi slider input (berat & tinggi).  
- **TS002** — Periksa hasil perhitungan & klasifikasi BMI.  
- **TS003** — Periksa fungsi penyimpanan history BMI.

### Contoh Test Cases (dari studi kasus)

| ID | Deskripsi | Precondition | Test Steps | Test Data | Expected Result |
|---:|---|---|---|---|---|
| TC001 | Verifikasi slider input berat | Aplikasi terbuka | 1. Geser slider berat ke 60 kg. 2. Periksa label berat. | Slider = 60 kg | Label menampilkan "60 kg" |
| TC002 | Verifikasi slider input tinggi | Aplikasi terbuka | 1. Geser slider tinggi ke 170 cm. 2. Periksa label tinggi. | Slider = 170 cm | Label menampilkan "170 cm" |
| TC003 | Verifikasi perhitungan BMI | Aplikasi terbuka | 1. Masukkan tinggi 170 cm. 2. Masukkan berat 65 kg. 3. Klik "Hitung". | Tinggi=170, Berat=65 | BMI ≈ 22.49 (kg/m²) |
| TC008 | Verifikasi penyimpanan hasil BMI ke history | Aplikasi terbuka | 1. Hitung BMI, 2. Klik "Simpan History", 3. Buka halaman History. | Tinggi=170, Berat=65 | Data BMI terbaru muncul di halaman History |

---

## Bug Report — Format & Contoh
Gunakan format terstruktur agar developer bisa cepat mereproduksi dan memperbaiki bug.

### Format Bug Report (fields)
- **Bug Title**: Judul singkat & jelas.  
- **Bug ID**: Contoh `BMI-001`.  
- **Environment**: OS / Device / App version / Browser.  
- **Build number / Version**: Versi aplikasi.  
- **Reported on**: Tanggal.  
- **Reporter**: Nama/role.  
- **Severity**: Critical / Major / Minor / Low.  
- **Priority**: P1 (Urgent) / P2 (High) / P3 (Medium) / P4 (Low).  
- **Steps to Reproduce**: Langkah berurutan untuk mereproduksi bug.  
- **Test Data**: Data yang digunakan.  
- **Actual Result**: Hasil yang muncul saat pengujian.  
- **Expected Result**: Hasil yang seharusnya.  
- **Attachments**: Screenshot, log, video.  
- **Assignee**: Developer yang ditugaskan.  
- **Status**: Open / In Progress / Fixed / Verified / Closed.

### Contoh Bug Report (dari studi kasus)
- **Bug Title**: Perhitungan BMI salah saat input berat 60kg dan tinggi 170cm  
- **Bug ID**: BMI-001  
- **Environment**: Android (staging)  
- **Build number**: v1.0.0  
- **Reported on**: 31-08-2025  
- **Reporter**: SQA  
- **Severity**: Major (High)  
- **Priority**: P2 - High  
- **Steps to Reproduce**: 1. Buka aplikasi BMI. 2. Masukkan Berat = 60. 3. Masukkan Tinggi = 170. 4. Klik tombol “Hitung”.  
- **Actual Result**: Hasil BMI = 12.5  
- **Expected Result**: Hasil BMI seharusnya ≈ 20.8  
- **Attachments**: screenshot hasil perhitungan, device log.  
- **Assignee**: Developer  
- **Status**: Open

---

## Severity vs Priority — Penjelasan Singkat
- **Severity** (dampak bug terhadap sistem):  
  - *Critical*: Sistem crash / kehilangan data / fungsi utama tidak bekerja.  
  - *Major*: Fungsi penting tidak berjalan dengan benar (tidak crash).  
  - *Minor*: Gangguan fungsional yang tidak kritis (cosmetic atau edge-case).  
  - *Low*: Masalah kosmetik / typo.

- **Priority** (seberapa cepat bug harus diperbaiki):  
  - *P1 (Urgent/Critical)* — Perbaikan segera.  
  - *P2 (High)* — Perbaikan pada rilis berikutnya cepat.  
  - *P3 (Medium)* — Bisa di-schedule.  
  - *P4 (Low)* — Perbaikan tidak mendesak.

> Catatan: Severity ditentukan oleh QA berdasarkan dampak; Priority biasanya ditentukan oleh Product Owner atau manajer.

---

## Cara Menghindari Bug — Praktik Terbaik
1. **Pahami requirement** secara lengkap sebelum development.  
2. **Unit testing** untuk menangkap bug di tahap awal.  
3. **Code review** rutin antar rekan kerja.  
4. **Test plan dan test cases** komprehensif (termasuk negatif & edge cases).  
5. **Test automation** untuk regression (CI pipeline).  
6. **Continuous integration** dan smoke tests pada build baru.  
7. **Kolaborasi erat** antara developer, QA, dan product owner.  
8. **Logging & monitoring** untuk mendeteksi issue di lingkungan produksi.

---

## Contoh Checklist Saat Menemukan Bug
- [ ] Apakah bug bisa direproduksi konsisten?  
- [ ] Apakah ada log atau screenshot yang mendukung?  
- [ ] Sudahkah saya cek versi & environment?  
- [ ] Apakah ada test case yang terkait perlu diupdate?  
- [ ] Sudah dikomunikasikan ke developer & ditandai priority/severity?

---

## Referensi & Penutup
Ringkasan ini dibuat berdasarkan materi presentasi **Kelompok 4 — Test scenario, Test case and Bug report**. Gunakan template dan contoh di atas sebagai dasar untuk dokumentasi QA pada proyek Anda. Sesuaikan fields, format dan alur kerja dengan tool dan proses tim (mis. Jira, GitHub Issues, TestRail).

---
