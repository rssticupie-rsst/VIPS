# VIPS Digital

## Isi
- `index.html`: aplikasi web satu berkas, tanpa proses build.
- Scoring prototipe 0–5, interpretasi dan tindakan awal dari gambar VIPS.
- Riwayat lokal pada browser, ekspor CSV, cetak/Simpan sebagai PDF.
- Tidak ada backend, login, sinkronisasi, atau penyimpanan cloud.

## Cara menjalankan lokal
1. Ekstrak ZIP.
2. Buka `index.html` dengan browser modern.
3. Pilih gejala lalu tekan **Hitung skor VIPS**.
4. Simpan untuk menguji riwayat lokal.
5. Ekspor CSV atau pilih **Cetak / Simpan sebagai PDF**.

## Publikasi gratis dengan GitHub Pages
1. Buat akun GitHub jika belum ada.
2. Buat repository baru, misalnya `vips-digital` (Public hanya jika kontennya tidak memuat data pasien).
3. Unggah `index.html` ke root repository.
4. Buka **Settings → Pages**.
5. Pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu Save.
6. Setelah GitHub Pages memberi URL, buka URL itu di HP dan uji seluruh fungsi.
7. Buat QR Code dari URL publik menggunakan pembuat QR Code tepercaya, lalu uji QR dari perangkat lain sebelum dicetak.

## Batasan penting
- Riwayat disimpan di `localStorage` browser. Data hanya tersedia pada browser/perangkat yang sama; membersihkan data browser dapat menghapus riwayat.
- Jangan masukkan nama, nomor rekam medis, atau informasi kesehatan yang dapat mengidentifikasi pasien ke prototipe ini.
- Hosting web publik berarti siapa pun yang memiliki URL bisa membuka aplikasi. Jangan anggap URL/QR sebagai kontrol akses.
- Untuk penggunaan bersama dan penyimpanan klinis, diperlukan autentikasi, otorisasi, backend/database yang dikelola rumah sakit, audit trail, backup, kebijakan retensi, dan tinjauan keamanan/privasi.
- Prototipe ini bukan alat medis tervalidasi. Rumus skor dan tindakan harus diverifikasi oleh tim klinis serta disahkan dalam SOP sebelum penggunaan klinis.

## Aturan skor yang diprototipekan dari gambar
- 0: tidak ada gejala yang dipilih.
- 1: nyeri ringan pada tempat IV atau sedikit kemerahan dekat IV line; juga digunakan sebagai fallback bila hanya satu gejala inti dipilih.
- 2: dua dari tiga gejala inti: nyeri sepanjang jalur kanula, kemerahan, pembengkakan.
- 3: ketiga gejala inti.
- 4: ketiga gejala inti + vena teraba keras.
- 5: ketiga gejala inti + vena teraba keras + pireksia/demam.

Fallback skor 1 dan penanganan kombinasi yang tidak cocok harus ditinjau klinis. Ini adalah asumsi implementasi awal, bukan penetapan klinis final.
