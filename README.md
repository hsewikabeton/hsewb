# Daftar Hadir HSE Event

Aplikasi daftar hadir digital untuk acara HSE: form peserta (dengan paraf, kehadiran online/offline), dashboard panitia (rekap, ubah data, cetak/PDF, unduh Excel), kelola acara dengan link & QR code. Data tersimpan di Google Sheets.

Alamat: **https://hsewikabeton.github.io/hsewb/**

## Isi repo
| File | Fungsi |
|---|---|
| `index.html` | Aplikasi web (di-host GitHub Pages) |
| `Code.gs` | Backend Google Apps Script — **jangan** di-upload ke GitHub, tempel di Apps Script |

## 1. Pasang backend (Google Sheets + Apps Script)
1. Buat Google Spreadsheet baru → **Extensions › Apps Script**.
2. Tempel seluruh isi `Code.gs`, simpan.
3. Pilih fungsi **`setup`** → **Run** → izinkan akses. Sheet *Kehadiran*, *Acara*, *Unit Kerja* dibuat otomatis dan akun admin diisi.
4. **Deploy › New deployment › Web app** — *Execute as:* Me, *Who has access:* Anyone → salin URL berakhiran `/exec`.
5. Buka `index.html`, isi `GAS_WEBAPP_URL: 'https://script.google.com/macros/s/.../exec'`.

Mengubah kode Apps Script nanti: **Deploy › Manage deployments › Edit › Version: New version** (URL tetap sama).

## 2. Publikasi (GitHub Pages)
Repo: `hsewikabeton/hsewb` → **Settings › Pages** → Source: *Deploy from a branch*, Branch: `main` / `(root)`.
Setelah `GAS_WEBAPP_URL` diisi, edit `index.html` di GitHub (ikon pensil) lalu Commit — situs otomatis ter-update.

Link per acara (bisa dibuat dari menu *Kelola Acara › Link & QR*):
`https://hsewikabeton.github.io/hsewb/?event=EVT-xxxxxxxx-XXXX`

## Admin
Klik ikon profil di kanan atas → login. Username & password disimpan di **Apps Script › Project Settings › Script Properties** (`ADMIN_USER`, `ADMIN_PASS`) dan bisa diganti di sana kapan saja.
