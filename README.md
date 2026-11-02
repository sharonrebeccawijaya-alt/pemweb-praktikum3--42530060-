# pemweb-praktikum3--42530060-
# Praktikum 3: Express + MySQL CRUD dengan Prepared Statements

- Nama: Sharon Rebecca Wijaya
- NIM: 42530060
- Mata Kuliah: Pemrograman Web

## Teknologi
Express, EJS, MySQL2 (Connection Pool), dotenv

## Cara Menjalankan
1. `npm install`
2. Import `database.sql` ke MySQL
3. Salin `.env.example` menjadi `.env`, sesuaikan isinya
4. `npm run dev`, buka http://localhost:3000/produk

## Logbook Pengujian

| ID Uji | Fitur / Operasi | Endpoint URL | HTTP Method | Skenario Pengujian | Hasil yang Diharapkan | Status | Bukti Tangkapan Layar |
|---|---|---|---|---|---|---|---|
| TC-01 | Koneksi Pool | App Startup | - | Server dijalankan pertama kali | Terhubung ke MySQL Pool tanpa error | Pass | ![TC-01](docs/screenshots/01-db-pool-connection.png) |
| TC-02 | Read (All) | /produk | GET | Akses halaman daftar produk | Seluruh record tampil di antarmuka EJS | Pass | ![TC-02](docs/screenshots/02-read-select-render.png) |
| TC-03 | Create | /produk/tambah | POST | Submit formulir produk baru | Data tersimpan, DevTools mencatat 302 Redirect ke /produk | Pass | ![TC-03](docs/screenshots/03-create-insert-prg.png) |
| TC-04 | Update | /produk/edit/:id | POST | Mengubah harga dan stok | Nilai kolom di MySQL berubah sesuai input | Pass | ![TC-04](docs/screenshots/04-update-param-redirect.png) |
| TC-05 | Delete | /produk/hapus/:id | POST | Klik tombol hapus | Baris terhapus dari MySQL dan UI ter-refresh | Pass | ![TC-05](docs/screenshots/05-delete-feedback.png) |
| TC-06 | Keamanan | /uji-keamanan | GET | Input `' OR '1'='1` via URL | Input diperlakukan sebagai teks biasa (tanpa injeksi) | Pass | ![TC-06](docs/screenshots/06-sql-injection-mitigation.png) |

## Troubleshooting

| Kasus | Bukti |
|---|---|
| ER_ACCESS_DENIED_ERROR | ![Kasus 1](docs/screenshots/07-error-access-denied.png) |
| Bind parameters must not contain undefined | ![Kasus 2](docs/screenshots/08-error-undefined-bind.png) |
