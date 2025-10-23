---
title: "PENGANTAR UNIT TESTING"
date: 2025-09-07 07:30:00
categories: [Software Testing and Quality Assurance]
tags: [STQA]
image: /assets/images/pengantar-unit-testing.png
---


# Unit Testing — Ringkasan Praktis
Ringkasan ini berasal dari materi *Kelompok 5, membahas tentang **Unit Testing* sebagai salah satu tahap penting dalam Software Testing Life Cycle (STLC).  
Unit testing dilakukan oleh developer untuk memastikan setiap fungsi kecil dari program bekerja dengan benar.

---

## Pengertian Unit Testing
*Unit Testing* adalah proses pengujian terhadap unit terkecil dari kode program — biasanya berupa *fungsi, prosedur, atau class* — untuk memastikan bagian tersebut berjalan sesuai harapan.

*Tujuan utama:*  
- Menemukan bug sejak tahap awal pengembangan.  
- Memastikan setiap unit berfungsi secara individual.  
- Memudahkan maintenance dan refactoring.  
- Meningkatkan keandalan sistem secara keseluruhan.

---

## Ciri-ciri Unit Testing yang Baik
- Dapat dijalankan *secara otomatis*.  
- Bersifat *independen* dari modul lain.  
- Menghasilkan hasil *pass/fail* yang jelas.  
- Cepat dieksekusi dan mudah direproduksi.

---

## Tools Umum untuk Unit Testing

| Bahasa Pemrograman | Framework / Tools |
|--------------------|-------------------|
| Java | JUnit, TestNG |
| Python | unittest, pytest |
| JavaScript | Jest, Mocha, Jasmine |
| PHP | PHPUnit |
| C# | MSTest, xUnit, NUnit |

---

## Struktur Umum Unit Test
Biasanya unit test terdiri dari tiga tahap utama (AAA Pattern):

1. *Arrange* — siapkan data, objek, atau kondisi awal.  
2. *Act* — panggil fungsi atau metode yang akan diuji.  
3. *Assert* — periksa apakah hasil yang diperoleh sesuai dengan yang diharapkan.

Contoh struktur sederhana:

python
def test_addition():

    # Arrange
    a, b = 2, 3

    # Act
    result = a + b

    # Assert
    assert result == 5


## Contoh Unit Testing Sederhana (Python)
python
import unittest

def add(a, b):
    return a + b

class TestMath(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)

if __name__ == '__main__':
    unittest.main()


hasil
python
----------------------------------------------------------------------
Ran 1 test in 0.001s
OK


## Kesimpulan
Unit Testing adalah fondasi awal dari kualitas perangkat lunak.
Dengan menulis dan menjalankan unit test secara konsisten, developer dapat:
- Mendeteksi bug lebih cepat,
- Mengurangi biaya perbaikan, dan
- Meningkatkan stabilitas sistem dalam jangka panjang.
