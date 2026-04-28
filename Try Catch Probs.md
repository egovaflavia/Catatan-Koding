## ⚠️ Try Catch Probs

Catatan kecil tapi penting saat menggunakan `try-catch` di Laravel / PHP.

---

### ❌ Masalah yang Sering Terjadi

Urutan `catch` salah, sehingga error spesifik tidak pernah tertangkap.

Contoh salah:

```php id="k3x9dz"
try {
    // query database
} catch (Exception $e) {
    // ini terlalu umum
} catch (QueryException $e) {
    // tidak akan pernah dieksekusi
}
```

**Kenapa salah?**

* `Exception` adalah parent class
* Semua error (termasuk QueryException) sudah ditangkap duluan

---

### ✅ Cara yang Benar

Letakkan `QueryException` di atas:

```php id="c2m1ab"
try {
    // query database
} catch (QueryException $e) {
    // khusus error database
} catch (Exception $e) {
    // error umum
}
```

---

### 🧠 Penjelasan

* `QueryException` = error dari database (koneksi, query gagal, dll)
* `Exception` = semua jenis error umum

👉 Jadi:

* Yang **lebih spesifik harus di atas**
* Yang **lebih umum di bawah**

---

### 📌 Studi Kasus

Misalnya:

* koneksi DB putus
* query salah syntax

Kalau urutan salah:

* error langsung masuk ke `Exception`
* kamu kehilangan detail error database

---

### 💡 Tips

* Selalu urutkan dari **spesifik → umum**
* Gunakan `QueryException` untuk handling database
* Gunakan `Exception` sebagai fallback

---

### 🎯 Kesimpulan

Urutan `catch` itu penting:

```id="c9y1lw"
QueryException → Exception
```

Kalau kebalik:

* logic error
* debugging jadi susah
* handling tidak optimal

---

**Note:**
Kalau `catch` tidak pernah jalan, kemungkinan besar urutannya salah 😅

---
