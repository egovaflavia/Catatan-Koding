## 🔢 Iterasi jika menggunakan Paginate

Digunakan untuk membuat nomor urut yang **tidak reset** saat menggunakan pagination di Laravel.

---

### ❌ Masalah yang Sering Terjadi

Saat menggunakan pagination (`paginate()`), nomor urut akan selalu mulai dari 1 di setiap halaman.

Contoh:

* Halaman 1 → 1, 2, 3, 4, 5
* Halaman 2 → 1, 2, 3, 4, 5 ❌ (harusnya lanjut)

---

### ✅ Solusi

Gunakan perhitungan berikut:

```blade id="g8q2xp"
{{ ($data->currentPage() - 1) * $data->perPage() + $loop->iteration }}
```

---

### 🧠 Penjelasan

* `$data->currentPage()` → halaman saat ini
* `$data->perPage()` → jumlah data per halaman
* `$loop->iteration` → nomor urut di loop saat ini

👉 Rumus:

```id="q9n2jk"
(offset halaman) + (urutan di halaman sekarang)
```

---

### 📌 Contoh

Misalnya:

* perPage = 10
* halaman = 2

Maka:

```id="c4z8ya"
(2 - 1) * 10 + 1 = 11
```

Hasil:

* Data pertama di halaman 2 = nomor 11 ✅

---

### 💡 Contoh di Blade

```blade id="h1v6lk"
@foreach ($data as $item)
    <tr>
        <td>{{ ($data->currentPage() - 1) * $data->perPage() + $loop->iteration }}</td>
        <td>{{ $item->name }}</td>
    </tr>
@endforeach
```

---

### 🎯 Kesimpulan

* Pagination reset nomor urut ❌
* Gunakan rumus untuk lanjutkan nomor ✅
* Cocok untuk tabel data

---

**Note:**
Kalau nomor tiba-tiba balik ke 1, berarti lupa pakai rumus ini 😅

---
