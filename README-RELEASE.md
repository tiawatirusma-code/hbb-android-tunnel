# HBB Android — Release Online

Workflow GitHub Actions ini membangun **HBB-release.apk** di cloud GitHub.

## Secret yang diperlukan
Buat 4 Repository Secrets di **Settings → Secrets and variables → Actions**:
- `HBB_KEYSTORE_BASE64` — Base64 file `hbb-release.jks`
- `HBB_KEYSTORE_PASSWORD` — password keystore
- `HBB_KEY_ALIAS` — alias key, misalnya `hbb`
- `HBB_KEY_PASSWORD` — password key

Jalankan `prepare-release-keystore.ps1` sekali pada komputer yang memiliki JDK 17+ untuk membuat keystore. Simpan file dan password dengan aman.

PowerShell untuk menyalin Base64 ke clipboard:
`[Convert]::ToBase64String([IO.File]::ReadAllBytes(".\hbb-release.jks")) | Set-Clipboard`

## Build
1. Upload project ke GitHub.
2. Buka **Actions**.
3. Pilih **Build HBB Android Release APK**.
4. Klik **Run workflow**.
5. Download artifact **HBB-release-APK**.

Hasilnya: `HBB-release.apk`.

**Penting:** jangan kehilangan `hbb-release.jks`. Semua update aplikasi HBB harus memakai key yang sama agar dapat meng-update APK lama.
