---
title: "PENGANTAR SELENIUM WEB DRIVER"
date: 2025-09-14 07:30:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/pengantar-selenium.png
---

##  Pengertian Selenium
*Selenium* adalah framework open-source yang digunakan untuk mengotomatisasi pengujian aplikasi web di berbagai browser (Chrome, Firefox, Edge, Safari).  
Dengan Selenium, tester dapat menjalankan skenario UI secara otomatis tanpa harus melakukannya secara manual.

---

##  Komponen Utama Selenium

| Komponen | Deskripsi |
|-----------|------------|
| *Selenium IDE* | Alat berbasis browser untuk merekam dan memutar ulang langkah pengujian. |
| *Selenium WebDriver* | API utama untuk mengontrol browser secara langsung melalui kode (Python, Java, JS, dll). |
| *Selenium Grid* | Menjalankan tes di beberapa browser, OS, dan perangkat secara paralel. |
| *Selenium RC (Deprecated)* | Versi lama Selenium sebelum WebDriver (tidak lagi digunakan). |

---



## Bahasa dan Browser yang Didukung
- Bahasa: Java, Python, C#, Ruby, JavaScript, PHP  
- Browser: Chrome, Firefox, Edge, Safari, Opera  
- Platform: Windows, macOS, Linux  

---

##  Contoh Kode Selenium (Python)
python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
import time

# Inisialisasi driver
driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()))

# Buka halaman web
driver.get("https://www.saucedemo.com/")
driver.maximize_window()

# Input username dan password
driver.find_element(By.ID, "user-name").send_keys("standard_user")
driver.find_element(By.ID, "password").send_keys("secret_sauce")

# Klik tombol login
driver.find_element(By.ID, "login-button").click()

# Tunggu beberapa detik
time.sleep(3)

# Verifikasi judul halaman setelah login
assert "Swag Labs" in driver.title

# Tutup browser
driver.quit()

---
## Penjelasan Kode
- webdriver.Chrome() membuka browser otomatis.
- find_element(By.ID, "login-button") mencari elemen tombol login.
- click() dan send_keys() digunakan untuk berinteraksi dengan UI.
- assert memastikan hasil sesuai ekspektasi.

---

### Contoh Test Case Selenium

| ID | Deskripsi | Langkah | Expected Result | Status |
|----|------------|----------|----------------|--------|
| *SEL-001* | Login valid | 1. Buka web <br> 2. Isi username dan password <br> 3. Klik *Login* | Halaman *dashboard* muncul | ✅ Pass |
| *SEL-002* | Login gagal (password salah) | 1. Isi password salah <br> 2. Klik *Login* | Pesan error *“Invalid password”* tampil | ✅ Pass |
| *SEL-003* | Cek tombol logout | 1. Login ke aplikasi <br> 2. Klik menu *Logout* | User kembali ke *halaman login* | ✅ Pass |

---

## Kesimpulan
Selenium membantu QA melakukan pengujian web secara otomatis dan efisien.
Dengan integrasi framework yang tepat, Selenium dapat meningkatkan kecepatan dan kualitas proses testing, terutama pada aplikasi berbasis web yang terus berkembang.
---