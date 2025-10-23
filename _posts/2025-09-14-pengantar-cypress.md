---
title: "PENGANTAR CYPRESS"
date: 2025-09-14 08:00:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/pengantar-cypress.png
---

## Pengantar  
*Cypress* adalah framework *end-to-end testing* untuk aplikasi web modern seperti *React, **Vue, dan **Angular*.  
Framework ini dirancang agar pengujian berjalan cepat, stabil, dan mudah diintegrasikan dengan proses pengembangan modern.  

### Posisi Cypress dalam Pengujian:
Cypress dapat digunakan untuk tiga jenis pengujian utama:
- *Unit Testing*
- *Integration Testing*
- *End-to-End Testing*  

Meskipun fokus utamanya adalah end-to-end testing, Cypress juga mendukung *integration* dan *component testing*, sehingga fleksibel untuk berbagai kebutuhan QA.

---

## Instalasi Cypress  

### Syarat Utama  
- *Node.js* harus sudah terpasang di komputer.  

### Langkah Instalasi  
1. Inisialisasi proyek Node.js:  
   bash
   npm init -y
   
2. Instal Cypress sebagai development dependency:  
   bash
   npm install cypress --save-dev
   
3. Jalankan Cypress GUI (test runner):  
   bash
   npx cypress open
   
4. Jalankan Cypress melalui browser tertentu:  
   bash
   npx cypress run --browser chrome
   npx cypress run --browser firefox
   npx cypress run --browser edge
   

---

## Perintah Dasar Cypress  

Cypress menggunakan sintaks yang sederhana dan mudah dibaca, mirip dengan bahasa alami.  

### 1. Membuka Halaman Web  
javascript
cy.visit('https://example.com')


### 2. Mengambil Elemen Berdasarkan Selector  
javascript
cy.get('input[name="username"]')


### 3. Mengetik ke Input Field  
javascript
cy.get('input[name="username"]').type('standard_user')


### 4. Klik Tombol atau Link  
javascript
cy.get('button[type="submit"]').click()


### 5. Mencari Elemen Berdasarkan Teks  
javascript
cy.contains('Login')


### 6. Mengecek URL Aktif  
javascript
cy.url().should('include', '/dashboard')


---

## Keunggulan Cypress  

1. *Arsitektur Modern* — Berjalan langsung di browser menggunakan JavaScript.  
2. *Test Runner Interaktif* — Menampilkan setiap langkah pengujian secara visual.  
3. *Time Travel* — Menyimpan snapshot tiap langkah pengujian.  
4. *Automatic Waits* — Tidak perlu menulis wait manual.  
5. *Real-Time Reloads* — Tes otomatis dijalankan ulang setelah perubahan skrip.  

---

## Perbandingan dengan Selenium dan Playwright  

- *Bahasa:* Cypress (JavaScript), Selenium (multi-bahasa), Playwright (JS, Python, C#).  
- *Fokus:* Cypress → E2E modern web, Selenium → cross-browser klasik, Playwright → multi-browser modern.  
- *Setup:* Cypress mudah, Selenium kompleks, Playwright sedang.  
- *Wait otomatis:* Ya di Cypress dan Playwright.  
- *GUI interaktif:* Hanya Cypress.  

Cypress unggul karena kemudahan, GUI visual, dan stabilitas tinggi.  

---

## Studi Kasus — Login di SauceDemo  

### Tujuan  
Menguji login di situs [saucedemo.com](https://www.saucedemo.com).  

### Langkah Pengujian:  
1. Buka halaman utama.  
2. Isi username dan password.  
3. Klik tombol *Login*.  
4. Verifikasi hasil login.  

### Contoh Skrip Cypress:  
javascript
describe('Login Test', () => {
  it('Login berhasil di SauceDemo', () => {
    cy.visit('https://www.saucedemo.com')
    cy.get('#user-name').type('standard_user')
    cy.get('#password').type('secret_sauce')
    cy.get('#login-button').click()
    cy.url().should('include', '/inventory.html')
  })
})


---

## Kesimpulan  
*Cypress* adalah framework modern yang efisien untuk pengujian aplikasi web.  
Dengan fitur interaktif seperti *Test Runner, **Time Travel, dan **Automatic Waits*, Cypress membantu QA melakukan pengujian cepat dan akurat.  

> *Kesimpulan akhir:* Cypress adalah alat ideal untuk meningkatkan *kualitas, **stabilitas, dan **kecepatan pengujian aplikasi web* modern.  

---

