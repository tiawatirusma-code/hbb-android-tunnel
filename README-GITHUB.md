# HBB Android — Build APK via GitHub Actions

Source ini sudah siap untuk koneksi server menggunakan **URL**, bukan hanya alamat IP.

Contoh URL server:
`https://contoh.loca.lt/hbb-fullstack/`

## Build APK
1. Buat repository GitHub baru.
2. Upload seluruh isi folder project ini.
3. Pastikan `.github/workflows/build-apk.yml` ikut ter-upload.
4. Buka **Actions**.
5. Pilih **Build HBB Android APK**.
6. Klik **Run workflow**.
7. Setelah selesai, buka job tersebut.
8. Di bagian **Artifacts**, download `HBB-Android-Tunnel-Test`.

APK yang dihasilkan adalah debug APK untuk pengujian di HP.

## Mengatur koneksi di HP
Buka aplikasi → **Pengaturan Koneksi Server**.

Isi URL lengkap, misalnya:
`https://flat-sides-care.loca.lt/hbb-fullstack/`

Lalu tekan **Tes Koneksi** dan setelah berhasil tekan **Simpan Server**.

## Catatan
- URL LocalTunnel dapat berubah setiap kali tunnel dibuat.
- CMD yang menjalankan `lt --port 80` harus tetap terbuka.
- Untuk penggunaan produksi, sebaiknya HBB API dipasang pada domain/server online permanen.
- APK Android tidak menyimpan password MySQL; Android hanya mengakses API HBB.
