## 💻 [TERMINAL] Install Oh My Posh di CMDER

Catatan untuk mempercantik tampilan terminal **CMDER** menggunakan Oh My Posh.

---

### 📌 Referensi

Ikuti langkah dari:
https://satheeshds.github.io/tech/2023/03/25/cmder-oh-my-posh-widows-terminal-vscode

---

### ⚙️ Konfigurasi Tambahan (Penting)

Setelah install selesai, tambahkan konfigurasi berikut di file:

```id="1b0j7f"
C:\laragon\bin\cmder\vendor\clink\clink.lua
```

---

### ✍️ Tambahkan Script Berikut

```lua id="m9t8j2"
load(io.popen('oh-my-posh init cmd --config "C:/Users/KangSseulgi/AppData/Local/Programs/oh-my-posh/themes/material.omp.json"'):read("*a"))()
```

---

### ❗ Catatan Penting

* Sesuaikan path:

  ```id="g7a3rf"
  C:/Users/KangSseulgi/
  ```

  dengan username Windows kamu

* Pastikan file theme ada:

  ```id="4h6c2x"
  material.omp.json
  ```

---

### ✅ Hasil yang Diharapkan

* Tampilan CMDER jadi lebih modern
* Ada informasi tambahan:

  * Git branch
  * Status repo
  * Path aktif
  * dll

---

### 🧠 Tips

* Kalau tidak berubah:

  * restart CMDER
* Kalau error:

  * cek path `oh-my-posh`
  * cek lokasi theme

---

### 🎯 Kesimpulan

* Install saja tidak cukup ❌
* Harus inject ke `clink.lua` ✅
* Path harus sesuai user masing-masing

---

**Note:**
Kalau prompt masih default, biasanya karena path config salah 😅

---
