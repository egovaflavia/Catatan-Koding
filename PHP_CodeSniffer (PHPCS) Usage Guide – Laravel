# PHP_CodeSniffer (PHPCS) Usage Guide – Laravel

Dokumentasi ini menjelaskan cara menggunakan **PHP_CodeSniffer (PHPCS)** untuk melakukan pengecekan dan perapihan kode pada folder `Modules/SPM` di project Laravel.

---

## 📦 Requirement

* PHP 7.4
* Composer
* PHPCS sudah terinstall

Install PHPCS jika belum:

```bash
composer require --dev squizlabs/php_codesniffer
```

---

## 📁 Struktur yang digunakan

Target folder:

```
Modules/SPM
```

---

## 🚀 Menjalankan PHPCS (Check Code)

Untuk mengecek kode:

```bash
vendor\bin\phpcs.bat Modules/SPM
```

Menggunakan standar PSR-12:

```bash
vendor\bin\phpcs.bat --standard=PSR12 Modules/SPM
```

---

## 🧹 Auto Fix Code (phpcbf)

Untuk memperbaiki kode secara otomatis:

```bash
vendor\bin\phpcbf.bat Modules/SPM
```

---

## ⚙️ Konfigurasi (phpcs.xml)

Agar tidak perlu menulis command panjang, buat file `phpcs.xml` di root project:

```xml
<?xml version="1.0"?>
<ruleset name="Modules SPM Standard">
    <rule ref="PSR12"/>

    <!-- Target folder -->
    <file>Modules/SPM</file>

    <!-- Exclude folder -->
    <exclude-pattern>vendor/*</exclude-pattern>
    <exclude-pattern>storage/*</exclude-pattern>
    <exclude-pattern>bootstrap/cache/*</exclude-pattern>
</ruleset>
```

Setelah itu cukup jalankan:

```bash
vendor\bin\phpcs.bat
```

---

## 🔁 Composer Script (Opsional)

Tambahkan ke `composer.json`:

```json
"scripts": {
    "lint": "phpcs Modules/SPM",
    "lint-fix": "phpcbf Modules/SPM"
}
```

Jalankan dengan:

```bash
composer lint
composer lint-fix
```

---

## 💻 Penggunaan di Windows

Gunakan `.bat`:

```
vendor\bin\phpcs.bat
vendor\bin\phpcbf.bat
```

---

## 🔄 Workflow Rekomendasi

1. Menulis kode
2. Jalankan auto fix:

   ```bash
   composer lint-fix
   ```
3. Cek ulang:

   ```bash
   composer lint
   ```

---

## 🧠 Tips

* Gunakan standar **PSR-12** untuk konsistensi kode
* Jalankan lint sebelum commit
* Gunakan auto-fix untuk menghemat waktu

---

## 📌 Catatan

* PHPCS hanya mendeteksi masalah style, bukan bug logika
* Gunakan tools tambahan seperti PHPStan jika dibutuhkan

---

## 🎯 Kesimpulan

Dengan PHPCS:

* Kode lebih rapi
* Konsisten antar developer
* Lebih mudah di-maintain

---
