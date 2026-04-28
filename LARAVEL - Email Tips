## 📧 [LARAVEL] Email Tips

Konfigurasi dasar email di Laravel menggunakan SMTP.

---

### ⚙️ Konfigurasi `.env`

```env id="3p8k2q"
MAIL_MAILER=smtp
MAIL_HOST={host}            # contoh: srv184.niagahoster.com
MAIL_PORT=465
MAIL_USERNAME={akun email}
MAIL_PASSWORD={password email}
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS="{sender}"   # samakan dengan akun email
MAIL_FROM_NAME="${APP_NAME}"
```

---

### 🧠 Penjelasan

* `MAIL_MAILER` → driver yang digunakan (smtp)
* `MAIL_HOST` → server SMTP dari provider hosting/email
* `MAIL_PORT` → port email (umumnya 465 untuk SSL)
* `MAIL_USERNAME` → email yang digunakan
* `MAIL_PASSWORD` → password email
* `MAIL_ENCRYPTION` → jenis enkripsi (`ssl` / `tls`)
* `MAIL_FROM_ADDRESS` → email pengirim (disarankan sama dengan username)
* `MAIL_FROM_NAME` → nama pengirim (ambil dari `APP_NAME`)

---

### ❌ Masalah yang Sering Terjadi

* Email tidak terkirim
* Timeout / connection refused
* Authentication failed

---

### 💡 Tips Penting

* Pastikan:

  * username & password benar
  * host sesuai provider

* Gunakan:

  * `ssl` → port 465
  * `tls` → port 587

* Biasakan:

  ```env id="p7l4md"
  MAIL_FROM_ADDRESS = MAIL_USERNAME
  ```

---

### 🧪 Testing

Gunakan Tinker:

```bash id="6b8n3y"
php artisan tinker
```

Lalu coba kirim email untuk testing.

---

### ⚠️ Catatan

* Beberapa hosting perlu:

  * whitelist IP
  * atau aktifkan SMTP
* Jangan commit `.env` ke repository

---

### 🎯 Kesimpulan

* SMTP harus sesuai provider
* Port & encryption harus cocok
* Email sender sebaiknya sama dengan akun

---

**Note:**
Kalau email tidak terkirim, 90% masalah ada di konfigurasi `.env` 😅

---
