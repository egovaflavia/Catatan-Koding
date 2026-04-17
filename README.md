# Catatan-Koding
Catatan ini sebagai pengingat dimasa akan datang, Berisi catatan kesalahan kecil yang sering terjadi dalam ngoding wkkwkw

## Try Catch Probs

Saat menggunakan Try Catch  ```catch (QueryException $e)``` diletkan diatas urutan ```catch (Exception $e)``` sebagai prioritas pengecekan koneksi database

## Iterasi jika menggunakan Paginate
```{{ ($data->currentPage() - 1) * $data->perPage() + $loop->iteration }}```

## [LIVEWIRE] $data di Komponen
```$this→data``` tidak bisa digunakan

## [TERMINAL] Install Oh My Posh di CMDER
Ikuti langkah https://satheeshds.github.io/tech/2023/03/25/cmder-oh-my-posh-widows-terminal-vscode. Pada ```C:\laragon\bin\cmder\vendor\clink\clink.lua``` tambahkan 
load(io.popen('oh-my-posh init cmd --config "C:/Users/KangSseulgi/AppData/Local/Programs/oh-my-posh/themes/material.omp.json"'):read("*a"))()

## [LARAVEL] Email Tips
MAIL_MAILER=smtp
MAIL_HOST={host} #misal srv184.niagahoster.com
MAIL_PORT=465
MAIL_USERNAME={akun email}
MAIL_PASSWORD={password email}
MAIL_ENCRYPTION=ssl
MAIL_FROM_ADDRESS="{sender, samakan aja dengan akun email}"
MAIL_FROM_NAME="${APP_NAME}"
