KresaManagement MVP — Kresaidea

CARA MENJALANKAN
1. Ekstrak seluruh isi ZIP ke satu folder.
2. Buka index.html di browser modern (Chrome/Edge disarankan).
3. Untuk instalasi sebagai aplikasi/PWA dan cache offline, unggah semua isi folder ke hosting HTTPS.

PENYIMPANAN
- Data profil dan metadata booking disimpan lokal pada browser.
- Foto booking disimpan terpisah di IndexedDB pada browser/perangkat yang sama.
- Data tidak otomatis tersinkron antara laptop dan ponsel.
- Gunakan menu Backup secara berkala. File backup JSON mencakup booking, foto, dan profil.
- Jangan hapus data situs/browser sebelum membuat backup.

EKSPOR
- Invoice: JPG.
- Daftar booking: PDF A4 melalui modul html2pdf yang saat ini dimuat dari CDN, sehingga tombol ekspor PDF masih memerlukan koneksi internet untuk memuat modul tersebut.

Catatan: Ini MVP untuk pengujian. Lakukan uji backup/restore sebelum dipakai untuk operasional utama.


LISENSI KRESAMANAGEMENT (VERSI INTEGRASI AWAL)
- Aktivasi pertama memerlukan internet dan kode lisensi yang dibuat pada KresaManagement License Manager.
- Setelah aktivasi tersimpan di browser/perangkat yang sama, aplikasi membuka secara offline tanpa memeriksa server setiap kali.
- Jangan hapus data situs/browser atau penyimpanan lokal: hal itu dapat menghapus data aplikasi dan salinan aktivasi. Jika perangkat perlu diganti atau penyimpanan terhapus, admin harus menangani pelepasan/perubahan perangkat pada License Manager.
- Catatan keamanan: ini aplikasi web offline. Data aktivasi di penyimpanan browser bukan perlindungan anti-pembajakan yang setara dengan aplikasi native; pengguna teknis yang mengubah storage/kode lokal dapat melewati gate. Token tidak diverifikasi kriptografis secara offline karena server saat ini menggunakan HMAC dan tidak boleh membagikan secret ke browser. Untuk perlindungan komersial lebih kuat diperlukan skema tanda tangan asimetris dan/atau pemeriksaan server berkala.
- Tes integrasi ini belum dianggap lulus sebelum diuji di hosting HTTPS dengan aktivasi nyata, reload, dan mode offline.
