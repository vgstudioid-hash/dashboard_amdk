# Logistik Control Tower

Dashboard statis berbahasa Indonesia untuk demonstrasi pemantauan pengiriman, keluar-masuk gudang, armada, persediaan, dan biaya/pembiayaan. Antarmuka mengambil inspirasi dari contoh dashboard Distribusi AMDK yang disertakan.

## Jalankan lokal

Buka `index.html` di browser, atau jalankan server lokal:

```bash
python3 -m http.server 8000
```

Lalu buka `http://localhost:8000`.

## Publikasikan dengan GitHub Pages

1. Buat repository GitHub baru. Unggah seluruh isi paket ini ke root repository.
2. Buka **Settings → Pages**.
3. Pada **Build and deployment**, pilih **GitHub Actions**.
4. Push ke branch `main`. Workflow `.github/workflows/pages.yml` akan menerbitkan dashboard.
5. URL akan tampil di pengaturan Pages repository.

Dashboard ini sengaja hanya berupa aset statis tanpa library build. Koneksi internet diperlukan untuk memuat font DM Sans dan Manrope dari Google Fonts; jika font tidak tersedia, browser memakai sans-serif sistem.

## Fitur demonstrasi

- Ringkasan KPI distribusi, ketepatan pengiriman, stok, dan biaya.
- Peta rute ilustratif dengan status perjalanan simulasi.
- Daftar pengiriman, stok per SKU/lokasi, ketersediaan armada, anggaran dan biaya.
- Pencarian tabel, filter periode ringkasan, ekspor CSV, navigasi responsif.
- Form simulasi untuk pengiriman, mutasi gudang, kendaraan, dan data master.
- Halaman arsitektur data dan kontrol minimum.

Data di `app.js` seluruhnya berupa contoh. Form hanya memberi konfirmasi pada browser dan tidak menyimpan ke server. Posisi armada maupun peta tidak berasal dari GPS langsung.

## Batas penggunaan GitHub Pages

GitHub Pages hanya menjadi host antarmuka statis. Jangan mengunggah data pelanggan, transaksi internal, token GPS, password, API key, atau kredensial ke repository publik maupun ke JavaScript sisi browser. Mengganti contoh dengan data internal memerlukan backend/API privat yang menyediakan autentikasi, otorisasi, audit log, dan koneksi terenkripsi. Repository privat membantu membatasi akses kode sumber, tetapi tidak menjadikan data yang dikirim ke browser sebagai data rahasia.

## Berkas

- `index.html` — struktur dan halaman dashboard.
- `styles.css` — gaya responsif.
- `app.js` — data contoh dan interaksi browser.
- `ARCHITECTURE.md` — rancangan arsitektur, model data, dan tahapan integrasi.
- `.github/workflows/pages.yml` — workflow publikasi GitHub Pages.
