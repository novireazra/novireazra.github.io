---
title: "UI/UX TESTING"
date: 2025-08-25 08:00:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/ui-ux-testing.png
---


## Perbedaan mendasar: UI vs UX Testing
- **UI Testing** — fokus pada tampilan visual dan elemen antarmuka: warna, ikon, ukuran tombol, layout, responsivitas, konsistensi across screens/browsers.
- **UX Testing** — fokus pada pengalaman pengguna secara keseluruhan: kemudahan menyelesaikan tugas, kepuasan pengguna, alur (flow), kegunaan (usability), dan aksesibilitas.

Singkat: *UI = bagaimana tampilannya; UX = bagaimana rasanya digunakan.*

---

## Fokus & Contoh Pengujian UI
- **Konsistensi visual**: warna, font, ikon, ukuran tombol.  
  Contoh: pastikan tombol “Login” sama di halaman A dan B.
- **Responsivitas**: layout adaptif pada berbagai ukuran layar (mobile, tablet, desktop).  
  Contoh: menu tidak menumpuk pada layar 5".
- **Kompatibilitas**: cross-browser & cross-platform.  
  Contoh: animasi berjalan sama di Chrome, Firefox, Safari, Edge.

**Teknik pengujian UI**: checklist manual, automated visual regression (Percy, Applitools), cross-browser testing (BrowserStack, LambdaTest).

---

## Fokus & Alur Kerja UX Testing
Alur umum UX testing (iteratif):
1. Rencana & tujuan (apa yang ingin diuji / KPI)  
2. Rekrut peserta / representative users  
3. Desain tugas (task scenarios) dan KPI (task success, time on task)  
4. Pelaksanaan (moderated / unmoderated, remote / in-person)  
5. Pengumpulan data & observasi (video, heatmap, think-aloud)  
6. Analisis & rekomendasi desain → iterasi

Contoh metode: Usability testing (lab/remote), A/B testing, tree testing, card sorting, session recording & heatmaps (Hotjar, Microsoft Clarity).

---

## Aksesibilitas (Accessibility Testing)
Pastikan aplikasi dapat dipakai oleh semua orang (WCAG guidelines):
- **Kontras warna** (WCAG AA/AAA), ukuran teks, dan skalabilitas.
- **Navigasi keyboard**: semua kontrol dapat diakses tanpa mouse.
- **Screen reader support**: label ARIA, ordered heading structure.
- **Form feedback & error handling**: pesan jelas dan solusinya.
Tools bantu: Lighthouse, axe, WAVE.

Contoh pemeriksaan cepat:
- Ratio kontras teks ≥ 4.5:1 untuk teks normal.
- Semua tombol fokus terlihat saat navigasi keyboard.
- Gambar penting memiliki atribut `alt`.

---

## Heuristic Evaluation — Prinsip Singkat (Nielsen)
1. **Visibility of system status** — system harus memberi feedback.  
2. **Match between system and real world** — gunakan bahasa familiar.  
3. **User control & freedom** — sediakan undo/exit.  
4. **Consistency & standards** — elemen seragam di seluruh UI.  
5. **Error prevention** — hindari kesalahan dengan desain.  
6. **Recognition rather than recall** — buat opsi terlihat.  
7. **Flexibility & efficiency** — shortcuts untuk pengguna mahir.  
8. **Aesthetic & minimalist design** — hindari info berlebih.  
9. **Help users recognize & recover from errors** — pesan solusi.  
10. **Help & documentation** — mudah diakses dan fokus tugas.

---

## Tools & Teknik Populer
- **Visual regression / UI**: Applitools, Percy  
- **Cross-browser / Device**: BrowserStack, LambdaTest, Responsively App  
- **Analytics & Heatmaps**: Hotjar, Crazy Egg, Microsoft Clarity  
- **Prototyping & Design Handoff**: Figma, Zeplin, Sketch  
- **Usability testing & prototypes**: Maze, UserTesting  
- **Accessibility**: Lighthouse, axe (browser extension), WAVE

---

## Checklist UI/UX sebelum release (singkat)
- [ ] Konsistensi visual antar halaman sudah dicek.  
- [ ] Semua flow kritis (signup, payment, search) diuji end-to-end.  
- [ ] Responsivitas diuji pada 3+ breakpoint (mobile, tablet, desktop).  
- [ ] Cross-browser: tes pada Chrome, Firefox, Safari, Edge.  
- [ ] Usability test: minimal 5–10 pengguna untuk validasi awal.  
- [ ] Accessibility basic: kontras, keyboard nav, ARIA labels.  
- [ ] Heatmap/analytics setup untuk 2 minggu setelah release.  
- [ ] Recovery plan & rollback bila ada regressions besar.

---

## 📋 Contoh Test Case UI/UX (Markdown table)

| ID      | Jenis       | Deskripsi singkat                        | Precondition            | Langkah Pengujian (Test Steps)                                                                 | Test Data / Perangkat         | Expected Result                                      |
|---------|-------------|------------------------------------------|-------------------------|-----------------------------------------------------------------------------------------------|-------------------------------|------------------------------------------------------|
| UI-001  | UI          | Tombol Login konsisten di semua halaman  | App terpasang & terbuka | 1. Buka halaman A → periksa tombol Login. 2. Buka halaman B → periksa tombol Login.           | Desktop (1366x768), Chrome    | Warna, teks, ukuran & posisi tombol sama di kedua halaman |
| UX-001  | Usability   | Pengguna dapat checkout dalam 3 langkah  | Akun & produk tersedia  | 1. Login 2. Tambah produk ke cart 3. Checkout → isi alamat & bayar                           | Mobile 360x800                | Pengguna menyelesaikan checkout < 5 menit tanpa kesalahan |
| ACC-001 | Accessibility| Keyboard navigation pada form registrasi | Halaman registrasi      | 1. Tab dari field pertama → pastikan fokus berpindah logis ke field berikutnya. 2. Submit form | Desktop, NVDA / VoiceOver     | Semua control dapat diakses via keyboard; screen reader membaca label |
| UI-002  | Responsiveness| Layout tidak overlap pada 5" screen     | Halaman home            | 1. Buka home pada 320x568 viewport 2. Periksa teks & tombol apakah readable/klikable         | Mobile 320x568                | Tidak ada elemen overlap; tombol dapat diklik         |

> Kamu bisa ekspor tabel ini ke CSV/Excel untuk manajemen QA lebih lanjut.

---

## KPI / Metrik UX yang Sering Digunakan
- **Task success rate** (persentase tugas terselesaikan)  
- **Time on task** (waktu rata-rata menyelesaikan tugas)  
- **Error rate** (frekuensi kesalahan pengguna)  
- **System Usability Scale (SUS)** — skor subjektif usability  
- **Net Promoter Score (NPS)** / Satisfaction rating

---

## Tips Praktis untuk Integrasi UI/UX Testing dalam SDLC
- Mulai sejak fase desain: lakukan prototype testing lebih awal (shift-left).  
- Kombinasikan qualitative (user interview) + quantitative (analytics) data.  
- Otomasi visual regression untuk mencegah regresi tampilan.  
- Jadwalkan sesi usability setelah setiap major redesign.  
- Libatkan PM & developer saat menemukan isu UX penting—bukan hanya designer.

---

## Kesimpulan
UI testing dan UX testing saling melengkapi: UI memastikan tampilan dan fungsionalitas elemen antarmuka benar, sedangkan UX memastikan pengguna dapat mencapai tujuan mereka dengan mudah, cepat, dan menyenangkan. Pendekatan yang baik menggabungkan testing manual, otomatisasi visual, metrik pengguna nyata, dan pengecekan aksesibilitas untuk menghasilkan pengalaman yang inklusif dan andal.

---

## Referensi
Materi ringkasan ini berdasarkan presentasi **Kelompok 2 — UI/UX Testing**, Fakultas Sistem Informasi.

---
