## ⚡ [LIVEWIRE] `$data` di Komponen

Catatan penting saat menggunakan Livewire terkait penggunaan variabel `$data`.

---

### ❌ Masalah yang Sering Terjadi

Mengira `$this->data` bisa langsung digunakan di Blade seperti `$data`.

Contoh:

```php
// Livewire Component
public $data;
```

```blade
{{-- Blade --}}
{{ $data }} ❌
```

👉 Error / tidak terbaca

---

### 🧠 Penyebab

Di Livewire:

* `$this->data` = milik class (backend)
* `$data` di Blade = harus dikirim ke view

👉 Tidak otomatis tersedia sebagai `$data` di Blade

---

### ✅ Cara yang Benar

#### ✔️ 1. Gunakan langsung property (Livewire v2/v3)

```blade
{{ $this->data }}
```

---

#### ✔️ 2. Atau kirim lewat `render()`

```php
public function render()
{
    return view('livewire.example', [
        'data' => $this->data
    ]);
}
```

Blade:

```blade
{{ $data }}
```

---

### 📌 Contoh Lengkap

```php
class Example extends Component
{
    public $data = 'Hello World';

    public function render()
    {
        return view('livewire.example');
    }
}
```

```blade
{{-- livewire/example.blade.php --}}
{{ $this->data }}
```

---

### 💡 Tips

* Gunakan `$this->property` kalau mau langsung akses
* Gunakan `render()` kalau mau kirim sebagai variable biasa
* Jangan campur dua cara tanpa alasan

---

### 🎯 Kesimpulan

* `$this->data` ❗ (di komponen)
* `$data` ❗ (harus dikirim ke view)

👉 Livewire tidak otomatis mengubah `$this->data` menjadi `$data`

---

**Note:**
Kalau `$data` undefined, kemungkinan besar belum dikirim dari `render()` 😅

---
