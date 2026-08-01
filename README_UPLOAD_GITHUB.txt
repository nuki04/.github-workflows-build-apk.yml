UPDATE EXAMVOICEBROWSER DI GITHUB — V1.1.4
=========================================

Repository tujuan:
nuki04/.github-workflows-build-apk.yml

Perubahan aplikasi:
- Tampilan dan fitur lain tidak diubah.
- Fungsi baca soal dan seluruh pilihan jawaban dipertahankan.
- minSdk tetap 23, sehingga source mendukung Android 6 ke atas.
- versionCode dinaikkan menjadi 14.
- versionName dinaikkan menjadi 1.1.4.
- Build release memakai keystore tetap agar APK berikutnya dapat dipasang sebagai pembaruan.

LANGKAH 1 — UNGGAH SOURCE
1. Buka repository GitHub.
2. Pilih Add file > Upload files.
3. Unggah ExamVoiceBrowser_Source.zip ke folder paling atas repository.
4. Commit dengan pesan: Update ExamVoiceBrowser v1.1.4

LANGKAH 2 — GANTI WORKFLOW
1. Buka .github/workflows/build-apk.yml.
2. Pilih Edit.
3. Ganti seluruh isinya dengan isi file build-apk.yml dalam paket ini.
4. Commit perubahan.

LANGKAH 3 — TAMBAHKAN GITHUB ACTIONS SECRETS
Buka Settings > Secrets and variables > Actions > New repository secret.
Tambahkan empat secret berikut:

ANDROID_KEYSTORE_BASE64
- Isi dengan seluruh teks dari ANDROID_KEYSTORE_BASE64.txt.

ANDROID_KEYSTORE_PASSWORD
- Isi: examvoice123

ANDROID_KEY_ALIAS
- Isi: examvoice

ANDROID_KEY_PASSWORD
- Isi: examvoice123

LANGKAH 4 — BUILD APK
1. Buka tab Actions.
2. Pilih Build Exam Voice Browser APK.
3. Pilih Run workflow.
4. Setelah selesai, unduh artifact ExamVoiceBrowser-v1.1.4-apk.
5. Gunakan app-release.apk untuk instalasi dan pembaruan.
6. Jangan gunakan app-debug.apk untuk distribusi pembaruan.

CATATAN TANDA TANGAN
Keystore dalam paket ini memiliki fingerprint SHA-256:
F6:7C:E8:A8:C1:F6:0E:91:51:46:ED:97:DB:A0:A2:87:1B:4E:2C:19:49:68:08:C0:EA:F3:02:48:D4:DD:BA:4C

Fingerprint tersebut sama dengan APK ExamVoiceBrowser_BacaSoalJawaban_ChromeTTS.apk yang dibuat sebelumnya. Karena itu, app-release.apk dari GitHub dapat memperbarui APK tersebut selama applicationId tetap id.schoolsafe.examvoice dan versionCode lebih tinggi.

Jangan membagikan keystore atau nilai secret kepada orang lain.
