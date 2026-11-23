# Daftar Hadir HSE Event

Aplikasi daftar hadir digital acara HSE: form peserta (paraf, online/offline, acara berulang), dashboard panitia (rekap, ubah data, analisa kehadiran, cetak form WB-CPR-PS-01-F27, unduh Excel), kelola acara dengan link & QR code.

Alamat untuk peserta: **https://hsewikabeton.github.io/hsewb/**

## Arsitektur
- **Aplikasi & data**: Google Apps Script "Daftar Hadir HSE Event" (akun hse.wikabeton@gmail.com), terikat ke spreadsheet "Daftar Hadir HSE Event" (sheet *Kehadiran*, *Acara*, *Unit Kerja*).
  - `Code.gs` — backend
  - `Index.html` — tampilan
- **Repo ini**: `index.html` hanya membingkai Web App Apps Script dan meneruskan `?event=EVT-xxxx`.

## Mengubah aplikasi
1. Edit `Code.gs` / `Index.html` di Apps Script, simpan.
2. **Deploy › Manage deployments › ✏️ Edit › Version: New version › Deploy** (URL tetap sama).

## Admin
Ikon profil di kanan atas → login. Username & password ada di **Apps Script › Project Settings › Script Properties** (`ADMIN_USER`, `ADMIN_PASS`) dan bisa diganti di sana.
