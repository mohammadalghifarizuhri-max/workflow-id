WORKFLOW.ID — PAKET PWA UNTUK IPHONE

ISI PAKET
- index.html: prototype asli, dengan penambahan dukungan PWA.
- manifest.webmanifest: nama aplikasi, ikon, dan mode standalone.
- service-worker.js: menyimpan app shell agar bisa dibuka kembali saat offline.
- icons/: ikon aplikasi untuk iPhone dan browser.

CARA MEMASANG DI IPHONE (GRATIS)
1. Unggah seluruh ISI folder workflow-id-pwa ke sebuah hosting statis HTTPS gratis.
   Pilihan sederhana: GitHub Pages. Jangan hanya mengunggah index.html; semua file
   dan folder harus ikut diunggah dengan struktur yang sama.
2. Buka URL HTTPS situs tersebut menggunakan Safari di iPhone.
3. Biarkan halaman selesai dimuat saat internet aktif. Service worker akan memasang
   cache aplikasi pada kunjungan pertama.
4. Ketuk tombol Share/Bagikan di Safari, lalu pilih Add to Home Screen/Tambahkan ke
   Layar Utama. Jika tersedia, aktifkan Open as Web App/Buka sebagai App.
5. Jalankan WorkFlow.id dari ikon di Home Screen. Setelah cache awal berhasil dibuat,
   app shell dapat dibuka tanpa koneksi internet.
6. Uji offline dengan membuka aplikasi sekali saat online, tutup aplikasi, aktifkan
   Airplane Mode, lalu buka kembali dari ikon Home Screen.

CATATAN PENTING
- Pemasangan pertama dan pengunduhan cache membutuhkan internet.
- PWA harus disajikan melalui HTTPS (atau localhost untuk pengembangan). Membuka
  index.html langsung dari aplikasi Files tidak mengaktifkan service worker.
- Data prototype disimpan di localStorage browser/perangkat. Data tidak otomatis
  tersinkron ke perangkat lain. Jangan hapus data situs/browser jika ingin menjaga data.
- Ini adalah web app yang tampil standalone, bukan aplikasi native App Store.
- Untuk menerbitkan pembaruan, ubah CACHE_NAME di service-worker.js (misalnya v2)
  agar perangkat mengambil versi cache terbaru.
