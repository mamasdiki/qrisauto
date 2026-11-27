# DANA QRIS Bot PWA V2

PWA pribadi untuk membaca QRIS dari gambar, mengelola antrean, dan menyimpan screenshot bukti yang dipilih sendiri dari galeri.

## Batasan dan keselamatan
- Bukan aplikasi resmi DANA dan tidak terhubung ke API pembayaran DANA.
- Tidak mengendalikan aplikasi DANA, tidak menekan tombol pembayaran, dan tidak mengisi PIN/OTP.
- Pengguna harus membuka DANA sendiri, memindai QRIS, memeriksa merchant/nominal, dan mengotorisasi pembayaran.
- Bukti screenshot yang diunggah tidak diverifikasi oleh server DANA. Status "Dicek manual" hanya menandakan pengguna menyatakan sudah memeriksa bukti.
- QRIS bernominal tetap tidak diubah. Target Rp10 hanya pengingat. Jangan lanjutkan bila nominal/merchant di DANA tidak sesuai.
- Pemeriksaan CRC/struktur hanya membantu mendeteksi kerusakan data, bukan membuktikan QRIS asli atau aman.
- QR decoder jsQR dimuat dari jsDelivr CDN; koneksi internet diperlukan untuk memuat library tersebut, terutama pada kunjungan pertama.
- Data antrean dan screenshot disimpan lokal dalam IndexedDB browser pada perangkat. Hapus data situs/browser dapat menghilangkannya. Ekspor laporan dan simpan screenshot penting secara terpisah.

## Deploy ke GitHub Pages
1. Buat repository GitHub (Public bila memakai GitHub Free).
2. Unggah seluruh isi folder ini ke root repository; `index.html` harus di root dan folder `icons` ikut diunggah.
3. Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save.
4. Buka URL HTTPS GitHub Pages dari Safari iPhone.
5. Share → Add to Home Screen.

## Penggunaan
1. Pilih gambar QRIS. Aplikasi akan mencoba mendekode dan menampilkan data.
2. Masukkan target nominal (default Rp10) lalu tambahkan ke antrean.
3. Buka DANA secara manual dan lakukan proses pembayaran dengan otorisasi sendiri.
4. Setelah pembayaran, pilih transaksi pada bagian Bukti Pembayaran dan unggah screenshot dari galeri.
5. Periksa bukti sendiri. Tombol "Tandai sudah saya periksa" hanya catatan manual.
6. Ekspor TXT, CSV, atau PNG sebagai laporan.

## Pengujian lokal
Jalankan server lokal dari folder ini:
`py -m http.server 8000`
Kemudian buka `http://localhost:8000` pada komputer. Untuk instalasi PWA di iPhone gunakan hosting HTTPS seperti GitHub Pages.
